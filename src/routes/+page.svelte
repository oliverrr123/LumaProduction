<script lang="ts">
    import { onMount } from 'svelte';

    let scroll = 0;

    onMount(() => {
        const luma = document.getElementById('luma');
        const description = document.getElementById('description');
        const scrollTxt = document.getElementById('scrollTxt');
        const whiteCircle = document.getElementById('whiteCircle');
        const about = document.getElementById('about');

        if (luma) {
            luma.style.textShadow = '0 0 20px rgba(255, 255, 255, 0.25), 0 0 200px rgba(255, 255, 255, 0.5)';
            luma.style.transition = 'opacity 2s ease-in-out, transform 2s ease-in-out';
            luma.style.opacity = '1';
            luma.style.transform = 'translateY(0)';
        }
        if (description) {
            const text = "your Media Production Agency";
            description.style.opacity = '0';
            let index = 2;
            // Add a 1-second delay before starting the text animation
            setTimeout(() => {
                description.textContent = 'yo';
                description.style.opacity = '1';
                const interval = setInterval(() => {
                    if (Math.random() > 0.33) {
                        description.textContent += text[index];
                        index++;
                        if (index === text.length) {
                            clearInterval(interval);
                        }
                    }
                }, 25);
            }, 1500);
        }
        if (scrollTxt) {
            scrollTxt.style.opacity = '0';
            setTimeout(() => {
                scrollTxt.style.transition = "opacity 1s ease-in-out";
                scrollTxt.style.opacity = '0.66';
            }, 2500);
        }
        
        
        window.addEventListener('scroll', () => {
            scroll = window.scrollY;
            if (scrollTxt && scroll > 10) {
                scrollTxt.style.opacity = '0';
            }
            else if (scrollTxt) {
                scrollTxt.style.transition = "opacity 250ms ease-in-out";
                scrollTxt.style.opacity = '0.66';
            }
            
            // Animate the white circle based on scroll position
            if (whiteCircle) {
                whiteCircle.style.transition = 'opacity 333ms ease-in-out';
                if (scroll > 100) {
                    whiteCircle.style.opacity = '1'; // Show the white circle
                } else {
                    whiteCircle.style.opacity = '0'; // Hide the white circle
                }
            }

            if (about && scroll > 100) {
                about.style.transition = 'opacity 1s ease-in-out';
                about.style.opacity = '1';
            }
        });

    });
</script>

<main class="font-['Montaga']">
    <div id="whiteCircle" class="fixed inset-0 bg-white opacity-0 -z-10"></div> <!-- White circle element -->
    <div class="flex flex-col items-center justify-center min-h-[100vh] text-8xl gap-y-2">
        <h1 id="luma" class="font-['Montserrat'] opacity-0 translate-y-10 font-black">Luma.</h1>
        <p id="description" class="text-base ">your Media Production Agency</p>
    </div>
    <p id="scrollTxt" class="absolute bottom-10 w-full text-center justify-center text-xs">
        scroll to begin
    </p>
    <div id="about" class="flex flex-col items-center justify-around gap-16 m-5 text-[#1E1E1E] opacity-0">
        <p>No matter your project size, budget or requirements, we will always do our best to bring your vision to reality.</p>
        <p>We will provide a solution for all your photo, video or visual projects.</p>
        <p>Whether it's a commercial car photoshoot, music video, marketing ad, animation or anything else, we've got you covered.</p>
    </div>
    <div class="flex flex-col items-center justify-around gap-16 p-4 my-16 py-16 text-white bg-[#1E1E1E]">
        <h2 class="text-4xl mb-0 px-2 text-center">What our clients say about us:</h2>
        <div class="flex flex-col gap-8">
            <div class="flex flex-col p-2">
                <div class="flex items-center bg-[#333333] p-5 rounded-xl">
                    <img class="" src="images/Dwiger.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">Dwiger automotive</h3>
                        <h4 class=" text-sm opacity-50">Car photoshoots, marketing videos, car edits</h4>
                    </div>
                </div>
                <p class="mt-5 opacity-75 mx-3">
                    Man! Cool<br>
                    I really like it<br>
                    We should do all the videos like that<br>
                    That's what I want!!!<br>
                    Very nice<br>
                    I am happy<br>
                    Let's film a lot!!!!<br>
                </p>
            </div>
            <div class="flex flex-col p-2">
                <div class="flex items-center bg-[#333333] p-5 rounded-xl">
                    <img class="" src="images/Mark.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">Mark Steiner</h3>
                        <h4 class=" text-sm opacity-50">Music video</h4>
                    </div>
                </div>
                <p class="mt-5 opacity-75 mx-3">
                    WOW!!! OLIVER… I am TRULY impressed with the music video. Not only with your ability to conceive and direct, but also to film and to EDIT. I love the fact that you pay such close attention to detail, especially in terms of lip sync and music instrument sync. (I know several “professional” filmmakers who do not possess half of your abilities and skills. I’m honestly amazed. You are a remarkable young man, full of talent.<br>...
                </p>
            </div>
        </div>
    </div>
    <div class=" flex flex-col items-center justify-center py-20 gap-10 mb-16">
        <h1 class="text-3xl text-center text-[#1E1E1E]">Bring your vision to reality:</h1>
        <button class="bg-[#1E1E1E] text-white px-10 py-2 rounded-full text-2xl transition-colors hover:bg-[#3E3E3E]">Contact</button>
    </div>
    <div class="flex justify-center text-xs text-[#1E1E1E] m-7 opacity-50">
        © 2024 Luma production
    </div>
</main>

