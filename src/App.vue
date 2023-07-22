<script>
import HeaderComponent from './components/HeaderComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
import './style.scss'
export default {
  components: {
    HeaderComponent,
    FooterComponent
  }
}
</script>

<template>
  <div class="App">
    <HeaderComponent />
    <RouterView />
    <FooterComponent />
  </div>
</template>
