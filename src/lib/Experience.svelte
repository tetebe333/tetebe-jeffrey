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
<p class=" p-0 m-0">.</p>

<div class=" text-gray-300 border-t border-black mb-5">
  <p class="text-center mt-8">Explore my</p>
  <h1 class="font-bold text-2xl text-gray-300 text-center">Experience</h1>

  <div class="font-mybold text-gray-300 sm:grid-cols-2 grid-cols-1 grid gap-4  mt-6">
    <div class="border-2 rounded-2xl  w-full p-5">
      <h2 class="text-center">programming Laguage</h2>

      <div class="mt-4 grid-cols-2 grid gap-4">
          <div >  

            <div class="flex items-center gap-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">HTML</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center ">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">CSS</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>
          </div>

          <div>
            <div class="flex items-center gap-3 mt-0 sm:mt-0 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">JavaScript</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">TypeScript</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>
          </div>
      </div>
    </div>

    <div class="border-2 sm:mt-0 rounded-2xl w-full mt-5 p-5">
      <h2 class="text-center">Framework & Libry</h2>

      
      <div class="mt-4 grid-cols-2 grid gap-4">
          <div >

            <div class="flex items-center gap-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Svelte</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center ">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Svelte-Kit</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center ">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Vue.js</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center ">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">React</h1>
                <p class="text-xs">Intermediate</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Github</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>


            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Node.js</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>
      
          </div>

          <div>
            <div class="flex items-center gap-3 mt-0 sm:mt-0 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Tailwind css</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Bootstrap</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Sass</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Node.js</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">Git</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>

            <div class="flex items-center gap-3 mt-3 justify-center">
              <img class="w-3 h-3" src="https://img.icons8.com/ios-glyphs/30/FFFFFF/verified-account--v1.png" alt="">
              <div>
                <h1 class="font-bold text-sm">NPM</h1>
                <p class="text-xs">Experienced</p>
              </div>
            </div>
            
          </div>
        </div>
      </div>
  </div>  
</div>
</div>