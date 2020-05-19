<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="/">Instrumentos Online</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="/" active="true">Home</b-nav-item>
          <a href="/#products" class="scrollactive-item nav-link">Productos</a>
          <b-nav-item href="/ubicacion" active="true">Donde Estamos</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {};

</script>
<style>
  .nav-link {
    display: block;
    padding: .5rem 1rem;
        padding-right: 1rem;
        padding-left: 1rem;
        color: white;
}

</style>