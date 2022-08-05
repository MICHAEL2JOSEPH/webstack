<template>
  <div>
    <div>
  <b-navbar toggleable="lg"  class="pg" type="dark" variant="">
    <b-navbar-brand href="#" class="gg">MikeJ🧡e<span class="f">F</span>rame</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        
        <b-nav-item href="/">Home</b-nav-item>
        <b-nav-item href="/about">About</b-nav-item> 
        <b-nav-item href="/contact">Contact</b-nav-item>
         <!-- <b-nav-item href="/projects">Projects</b-nav-item>  -->
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
         <b-input-group>
      <b-input-group-prepend>
        <b-button @click="value = null">Clear</b-button>
      </b-input-group-prepend>
      <b-form-rating v-model="value" color="#ff8800"></b-form-rating>
      <b-input-group-append>
        <b-input-group-text class="justify-content-center" style="min-width: 3em;">
          {{ value }}
        </b-input-group-text>
      </b-input-group-append>
    </b-input-group>

        <b-nav-item-dropdown text="Lang" right class="loading">
          <b-dropdown-item  class="loading" href="#">ENGLISH </b-dropdown-item>
          <b-dropdown-item class="loading" href="#">SPANISH</b-dropdown-item>
          <b-dropdown-item class="loading" href="#">FRENCH</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
           <div  class="toggle" ontoggle="doStuff()">
     <b-form-checkbox ontoggle="doStuff()" switch size="lg"></b-form-checkbox>
        </div>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
  </div>
</template>

<script>

export default {
     data() {
      return {
        value: null
      }
    },
}

</script>

<style>
.pg {
    background-color: transparent;
}

.f {
    text-decoration: overline;
    text-decoration-color: black;
    text-shadow: none;
}

.gg{
    text-shadow: 4px 3px 1px rgb(102, 7, 89);
}

.toggle {
    width: 40px;
    height: 30px;
    margin-left: 26px;
}

.loading {
  cursor: wait;
}
</style>