<script>
    let loggedIn = false;
    function toggle(){
        loggedIn = !loggedIn;
    }
</script>

{#if loggedIn}
    <button on:click={toggle}>Logout</button>
{:else}
    <button on:click={toggle}>Login</button>
{/if}