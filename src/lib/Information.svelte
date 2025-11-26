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
  class=" text-gray-300 "
>
  <div class="mt-12">
    <p class="text-center">Get To Know More</p>
    <h1 class="font-bold text-2xl text-gray-300 text-center">About Me</h1>
  </div>

  <div class="sm:grid flex flex-col  grid-cols-3 gap-5 float-left mt-10">
    <div>
      <img class=" h-79  w-70 sm:w-70 sm:h-60 rounded-2xl shadow-xl/20 sm:mx-0 mx-auto" src="https://media.licdn.com/dms/image/v2/D4D22AQGBYsnVFWUYvQ/feedshare-shrink_2048_1536/B4DZq3nT7aHsAw-/0/1764017135233?e=1765411200&v=beta&t=dTDC11t3SqGailoHWLfu8QjGhUAa1kzktxn9reCd-0I" alt="">
    </div>

    <div class="col-span-2 ">
      <div class="sm:flex block col-span-2 gap-3">
        <div class="border py-3 rounded-2xl w-full sm:mx-0 mx-auto mt-6 sm:mt-0">
          <img class="w-6 h-6 mx-auto" src="https://img.icons8.com/ios-filled/50/FFFFFF/prize.png" alt="">
          <h1 class="font-bold text-center">Experience</h1>
          <p class="text-center">1 year</p>
          <p class="text-center">Frontend Development</p>
        </div>

        <div class="border py-3 rounded-2xl w-full sm:mx-0 mx-auto m-6 sm:my-0">
          <img class="w-6 h-6 mx-auto" src="https://img.icons8.com/windows/32/FFFFFF/conference-call.png" alt="">
          <h1 class="font-bold text-center">Education</h1>
          <p class="text-center">Domdomingos Warri</p>
          <p class="text-center">Teqpace Lagos</p>
        </div>
      </div>
      <p class="sm:mx-0 mx-auto w-full">My name is Tetebe Jeffrey, i have 1 year experience of Frontend Development. I'm from Warri Delta State, but currently base in Lagos Nigeria, I schooled at Domdomingos college warri, and I'm currently studing programming at Teqpace Lagos</p>

    </div> 
  </div>
</div>
