<script>
    import {createEventDispatcher} from 'svelte';

    let dispatch = createEventDispatcher();

    function sayHello(){
        dispatch('message', {
            text: 'Hello World !!'
        });
    }
</script>

<button on:click={sayHello}>Say Hello</button>