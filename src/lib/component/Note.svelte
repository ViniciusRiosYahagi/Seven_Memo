<script lang="ts">
  let { text } = $props();
  
  let altura = $state();

  function autoResize(event: Event) {
    const textarea = event.target as HTMLTextAreaElement;
    altura = textarea.scrollHeight;
    console.log(altura)
    if (text.length === 0) {
      altura = 400
    }
  }

  // function autoResizeble() {
  //   altura = text.length 
  //   console.log(altura)
  // }
</script>

<section class="flex flex-col shadow-lg bg-[#E5E5E5] p-3">
  <textarea
    class="outline-0 min-h-[400px] w-5xl break-words text-[#636363] text-2xl"
    style="height: {altura}px;"
    oninput={autoResize}
    bind:value={text}
  ></textarea>
</section>
