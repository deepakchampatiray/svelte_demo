<script>
    let promise;
    function getRandomNumber() {
        return new Promise(function(resolve, reject){
            setTimeout(()=>{
                console.log(`Random ${new Date().getTime()}`);
                resolve(Math.ceil(Math.random()*2000));
            },1000)
        })
    }

    function handleClick() {
        promise = getRandomNumber();
    }
</script>
<button on:click={handleClick}>Generate Random Number</button>
{#await promise}
    <p>Waiting ...</p>
{:then num}
    <p>Random number is : {num}</p>
{/await}