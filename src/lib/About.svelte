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
  class="transition-all duration-700"
>

<div class=" mt-30  sm:flex justify-center items-center gap-10 text-gray-300">
    <div class="flex justify-center sm:block">
      <img class="w-60 h-60 rounded-full" src="https://media.licdn.com/dms/image/v2/D4D03AQGbRKYFPNxuLg/profile-displayphoto-crop_800_800/B4DZmlOAnXKQAM-/0/1759413540107?e=1766016000&v=beta&t=2JnJsVy6YGDFveaEDjPk3zyx1CHtWQtrqDU4092Zz_I" alt="my phyto">
    </div>

    <div class="text-center mt-6 sm:mt-0">
        <p class="font-mybold text-xs">Hello I'm</p>
        <h1 class="font-bold text-2xl text-gray-300">Tetebe Jeffrey</h1>
        
        <div class="flex justify-center">
          <p class="font-mybold text-lg w-45"><span class="inline-block overflow-hidden whitespace-nowrap border-r-3 bordertext-gray-300 animate-[typing_3s_steps(18,end)_infinite_alternate]">Frontend Developer</span><span class="animate-[blink_3s_step-end_infinite] h-full"></span></p>
        </div>

        <div class="mt-3 flex gap-2 justify-center ">
            <div class="transform hover:scale-112 transition ease-out duration-300">
              <a class="btn bg-black text-gray-300 border-none  hover:duration-400 hover:ease-in" href="https://wa.me/2349164041789?text=Hi Jeff I saw you Portfolio Website, and I wanted to discuss with you" target="_blank">
                <img class="inline mb-1 h-5" src="https://img.icons8.com/ios-glyphs/30/40C057/whatsapp.png" alt="">
                WhatsApp</a>
            </div>

            <div class="transform hover:scale-112 transition ease-out duration-300">
              <a class="btn bg-black text-gray-300 border-none  hover:duration-400 hover:ease-in" href="#contact">
                <img class="inline mb-1 me-0.2 h-4" src="https://img.icons8.com/forma-thin-filled-sharp/24/228BE6/contact-card.png" alt="">
                Contact info</a>
            </div>
        </div>

        <div class="flex gap-5 mt-5 justify-center animate-bounce">
            <a href="https://www.linkedin.com/in/tetebe-jeffrey-974b2a284/" target="_blank">
                <img class="w-7 h-7 rounded-full" src="https://img.icons8.com/ios-glyphs/30/1A1A1A/linkedin.png" alt="">
            </a>

            <a href="https://github.com/tetebe333" target="_blank">
                <img class="w-7 h-7 rounded-full" src="https://img.icons8.com/ios-filled/50/1A1A1A/github.png" alt="github">
            </a>
        </div>
    </div>
</div>
</div>


