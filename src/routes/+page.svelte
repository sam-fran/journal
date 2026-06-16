<script>
    import { onMount } from "svelte";

    let entriesArray = $state([]);

    onMount(() => {
        const entries = localStorage.getItem("entries");
        entriesArray = entries ? JSON.parse(entries) : [];
    });
</script>

<h1 class="text-5xl">Home</h1>
<hr class="pb-4" />
{#if entriesArray.length > 0}
    <h2 class="text-4xl">Entries</h2>
{:else}
    <h2 class="text-3xl">No Entries Yet. Write Some!</h2>
{/if}
<ul>
    {#each entriesArray as entry}
        <li
            class="rounded-2xl mt-10 bg-gray-200 dark:bg-gray-800 dark:text-amber-100 p-7 text-xl w-full"
        >
            {entry}
        </li>
    {/each}
</ul>
