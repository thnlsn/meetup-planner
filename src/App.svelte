<script>
  let name = "Thomas";
  let age = 22;

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
    color: purple;
  }
</style>

<h1>My name is {uppercaseName}, I am {age} years old!</h1>
<button type="submit" on:click={incrementAge}>Increment</button>
<!-- <button type="submit" on:click={changeName}>Fullname</button> -->
<!-- <input type="text" on:input={inputChange} value={name} id="" /> -->
<input type="text" bind:value={name} />
<!-- forceful two-way connection {value and name will always be the same} -->
