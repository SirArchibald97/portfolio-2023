<script>
    import Link from "$lib/components/Link.svelte";
    import Tag from "$lib/components/Tag.svelte";
    import Bullets from "$lib/components/Bullets.svelte";
    import Image from "$lib/components/Image.svelte";
    import ChevronRight from "$lib/svgs/ChevronRight.svelte";
    import ChevronDown from "$lib/svgs/ChevronDown.svelte";
    import { projects } from "$lib/projects.json";
    const project = projects[2];

    let screenshotCollapsed = true;
    function toggleScreenshot() { screenshotCollapsed = !screenshotCollapsed; }
</script>

<head>
    <title>Pushback | SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
    <meta name="description" content="This page is under construction!">
</head>

<div class="h-screen">
    <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">🎮 Pushback</h1>
    <div class="flex flex-col sm:flex-row">
        <div>
            {#each project.tags as tag}
                <Tag label={tag} />
            {/each}
        </div>
        <div>
            <!-- LINKS GO HERE -->
        </div>
    </div>

    <!-- ABOUT -->
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        This page is under construction.
    </p>
</div>