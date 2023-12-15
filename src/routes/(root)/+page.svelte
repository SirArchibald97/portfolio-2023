<script>
    import ArrowRight from "../../svgs/ArrowRight.svelte";
    import Link from "../../components/Link.svelte";
    import Tag from "../../components/Tag.svelte";
    import Social from "../../components/Social.svelte";
    import { projects } from "../../projects.json";
    import { socials } from "../../socials.json";

    function age() {
        const birthday = new Date(2003, 6, 23);
        const today = new Date();
        let age = today.getFullYear() - birthday.getFullYear();
        const m = today.getMonth() - birthday.getMonth();
        if (m < 0 || (m === 0 && today.getDate() < birthday.getDate())) age--;
        return age;
    }

    export let isRoot = true;
</script>

<head>
    <title>SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
</head>

<div>
    <!-- About Me -->
    <div id="aboutme">
        <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">👋 Hi, I'm Archie!</h1>
        <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
            I'm a {age()} year old developer and designer from the UK, and I go by SirArchibald online. I am passionate about games design and looking to enter a career in the industry, so 
            I created this website to showcase some of my own work, teams I have been a part of, as well as other info about me!
        </p>
        <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4">
            I have 8 years experience with programming and mostly develop for Minecraft and the web. I'm currently studying an undergraduate degree in software engineering, where I am 
            in my third and final year.
        </p>
        <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4">
            In my spare time, I enjoy playing video games, reading fantasy novels and swimming! I am also a moderator for <Link href="https://mccisland.net" text="MCC Island" />, a 
            Minecraft server created by Noxcrew.
        </p>
    </div>

    <hr class="mt-8 mb-6" />

    <!-- Projects -->
    <div id="projects">
        <h1 class="dark:text-slate-50 text-4xl font-bold mt-4">📂 Projects I've worked on!</h1>
        <div class="flex flex-col mt-6">
            {#each projects as project}
                <div class="flex flex-row">
                    <div class="flex flex-col items-center sm:items-start sm:flex-row dark:bg-slate-800 bg-slate-300 rounded-l dark:text-slate-50 text-black my-3 p-2 mx-0">
                        <img src="/images/{project.image}" class="w-32 h-32 rounded-md" alt="{project.name} Logo" />
                        <div class="flex flex-col">
                            <div class="flex flex-col sm:flex-row items-center">
                                <a href={project.link} target="_blank"><p class={`sm:pl-4 sm:pr-2 text-xl font-semibold ${project.link ? "underline text-blue-500" : ""}`}>{project.name}</p></a>
                                <div class="my-2 sm:my-0">
                                    {#each project.tags as tag}
                                        <Tag label={tag} />
                                    {/each}
                                </div>
                            </div>
                            <p class="pl-4 pt-2 pr-2 text-sm">{project.description}</p>
                        </div>
                    </div>
                    <a href="{project.page ? project.page : ""}" on:click={() => { isRoot = !isRoot }} class="dark:bg-slate-700 bg-slate-200 my-3 p-3 rounded-r flex flex-col justify-center hover:duration-100 hover:scale-110 ease-in-out">
                        <ArrowRight />
                    </a>
                </div>
            {/each}
        </div>
    </div>

    <hr class="mt-8 mb-4" />

    <!-- Socials -->
    <div id="socials">
        <h1 class="dark:text-slate-50 text-4xl font-bold mt-4 mb-8">📷 Find me online!</h1>
        <div class="grid grid-cols-2 sm:flex sm:flex-row items-center justify-center">
            {#each socials as social}
            <a href={social.url}>
                <Social social={social} />
            </a>
            {/each}
        </div>
    </div>

    <hr class="mt-10 mb-4" />

    <!-- Footer -->
    <div class="my-6">
        <p class="text-slate-500">© 2023 SirArchibald</p>
    </div>
</div>