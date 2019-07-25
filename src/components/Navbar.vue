<template>
  <div class="nav-bar">
    <div>
      <img class="nav-logo" src="https://news.ycombinator.com/y18.gif" />
    </div>
    <p>Hacker News</p>
    <router-link to="/news">news</router-link>
    <router-link to="/newest">newest</router-link>
    <router-link to="/show">show</router-link>
    <router-link to="/ask">ask</router-link>
    <router-link to="/jobs">jobs</router-link>
  </div>
</template>

<style>
.nav-bar {
  background-color: rgb(255, 102, 0);
  display: flex;
  justify-content: center;
  align-items: center;
}

.nav-bar p {
  font-size: 1em;
  font-weight: bold;
}

.nav-bar a {
  margin: 10px;
  text-decoration: none;
  color: black;
}

.nav-bar a::after {
  margin-left: 10px;
  content: '|';
}

.nav-logo {
  outline: 1px solid white;
  margin: 10px;
}
</style>
