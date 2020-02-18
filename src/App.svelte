<script>
  import ContactCard from "./ContactCard.svelte"; // PascalCase is important to svelte
  let name = "Thomas";
  let age = 22;

  let job = "Web Developer";
  let description = "Full-stack engineer";
  let image = "";

  // rerun this whenever name changes
  $: uppercaseName = name.toUpperCase(); // whenever the application reloads it will always make name uppercase even if it changes

  $: console.log();

  function incrementAge() {
    age += 1;
  }

  function changeName() {
    name = "Thomas Nelson";
  }

  function inputChange(e) {
    const enteredValue = event.target.value; // when a value is entered, it triggers and event, and this function runs, creating a variable of the current value of the input and setting name to that
    name = enteredValue;
  }
</script>

<style>
  h1 {
    color: purple; /* this styling will only affect THIS component, so using h1 wont affect h1's in other components */
  }
</style>

<h1>My name is {uppercaseName}, I am {age} years old!</h1>
<button type="submit" on:click={incrementAge}>Increment</button>
<!-- <button type="submit" on:click={changeName}>Fullname</button> -->
<!-- <input type="text" on:input={inputChange} value={name} id="" /> -->
<!-- forceful two-way connection {value and name will always be the same} -->
<div>
  <input type="text" bind:value={name} />
  <input type="text" bind:value={job} />
  <textarea rows="3" type="text" bind:value={desc} />
</div>

<ContactCard {name} {job} {description} {image} />
