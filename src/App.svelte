<script>
  import Counter from './Counter.svelte';
  import Login from './Login.svelte';
  import Cat from './Cat.svelte';
  import RandomNum from './Promise.svelte';
  import Hello from './Event.svelte';

  export let name;
  let imgSrc = "favicon.png";
  let cats = [{name: 'Tom'}, {name: 'James'}, {name: 'Cindy'}];
  setTimeout(()=>{
	  cats = [...cats, {name: 'Mike'}];
  }, 5000);

  function getMessage(msg) {
	  console.log(msg);
	  
  }
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    /* text-transform: uppercase; */
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name.toUpperCase()}!</h1>
  <img src={imgSrc} alt="Favicon" />
  
  <Counter></Counter>
  <hr>
  <Login></Login>
  <hr>
  <ul>
	{#each cats as cat}
		<li>
			<Cat cat={cat}></Cat>
		</li>
	{/each}
  </ul>
  <hr>
  <RandomNum></RandomNum>
  <hr>
  <Hello on:message={getMessage} ></Hello>
</main>
