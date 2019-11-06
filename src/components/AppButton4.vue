<template>
  <button><slot/></button>
</template>

<script>
export default {
  name: "AppButton4"
};
</script>

<style scoped>
button {
  --primary-color: #41b883;
  --on-primary-color: white;

  --background-color: white;
  --on-background-color: #222;

  --small-spacing: 12px;
  --normal-spacing: calc(var(--small-spacing) * 2);
  
  color: inherit;
  border: 4px solid var(--primary-color);
  font-weight: bold;
  background: transparent;
  border-radius: 9999px;
  padding: var(--small-spacing) var(--normal-spacing);
  transition: 0.25s ease-in-out all;
}

button:hover {
  color: var(--on-primary-color);
  background-color: var(--primary-color);
}
</style>
