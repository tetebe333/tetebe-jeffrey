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
  class="transition-all duration-700 w-80% max-w-800 mx-auto  text-gray-300"
>

<div class="mt-30 mb-8">
    <p class="text-center ">Get In Touch</p>
    <h1 class="font-bold text-2xl text-center">Contact me</h1>
</div>

<div class="flex flex-col sm:flex-row gap-3 border mx-auto p-5 rounded-3xl mb-8 sm:justify-between sm:w-99">
  <div class="flex justify-center items-center gap-1.5">
    <img class="h-5" src="https://img.icons8.com/small/16/FFFFFF/filled-message.png" alt="">
    <a class="" href="mailto:tetebejeffrey@gmail.com" target="_blank">tetebejeffrey@gmail.com</a>
  </div>

  <div class="flex justify-center items-center gap-1.5">
    <img class="h-5" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/linkedin.png" alt="">
    <a href="https://www.linkedin.com/in/tetebe-jeffrey-974b2a284/" target="_blank">linkedIn</a>
  </div>
</div>


</div>