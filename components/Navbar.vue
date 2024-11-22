<template>
  <nav class="navbar">
    <ul>
      <li><a href="#home">INICIO</a></li>
      <li><a href="#about">Iniciar Sesion</a></li>
      <li><a href="#contact">Menu</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style>
.navbar {
  background-color: #1a1a1a;
  padding: 1rem;
  text-align: center;
}

.navbar ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.navbar li {
  display: inline;
  margin: 0 1rem;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}
</style>
