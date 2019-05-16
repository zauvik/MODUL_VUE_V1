<template>
  <div id="app">
    <nav class="navbar justify-content-between navbar-light bg-light">
      <a class="navbar-brand" href="">
        <img src="https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-solid.svg" width="30" height="30" class="d-inline-block align-top" alt="">
        AppkuName
      </a>
        <ul style="list-style:none">
          <li class="nav-item active">
            <a class="nav-link" href="/" style="display:inline-block">Article</a>
            <a class="nav-link" href="/about" style="display:inline-block">About</a>
          </li>
        </ul>
    </nav>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
