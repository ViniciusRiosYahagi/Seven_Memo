<script lang="ts">

  let { text } = $props()

  function saveText() {
    localStorage.setItem('text', JSON.stringify(text))
  }

  function handleText(event: Event): void {
    let value = event.target as HTMLElement
    text = value.innerHTML || ''
    saveText()
  }

</script>
<input type="text">

<section class="flex flex-col shadow-lg bg-[#E5E5E5] p-3">
  <textarea
    class="outline-0 h-full min-h-96 w-6xl break-words text-[#636363] text-2xl"
    contenteditable="true" 
    bind:value={text}
    ></textarea>
</section>
