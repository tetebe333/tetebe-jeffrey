 <script lang="ts">
    import About from "../lib/About.svelte";
    import Information from "../lib/Information.svelte";
    import Experience from "../lib/Experience.svelte";
    import Projects from "../lib/Projects.svelte";
    import Contact from "../lib/Contact.svelte";
    import Foolter from "../lib/Foolter.svelte";

    import { fly, fade } from 'svelte/transition';
    import { cubicOut, cubicIn } from 'svelte/easing';

    let menustate= $state(true)

    function menuFunction() {
        menustate = !menustate
    }

 </script>
<main class="font-sans">

    <!-- Profile Section -->
    <div class="bg-gryOO py-5">
        <div class="flex justify-between text-gray-300 font-mybold w-80% max-w-800 mx-auto">
            <h1 class="sm:text-lg  font-bold text-2xl">
                Tetebe Jeffrey
            </h1>
            <div class="gap-4 text-sm hidden sm:flex">
                <a href="#about">About</a>
                <a href="#experience">Experience</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
            </div>

            {#if menustate}
                <button  onclick={menuFunction} class="block sm:hidden">
                    <img width="30" height="30" src="https://img.icons8.com/ios-filled/50/FFFFFF/menu--v6.png" alt=""> 
                </button>
            {:else} 
            <button onclick={menuFunction} class="" >
                <img width="40" height="40" src="https://img.icons8.com/ios-filled/50/FFFFFF/cancel.png" alt="">
            </button> 
                
            {/if}    
        </div>
    </div>

        {#if !menustate}
        <div class="absolute z-999 top-17.5 w-full flex justify-center sm:hidden bg-gryO" transition:fly={{ x: 100, duration: 800, easing: cubicOut }} >
            <div class="flex flex-col gap-5 p-5 text-gray-300 font-mybold rounded-xl ">
        
                <a onclick={menuFunction} href="#about">About</a>
                <a onclick={menuFunction} href="#experience">Experience</a>
                <a onclick={menuFunction} href="#projects">Projects</a>
                <a onclick={menuFunction} href="#contact">Contact</a>        
            </div>
        </div>
        {/if} 

    <!-- About Section -->
    <div class="bg-white-o py-7">
        <About />
    </div>


    <!-- Information Section -->
    <div class="w-80% max-w-800 mx-auto" id="about">
        <Information />
    </div>
    
    <!-- Experience Section -->
        
    <div class="w-80% max-w-800 mx-auto" id="experience">
        <Experience />
    </div>
    

    <!-- Projects Section -->
    <div class="" id="projects">
        <Projects />
    </div>

    <!-- Contact Section -->
    <div id="contact">
        <Contact />
    </div>

    <!-- Foolter Section -->
    <div class="w-80% max-w-800 mx-auto text-gray-300">
        <Foolter />
    </div>
</main>
