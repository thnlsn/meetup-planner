<script>
  let name = "Thomas";
  let age = 22;

  function incrementAge(number) {
    return age + number;
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {name}, I am {age} years old!</h1>
<button on:click={incrementAge} />
