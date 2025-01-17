<script>
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
</script>

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