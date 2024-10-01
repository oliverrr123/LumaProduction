<script lang="ts">
    import { onMount } from 'svelte';

    let scroll = 0;

    onMount(() => {
        const luma = document.getElementById('luma');
        const description = document.getElementById('description');
        const scrollTxt = document.getElementById('scrollTxt');
        const whiteCircle = document.getElementById('whiteCircle');
        const about = document.getElementById('about');
        const about1 = document.getElementById('about1');
        const about2 = document.getElementById('about2');
        const about3 = document.getElementById('about3');
        const arrow = document.getElementById('arrow');
        if (arrow) {
            const pathLength = arrow.clientHeight;

        }
    
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

            if (about && about1 && about2 && about3 && scroll > 100) {
                about.style.transition = 'opacity 1s ease-in-out';
                about.style.opacity = '1';
                about1.style.transition = 'transform 1s ease-in-out';
                about2.style.transition = 'transform 1s ease-in-out';
                about3.style.transition = 'transform 1s ease-in-out';
                about1.style.transform = 'translateY(0)';
                setTimeout(() => {
                    about2.style.transform = 'translateY(0)';
                }, 250);
                setTimeout(() => {
                    about3.style.transform = 'translateY(0)';
                }, 500);
            }

            // // Adjust the path length of the arrow based on scroll position
            // if (arrow) {
            //     let scrollPercentage = (document.getElemen.)
            // }
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
    <div id="about" class="flex flex-col justify-around gap-16 m-5 mb-64 text-[#1E1E1E] opacity-0 items-center text-center lg:text-2xl sm:text-xl ">
        <p id="about1" class="translate-y-10">No matter your project size, budget or requirements, we will always do our best to bring your vision to reality.</p>
        <p id="about2" class="translate-y-10">We will provide a solution for all your photo, video or visual projects.</p>
        <p id="about3" class="translate-y-10">Whether it's a commercial car photoshoot, music video, marketing ad, animation or anything else, we've got you covered.</p>
    </div>
    <div class="flex flex-col items-center justify-around gap-16 p-4 my-16 py-16 text-white bg-[#1E1E1E]">
        <h2 class="text-4xl mb-0 px-2 text-center">What our clients say about us:</h2>
        <div class="flex flex-col md:flex-row gap-8 lg:w-2/3">
            <div class="flex flex-col md:w-1/2 bg-[#3a3a3a] rounded-xl">
                <div class="flex items-center bg-[#2a2a2a] p-5 rounded-t-xl">
                    <img class="" src="images/Dwiger.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">Dwiger automotive</h3>
                        <h4 class=" text-sm opacity-50">Car photoshoots, marketing videos, car edits</h4>
                    </div>
                </div>
                <p class="my-4 mx-7 opacity-75 font-['Montserrat'] italic">
                    Man! Cool<br>
                    I really like it<br>
                    We should do all the videos like that<br>
                    That's what I want!!!<br>
                    Very nice<br>
                    I am happy<br>
                    Let's film a lot!!!!<br>
                </p>
            </div>
            <div class="flex flex-col md:w-1/2 bg-[#3a3a3a] rounded-xl">
                <div class="flex items-center bg-[#2a2a2a] p-5 rounded-t-xl">
                    <img class="" src="images/Mark.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">Mark Steiner</h3>
                        <h4 class=" text-sm opacity-50">Music video</h4>
                    </div>
                </div>
                <p class="my-4 mx-7 opacity-75 font-['Montserrat'] italic">
                    WOW!!! OLIVER… I am TRULY impressed with the music video. Not only with your ability to conceive and direct, but also to film and to EDIT. I love the fact that you pay such close attention to detail, especially in terms of lip sync and music instrument sync. (I know several “professional” filmmakers who do not possess half of your abilities and skills. I’m honestly amazed. You are a remarkable young man, full of talent.
                </p>
            </div>
        </div>
    </div>
    <div class=" flex flex-col items-center justify-center py-20 gap-10 mb-16">
        <h1 class="text-3xl text-center text-[#1E1E1E]">Bring your vision to reality:</h1>
        <a href="/contact"><button class="bg-[#1E1E1E] text-white px-10 py-2 rounded-full text-2xl transition-colors hover:bg-[#3E3E3E]">Contact</button></a>
        <!-- <svg width="65" height="44" viewBox="0 0 65 44" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M64 42.5C51 45.5 38.6 40 35 35.5C19.5 16.125 39.5 17.5 43 22.5C50.2197 32.8139 33 36.5 19.5 27.5C9.16113 20.6074 3.16667 6.33333 2.5 1M2.5 1L1 17.5M2.5 1L15 9.5" stroke="black"/>
        </svg> -->
            
    </div>
    <div class="flex justify-center text-xs text-[#1E1E1E] m-7 opacity-50">
        © 2024 Luma production
    </div>
    <div class="flex justify-center text-xs text-[#1E1E1E] m-7 opacity-30">
        <a target="_blank" href="https://www.youtube.com/@luma.production"><img src="icons/youtube.svg" alt="Youtube" class="w-5 h-5 mx-2"></a>
        <a target="_blank" href="https://www.facebook.com/luma.prod/"><img src="icons/facebook.svg" alt="Facebook" class="w-5 h-5 mx-2"></a>
        <a target="_blank" href="https://www.instagram.com/luma.production_"><img src="icons/instagram.svg" alt="Instagram" class="w-5 h-5 mx-2"></a>
        <a target="_blank" href="https://www.tiktok.com/@luma.producti0n"><img src="icons/tiktok.svg" alt="TikTok" class="w-5 h-5 mx-2"></a>
        <a target="_blank" href="mailto:hello@luma-production.com"><img src="icons/mail.svg" alt="Mail" class="w-5 h-5 mx-2"></a>
        <a target="_blank" href="tel:+420776781248"><img src="icons/phone.svg" alt="Phone" class="w-5 h-5 mx-2"></a>
        <!-- <a target="_blank" href="https://www.google.com/"><img src="icons/twitter-x.svg" alt="Twitter | X" class="w-5 h-5 mx-2"></a> -->
        <!-- <a target="_blank" href="https://www.google.com/"><img src="icons/linkedin.svg" alt="LinkedIn" class="w-5 h-5 mx-2"></a> -->
    </div>
</main>

