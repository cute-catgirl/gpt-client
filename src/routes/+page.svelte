<script>
    import Message from "../lib/message.svelte";
    const placeholders = [
        "What's on your mind?",
        "Ask me anything..."
    ]
    let message = "";
    let messages = [];

    function addMessage() {
        if (message !== "") {
            messages = [...messages, message];
            message = "";
        }
    }
</script>

<main class="h-screen bg-slate-950 select-none flex justify-center">
    <div id="content" class="h-full flex flex-col justify-between w-3/6">
        <div id="messages" class="flex flex-col gap-2 p-4">
            {#each messages as message}
                <Message message={message}/>
            {/each}
        </div>
        <div id="message-input" class="flex items-stretch p-4 gap-2">
            <input bind:value={message} type="text" class="rounded shadow-inner text-slate-800 bg-slate-200 grow w-full p-2 outline-none placeholder:text-slate-600 placeholder:italic" placeholder={placeholders[Math.floor(Math.random() * placeholders.length)]}/>
            <button on:click={addMessage} class="rounded shadow-inner text-slate-800 bg-emerald-300 aspect-square"><i class="fa-solid fa-arrow-up"></i></button>
        </div>
    </div>
</main>