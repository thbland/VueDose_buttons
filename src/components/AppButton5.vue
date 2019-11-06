<template>
  <button><slot/></button>
</template>

<script>
export default {
  name: "AppButton5"
};
</script>

<style scoped>
button {
  --black-color: #222;
  --primary-color: #41b883;
  --on-primary-color: white;

  --small-spacing: 12px;
  --normal-spacing: calc(var(--small-spacing) * 2);

  color: inherit;
  border: 4px solid var(--button-border-color, var(--primary-color));
  font-weight: bold;
  background: transparent;
  border-radius: 9999px;
  padding: var(--small-spacing) var(--normal-spacing);
  transition: 0.25s ease-in-out all;
}

button:hover {
  color: var(--button-hover-text-color, var(--on-primary-color));
  background-color: var(--button-hover-background-color, var(--primary-color));
}
</style>
