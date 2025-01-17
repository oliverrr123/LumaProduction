<script lang="ts">
    import { onMount } from 'svelte';

    let scroll = 0;

    const testimonials = [
        {
            name: 'Mark Steiner',
            role: 'Music video',
            testimony: "WOW!!! OLIVER… I am TRULY impressed with the music video. Not only with your ability to conceive and direct, but also to film and to EDIT. I love the fact that you pay such close attention to detail, especially in terms of lip sync and music instrument sync. (I know several “professional” filmmakers who do not possess half of your abilities and skills. I'm honestly amazed. You are a remarkable young man, full of talent."
        },
        {
            name: 'Dwiger automotive',
            role: 'Car photos, marketing videos, car edits',
            testimony: "Man! Cool\nI really like it\nWe should do all the videos like that\nThat's what I want!!!\nVery nice\nI am happy\nLet's film a lot!!!!"
        },
        {
            name: 'Realyx',
            role: 'Marketing videos',
            testimony: "Právě jsi se stal prvním člověkem, u kterého nemusím nic reklamovat, předělávat a hned první verze je dokonalá. Good job. 👏"
        }
    ]

    const recentWork = [
        {
            title: 'Lamborghini Huracan Evo Edit for Dwiger Automotive',
            link: 'https://www.instagram.com/p/DCJpYVqoWQY/'
        },
        {
            title: 'Marketing Video for Realyx',
            link: 'https://www.instagram.com/p/DCmEmRXAgIK/'
        },
        {
            title: 'Music Video for Mark Steiner',
            link: 'https://youtu.be/kXm4Nvl2DYw?si=JstOUSapeI3jxjUz'
        },
        {
            title: 'Porsche Cayenne Polishing Edit for Dwiger Automotive',
            link: 'https://www.instagram.com/reel/DAlrmHkIp59/'
        },
        {
            title: 'Brabus G900 Edit for Dwiger Automotive',
            link: 'https://www.instagram.com/reel/DAQ9SmXowg3/'
        },
        {
            title: 'RollsRoyce PDR Marketing Video and Edit for Dwiger Automotive',
            link: 'https://www.instagram.com/reel/C_TNntVo3un/'
        }
    ]

    let opacity: number = 100;

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

        let a = window.scrollY;

        console.log(a);

        if (a > 5) {
            console.log("yes")
            opacity = 0;
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
        
        // let canScroll = true;
        
        window.addEventListener('scroll', () => {
            scroll = window.scrollY;

            if (scroll < 10) {
                opacity = 100;
            }
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
                if (scroll > 5) {
                    whiteCircle.style.opacity = '1'; // Show the white circle
                } else {
                    whiteCircle.style.opacity = '0'; // Hide the white circle
                }
            }

            if (about && about1 && about2 && about3 && scroll > 10) {
                // if (canScroll) {
                //     window.scrollBy({top: 500, behavior: 'smooth'});
                //     canScroll = false;
                // }
                opacity = 0;
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
        });

        
    });

    function smoothScroll() {
        let scrollBy = 3000;
        const intervalId = setInterval(() => {
            window.scrollBy({top: scrollBy, behavior: 'smooth'});
            scrollBy = scrollBy * 0.9;

            if (scrollBy < 0.01) {
                clearInterval(intervalId);
            }
        }, 10);
    }
</script>

<svelte:head>
    <title>Luma Production</title>
</svelte:head>

<main class="font-['Montaga'] relative">
    <div id="whiteCircle" class="fixed inset-0 bg-white opacity-0 -z-10"></div> <!-- White circle element -->
    <section class="absolute top-0 w-full z-50" style="opacity: {opacity}; transition: opacity 1s;">
        <div class="flex flex-col items-center justify-center min-h-[100vh] text-7xl lg:text-8xl gap-y-2">
            <h1 id="luma" class="font-['Montserrat'] opacity-0 translate-y-10 font-black">Luma.</h1>
            <p id="description" class="text-base ">your Media Production Agency</p>
        </div>
        <button id="scrollTxt" class="absolute bottom-10 w-full text-center justify-center text-xs" on:click={smoothScroll}>
            scroll to begin
        </button>
    </section>
    <section id="about" class="flex flex-col justify-around gap-16 m-5 relative pt-96 lg:pt-[36rem] mb-32 text-[#1E1E1E] opacity-0 items-center text-center text-xl sm:px-10 sm:text-2xl">
        <p id="about1" class="translate-y-10">No matter your project size, budget or requirements, we will always do our best to bring your vision to reality.</p>
        <p id="about2" class="translate-y-10">We will provide a solution for all your photo, video or visual projects.</p>
        <p id="about3" class="translate-y-10">Whether it's a commercial car photoshoot, music video, marketing ad, animation or anything else, we've got you covered.</p>
    </section>
    <section class="flex flex-col items-center justify-around gap-16 p-8 my-10 py-16 text-white bg-[#1E1E1E]">
        <h2 class="text-4xl mb-0 px-2 text-center">What our clients say about us:</h2>
        <div class="grid grid-cols-1 md:grid-cols-7 md:grid-rows-2 justify-items-center gap-8 font-['Montserrat'] sm:w-9/12 md:w-10/12 lg:w-8/12 xl:w-6/12 2xl:w-5/12">
            <!-- {#each testimonials as testimonial} -->
                <div class="col-span-1 md:col-span-7 row-span-2 bg-[#3a3a3a] rounded-xl h-[100%]">
                    <div class="flex items-center bg-[rgb(42,42,42)] p-5 rounded-t-xl">
                        <img class="" src="images/{testimonials[0].name}.png" alt="Client testimonial">
                        <div class="ml-5 text-white">
                            <h3 class=" text-xl opacity-90">{testimonials[0].name}</h3>
                            <h4 class=" text-sm opacity-50">{testimonials[0].role}</h4>
                        </div>
                    </div>
                    <p class="my-4 mx-7 opacity-75">{testimonials[0].testimony}</p>
                </div>
                <div class="col-span-1 md:col-span-4 w-full bg-[#3a3a3a] rounded-xl h-[100%]">
                    <div class="flex items-center bg-[rgb(42,42,42)] p-5 rounded-t-xl">
                        <img class="" src="images/{testimonials[1].name}.png" alt="Client testimonial">
                        <div class="ml-5 text-white">
                            <h3 class=" text-xl opacity-90">{testimonials[1].name}</h3>
                            <h4 class=" text-sm opacity-50">{testimonials[1].role}</h4>
                        </div>
                    </div>
                    <p class="my-4 mx-7 opacity-75 whitespace-pre-wrap">{testimonials[1].testimony}</p>
                </div>
                <div class="col-span-1 md:col-span-3 bg-[#3a3a3a] rounded-xl h-[100%]">
                    <div class="flex items-center bg-[rgb(42,42,42)] p-5 rounded-t-xl">
                        <img class="" src="images/{testimonials[2].name}.png" alt="Client testimonial">
                        <div class="ml-5 text-white">
                            <h3 class=" text-xl opacity-90">{testimonials[2].name}</h3>
                            <h4 class=" text-sm opacity-50">{testimonials[2].role}</h4>
                        </div>
                    </div>
                    <p class="my-4 mx-7 opacity-75">{testimonials[2].testimony}</p>
                </div>
            <!-- {/each} -->
        </div>
    </section>
    <section>
        <h1 class="text-3xl text-center text-[#1E1E1E] mb-10">Our recent work:</h1>
        <div class="grid grid-cols-2 md:grid-cols-3 xl:grid-cols-6 pb-6 place-items-center place-self-center place-content-center">
            {#each recentWork as recentWorkItem}
                <a title={recentWorkItem.title} href={recentWorkItem.link} target="_blank">
                    <img src="images/ourwork/{recentWorkItem.title}.jpg" alt="Video Thumbnail - {recentWorkItem.title}" class="opacity-80 w-36 hover:opacity-100 rounded-md transition-all duration-700 filter grayscale hover:filter-none m-2" style="box-shadow: 0 0 50px rgba(0, 0, 0, 0.5)">
                </a>
            {/each}
        </div>
        <p class="text-center text-[#1E1E1E] opacity-50 pb-10">More will be shown soon...</p>
    </section>
    <section class="bg-[#1E1E1E] flex flex-col items-center justify-center py-20 gap-10 pb-16">
        <h1 class="text-3xl text-center text-white px-5" style="text-shadow: 0 0 40px rgba(255, 255, 255, 0.25), 0 0 75px rgba(255, 255, 255, 0.55)">Bring your vision to reality:</h1>
        <a href="/contact"><button class="text-[#1E1E1E] bg-white px-10 py-2 rounded-full text-2xl transition-color duration-200 hover:bg-[#E0E0E0]">Contact</button></a>
        <!-- <svg width="65" height="44" viewBox="0 0 65 44" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M64 42.5C51 45.5 38.6 40 35 35.5C19.5 16.125 39.5 17.5 43 22.5C50.2197 32.8139 33 36.5 19.5 27.5C9.16113 20.6074 3.16667 6.33333 2.5 1M2.5 1L1 17.5M2.5 1L15 9.5" stroke="black"/>
        </svg> -->
    </section>
    <footer class="bg-[#1E1E1E]">
        <div class="flex justify-center text-xs text-white p-7 opacity-50">
            © 2024 Luma production
        </div>
        <div class="flex justify-center text-xs text-white p-7 opacity-30">
            <a target="_blank" href="https://www.youtube.com/@luma.production"><img src="icons/youtube.svg" alt="Youtube" class="w-5 h-5 mx-2 filter invert"></a>
            <!-- <a target="_blank" href="https://www.facebook.com/luma.prod/"><img src="icons/facebook.svg" alt="Facebook" class="w-5 h-5 mx-2 filter invert"></a> -->
            <a target="_blank" href="https://www.instagram.com/luma.production_"><img src="icons/instagram.svg" alt="Instagram" class="w-5 h-5 mx-2 filter invert"></a>
            <a target="_blank" href="https://www.linkedin.com/company/lumaprod/"><img src="icons/linkedin.svg" alt="LinkedIn" class="w-5 h-5 mx-2 filter invert"></a>
            <!-- <a target="_blank" href="https://www.tiktok.com/@luma.producti0n"><img src="icons/tiktok.svg" alt="TikTok" class="w-5 h-5 mx-2 filter invert"></a> -->
            <a target="_blank" href="mailto:hello@luma-production.com"><img src="icons/mail.svg" alt="Mail" class="w-5 h-5 mx-2 filter invert"></a>
            <a target="_blank" href="tel:+420776781248"><img src="icons/phone.svg" alt="Phone" class="w-5 h-5 mx-2 filter invert"></a>
            <!-- <a target="_blank" href="https://www.google.com/"><img src="icons/twitter-x.svg" alt="Twitter | X" class="w-5 h-5 mx-2"></a> -->
        </div>
    </footer>
</main>

