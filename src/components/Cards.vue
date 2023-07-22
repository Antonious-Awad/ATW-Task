<script>
export default {
  name: 'CardComponent',
  props: ['title', 'imageUrl', 'options'] //options variable is a boolean to decide whether to show the last 2 buttons in the card
}
</script>

<template>
  <div class="card-content">
    <img class="card-image" :src="imageUrl" alt="card image" />
    <p class="card-title">
      {{ title }}
    </p>
    <div class="card-more-info" v-if="options">
      <p class="card-text">
        <img src="../assets/layers.png" alt="layers" class="card-icon" />
        View Study Case
      </p>
      <p class="card-text">
        <img src="../assets/show.png" alt="layers" class="card-icon" />
        Live Preview
      </p>
    </div>
  </div>
</template>

<style lang="scss">
.card-content {
  /* width: 540px; */
  width: max-content;
  .card-image {
    cursor: pointer;
    padding-bottom: 25px;
    max-width: 100%;
  }
  .card-title {
    padding: 5px 0px;
    cursor: pointer;
    font-size: 24px;
    color: #1c1c1c;
  }
  .card-more-info {
    display: flex;
    .card-text {
      display: flex;
      cursor: pointer;
      align-items: center;
      justify-content: center;
      padding: 10px 0;
      padding-right: 30px;
      font-weight: 500;
      font-size: 16px;
      color: #151517;
      .card-icon {
        padding: 0 5px;
      }
    }
  }
}
</style>
