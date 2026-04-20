<script lang="ts">
 import { onMount } from 'svelte';
  let containerElement: HTMLElement;
  let isIntersecting = false;  

  onMount(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            isIntersecting = true;
          }
        });
      },
      {
        root: null, // observe the viewport
        rootMargin: '0px',
         threshold: 0.1, // trigger when 10% of the element is visible
      }
    );

    if (containerElement) {
      observer.observe(containerElement);
    }

    return () => {
      if (containerElement) {
        observer.unobserve(containerElement);
      }
    };
  });
</script>

<div
  bind:this={containerElement}
  class:opacity-0={!isIntersecting}
  class:translate-y-5={!isIntersecting}
  class:animate-fadeSlideIn={isIntersecting}
 class="transition-all duration-700 text-gray-300 border-t border-black w-80% max-w-800 mx-auto mb-12"
>

<div class="mt-12 mb-8">
    <p class="text-center">Explore my</p>
    <h1 class="font-bold text-2xl text-gray-300 text-center">Projects</h1>
</div>

<div class="sm:grid-cols-2 grid-cols-1 gap-4 grid">
  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src="https://media.licdn.com/dms/image/v2/D4E22AQEN4bdCfrjIfQ/feedshare-shrink_2048_1536/B4EZ2q2SR8IcAg-/0/1776687850954?e=1778112000&v=beta&t=JI4JkKIH1jmz9wJI4hx5Vn-NlHACA5o5EMTNOHey76A" alt="">
      <h1 class="text-center font-bold my-3 text-lg">Project One</h1>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/note-keeping" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-notekeeping.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src="https://media.licdn.com/dms/image/v2/D4D22AQFDWxjqpGy43A/feedshare-shrink_800/B4DZx1vPQJGQAg-/0/1771501843794?e=1777507200&v=beta&t=1QWB8GG4ljWAcSu1oAlz3aXrbc71wciIhuUdXZeSZc4" alt="">
      <h1 class="text-center font-bold my-3 text-lg">Project Two</h1>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeff-contact" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-contact.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

</div>


<div class="sm:grid-cols-2 grid-cols-1 gap-4 grid mt-4">

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src="https://media.licdn.com/dms/image/v2/D4D22AQHVZBIuVjTpug/feedshare-shrink_480/B4DZq7pm2qIAAY-/0/1764084839884?e=1777507200&v=beta&t=JSwAqgpc0wj7v5aQAMaWJNvlhjOpksiEijeE36BZPDA" alt="">
      <h1 class="text-center font-bold my-3 text-lg">Project Three</h1>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeff-invoice" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-invoice.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src="https://media.licdn.com/dms/image/v2/D4D22AQGoRZD0lr-vxQ/feedshare-shrink_480/B4DZq7pmqEJEAY-/0/1764084839789?e=1777507200&v=beta&t=QGNJazaKdvrcbc0Db-fUeTAoMRLlquRQyqsg-NzySMA" alt="">
      <h1 class="text-center font-bold my-3 text-lg">Project Four</h1>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeffrey-blacklist" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeffrey-blacklist.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>
</div>

</div>