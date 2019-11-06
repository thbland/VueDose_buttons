<template>
  <button :style="getTheme"><slot/></button>
</template>

<script>
export default {
  name: "AppButton6",
  props: {
    theme: String,
    validator: (theme) => ['primary', 'secondary'].includes(theme)
  },
  computed: {
    getTheme() {
      const createButtonTheme = ({
        borderColor,
        hoverTextColor,
        hoverBackgroundColor
      }) => ({
        '--button-border-color': borderColor,
        '--button-hover-text-color': hoverTextColor,
        '--button-hover-background-color': hoverBackgroundColor
      })

      const primary = createButtonTheme({
        borderColor: 'var(--primary-color)',
        hoverTextColor: 'var(--on-primary-color)',
        hoverBackgroundColor: 'var(--primary-color)'
      })

      const secondary = createButtonTheme({
        borderColor: 'var(--secondary-color)',
        hoverTextColor: 'var(--on-secondary-color)',
        hoverBackgroundColor: 'var(--secondary-color)'
      })
      
      const themes = {
        primary,
        secondary
      }
      
      return themes[this.theme]
    }
  }
};
</script>

<style scoped>
button {
  --primary-color: #41b883;
  --on-primary-color: white;

  --secondary-color: #7589e4;
  --on-secondary-color:#131313;

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
