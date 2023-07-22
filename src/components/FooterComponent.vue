<script>
export default {
  name: 'FooterComponent',
  methods: {
    scrollToTop() {
      // Scroll back to the top of the page when the button is clicked
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<template>
  <div class="footer container">
    <p>Let's Connect</p>

    <div>
      <img src="../assets/Instagram.png" alt="Instagram" class="social" />
      <img src="../assets/YouTube.png" alt="YouTube" class="social" />
      <img src="../assets/Dribbble.png" alt="Dribble" class="social" />
    </div>

    <p class="back-to-top" @click="scrollToTop">
      Back to Top <img src="../assets/short_up.png" alt="arrow_up" />
    </p>
  </div>
</template>

<style lang="scss">
.footer {
  display: flex;
  justify-content: space-between;
  margin-bottom: 60px;
  p {
    font-weight: 500;
    font-size: 36px;
    line-height: 46px;
  }

  .social {
    margin: 0 25px;
    cursor: pointer;
  }
  .back-to-top {
    font-size: 24px;
    cursor: pointer;
  }
}
</style>
