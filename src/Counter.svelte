<script>
    let count = 0;

    function increment() {
        count++;
    }
</script>

<hr>
<button on:click={increment}>
    Clicked {count} {count > 1?'times':'time'}
</button>