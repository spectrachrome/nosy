<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import url("https://rsms.me/inter/inter.css");

html, body, #app {
  font-family: "Inter", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  background: var(--bg-light);
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

:root {
  --bg-light: #eef1f6;
  --bg-dark: #222;
}

h1, h2, h3, h4, h5, h6 {
  font-weight: 600;
  margin-bottom: 8px;
}

p {
  margin: 8px 0;
}

@media (prefers-color-scheme: dark) {
  #app {
    background: var(--bg-dark) !important;
  }
}
</style>
