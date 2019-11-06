<template>
  <main class="wrapper" :class="mode">
    <div class="grid">
      <AppButton text="Hello VueDose!" />
      <AppButton2>Hello VueDose!</AppButton2>
      <AppButton3>Hello VueDose!</AppButton3>
      <AppButton4>Hello VueDose!</AppButton4>
      <AppButton5 class="custom-theme">Hello VueDose!</AppButton5>
      <AppButton6 theme="secondary">Hello VueDose!</AppButton6>
      <AppButton6 theme="secondary">Hello VueDose!</AppButton6>
      <AppButton6 @click.native="toggleTheme" theme="secondary">Click me to change to dark mode!</AppButton6>
    </div>
  </main>
</template>

<script>
import AppButton from "./components/AppButton";
import AppButton2 from "./components/AppButton2";
import AppButton3 from "./components/AppButton3";
import AppButton4 from "./components/AppButton4";
import AppButton5 from "./components/AppButton5";
import AppButton6 from "./components/AppButton6";

export default {
  name: "App",
  data: () => ({
    mode: 'light'
  }),
  components: {
    AppButton,
    AppButton2,
    AppButton3,
    AppButton4,
    AppButton5,
    AppButton6
  },
  methods: {
    toggleTheme() {
      this.mode = this.mode === 'light' ? 'dark' : 'light'
    }
  }
};
</script>
<style>
html,
body {
  margin: 0;
  padding: 0;
}
</style>
<style scoped>
.light {
  --background-color: white;
  --on-background-color: #222;
}

.dark {
  --background-color: #222;
  --on-background-color: white;
}

.custom-theme {
  --button-border-color: pink;
  --button-hover-background-color: rgb(206, 161, 195);
}

.wrapper {
  width: 100%;
  min-height: 100vh;

  margin: 0;
  padding: 0;
  transition: 1s ease-in-out background-color;
  background-color: var(--background-color);
}

.grid {
  color: var(--on-background-color);
  padding: 24px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-gap: 24px;
}
</style>
