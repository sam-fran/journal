<script>
    function addEntry(){
        const textarea = document.getElementById("entrytext");
        const currentText = textarea.value.trim();
        const existingEntries = localStorage.getItem("entries");
        const entriesArray = existingEntries ? JSON.parse(existingEntries) : [];
        const now = new Date();
        const year = now.getFullYear(); 
        const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
        const month = months[now.getMonth()];
        const day = now.getDay()
        entriesArray.unshift(`${day} ${month} ${year} - ${currentText}`);
        localStorage.setItem("entries", JSON.stringify(entriesArray));
        textarea.value = "";
    }
</script>

<h1 class="text-5xl">New Entry</h1>
<hr class="pb-4">
<textarea id="entrytext" class="rounded-2xl w-full bg-gray-200 dark:bg-gray-700 p-5 h-50 max-h-90 min-h-30"></textarea>
<button onclick={addEntry} class="rounded-2xl bg-blue-200 p-2 text-center w-full hover:bg-blue-300">Save</button>
