<template>
  <div id="vue-app">
    <header>
        <nav>
            <ul class="nav-links">
                <li><a href="">Home</a></li>
                <li><a href="">About</a></li>
                <li><a href="">Products</a></li>
                <li><a href="">Services</a></li>
                <li><a href="">Blog</a></li>
                <li><a href="">Contact</a></li>
                <li><i class="far fa-heart" style="cursor:pointer"></i></li>
                <li><i class="fas fa-shopping-cart" style="cursor:pointer"></i></li>
            </ul>
        </nav>
    </header>
    <add-profile></add-profile>
  </div>
</template>

<script>
import addProfile from './components/addProfile.vue';
export default {
  components: {
    'add-profile': addProfile
  },

  data () {
    return {
    }
  }
}
</script>

