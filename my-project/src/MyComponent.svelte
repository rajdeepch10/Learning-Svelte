<script>
  export let name;
  export let address;
  export let counter;

  function incrementCounter() {
    counter++;
  }
  function decrementCounter() {
    counter--;
  }
</script>

<p>My name is {name} and I live in {address}</p>
<button on:click={incrementCounter}>Increment Counter</button>
<button on:click={decrementCounter}>Decrement Counter</button>
<p>{counter}</p>

<style>
  button {
    color: blueviolet;
    height: 60px;
    width: 100px;
  }
</style>
