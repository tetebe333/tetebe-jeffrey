<script lang="ts">
 import { onMount } from 'svelte';
 import project1 from '$lib/assets/project1.jpg';
  import project2 from '$lib/assets/project2.jpg';
  import project3 from '$lib/assets/project3.jpg';
  import project4 from '$lib/assets/project4.jpg';
  import flash_chat from '$lib/assets/flash_chat.PNG';
  import coin_ticker from '$lib/assets/coin_ticker.PNG';
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
      <img class="w-50 h-50 mx-auto rounded-3xl" src={project1} alt="Project 1">
      <h1 class="text-center font-bold mt-3 text-lg">Project One</h1>
      <p class="text-center text-gray-500 pb-2">note keeping website</p>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/note-keeping" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-notekeeping.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src={flash_chat} alt="Project 2">
      <h1 class="text-center font-bold mt-3 text-lg">Project Two</h1>
      <p class="text-center text-gray-500 pb-2">flash chat application</p>
      <div class="flex justify-center gap-3 px-17">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in w-full text-center" href="https://github.com/tetebe333/flash-chat" target="_blank">Github</a>
      </div>
  </div>

</div>


<div class="sm:grid-cols-2 grid-cols-1 gap-4 grid mt-4">

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src={project2} alt="Project 2">
      <h1 class="text-center font-bold mt-3 text-lg">Project Three</h1>
      <p class="text-center text-gray-500 pb-2">contact management website</p>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeff-contact" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-contact.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src={coin_ticker} alt="Project 4">
      <h1 class="text-center font-bold mt-3 text-lg">Project Four</h1>
      <p class="text-center text-gray-500 pb-2">crypto currency ticker app</p>
      <div class="flex justify-center gap-3 px-17">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in w-full text-center" href="https://github.com/tetebe333/bitcoin_ticker" target="_blank">Github</a>
      </div>
  </div>
</div>

<div class="sm:grid-cols-2 grid-cols-1 gap-4 grid mt-4">

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src={project3} alt="Project 3">
      <h1 class="text-center font-bold mt-3 text-lg">Project Five</h1>
      <p class="text-center text-gray-500 pb-2">invoice management website</p>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeff-invoice" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeff-invoice.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>

  <div class="border w-full rounded-2xl py-6 px-3">
      <img class="w-50 h-50 mx-auto rounded-3xl" src={project4} alt="Project 4">
      <h1 class="text-center font-bold mt-3 text-lg">Project Six</h1>
      <p class="text-center text-gray-500 pb-2">blacklist management website</p>
      <div class="flex justify-center gap-3">
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://github.com/tetebe333/jeffrey-blacklist" target="_blank">Github</a>
        <a class="sbtn hover:text-black hover:bg-white hover:duration-400 hover:ease-in" href="https://jeffrey-blacklist.vercel.app/" target="_blank">Veiw</a>
      </div>
  </div>
</div>



</div>