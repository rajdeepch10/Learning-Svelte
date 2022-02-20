<script>
  import MyComponent from "./MyComponent.svelte";
  export let name;
  let displayWarning = false;
  const props = {
    name: "Rajdeep",
    address: "Hyderabad",
    counter: 0,
  };
  let setCounter = (e) => {
    if (!isNaN(e.target.value) && e.target.value.length > 0) {
      console.log("Number");
      props.counter = parseInt(e.target.value);
      displayWarning = false;
    } else if (e.target.value.length === 0) {
      console.log("Not Number");
      props.counter = 0;
      displayWarning = false;
    } else {
      props.counter = 0;
      displayWarning = true;
    }
  };
</script>

<main>
  <h1>Hello {name}!</h1>
  <p>Enter Initial Count below:</p>
  <input type="text" name="" on:input={(e) => setCounter(e)} />
  <p
    id="warningMessage"
    style={displayWarning ? "display:block" : "display:none"}
  >
    Enter valid number
  </p>
  <MyComponent {...props} />
</main>

<style>
  #warningMessage {
    color: red;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
