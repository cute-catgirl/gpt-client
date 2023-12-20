<script>
    export let message;

    function copyMessage() {
        navigator.clipboard.writeText(message);
    }
</script>

<div class="rounded text-slate-100 mb-2">
    <h1 class="font-bold">You</h1>
    <p>{message}</p>
    <button on:click={copyMessage} class="transition-colors text-slate-200 hover:text-slate-50"><i class="fa-solid fa-copy"></i></button>
</div>