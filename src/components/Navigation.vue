<template>
    <div>
  <b-navbar toggleable="lg" type="dark" variant="dark">
    <b-navbar-brand to="/">Home</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item to="/Conv">Convertidor</b-nav-item>
        
      </b-navbar-nav>

     
    </b-collapse>
  </b-navbar>
  <router-view/>
</div>


</template>

<script> 
export default {
    name:'Navigation'
}
</script>