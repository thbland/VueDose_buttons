<template>
  <button><slot/></button>
</template>

<script>
export default {
  name: "AppButton3"
};
</script>

<style scoped>
button {
  --primary-color: #41b883;
  
  color: inherit;
  border: 4px solid var(--primary-color);
  font-weight: bold;
  background: transparent;
  border-radius: 9999px;
  padding: 12px 24px;
  transition: 0.25s ease-in-out all;
}

button:hover {
  color: white;
  background-color: var(--primary-color);
}
</style>
