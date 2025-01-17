<script>
    const testimonials = [
        {
            name: 'Mark Steiner',
            role: 'Music video',
            testimony: "WOW!!! OLIVER… I am TRULY impressed with the music video. Not only with your ability to conceive and direct, but also to film and to EDIT. I love the fact that you pay such close attention to detail, especially in terms of lip sync and music instrument sync. (I know several “professional” filmmakers who do not possess half of your abilities and skills. I'm honestly amazed. You are a remarkable young man, full of talent."
        },
        {
            name: 'Dwiger automotive',
            role: 'Car photos, marketing videos, car edits',
            testimony: "Man! Cool<br>I really like it<br>We should do all the videos like that<br>That's what I want!!!<br>Very nice<br>I am happy<br>Let's film a lot!!!!<br>"
        },
        {
            name: 'Realyx',
            role: 'Marketing videos',
            testimony: "Právě jsi se stal prvním člověkem, u kterého nemusím nic reklamovat, předělávat a hned první verze je dokonalá. Good job. 👏"
        }
    ]
</script>

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
                <p class="my-4 mx-7 opacity-75">{@html testimonials[0].testimony}</p>
            </div>
            <div class="col-span-1 md:col-span-4 w-full bg-[#3a3a3a] rounded-xl h-[100%]">
                <div class="flex items-center bg-[rgb(42,42,42)] p-5 rounded-t-xl">
                    <img class="" src="images/{testimonials[1].name}.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">{testimonials[1].name}</h3>
                        <h4 class=" text-sm opacity-50">{testimonials[1].role}</h4>
                    </div>
                </div>
                <p class="my-4 mx-7 opacity-75">{@html testimonials[1].testimony}</p>
            </div>
            <div class="col-span-1 md:col-span-3 bg-[#3a3a3a] rounded-xl h-[100%]">
                <div class="flex items-center bg-[rgb(42,42,42)] p-5 rounded-t-xl">
                    <img class="" src="images/{testimonials[2].name}.png" alt="Client testimonial">
                    <div class="ml-5 text-white">
                        <h3 class=" text-xl opacity-90">{testimonials[2].name}</h3>
                        <h4 class=" text-sm opacity-50">{testimonials[2].role}</h4>
                    </div>
                </div>
                <p class="my-4 mx-7 opacity-75">{@html testimonials[2].testimony}</p>
            </div>
        <!-- {/each} -->
    </div>
</section>