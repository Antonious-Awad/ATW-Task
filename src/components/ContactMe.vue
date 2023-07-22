<script>
export default {
  name: 'ContactMe'
}
</script>

<template>
  <div class="contact-me">
    <h1>Interested working with me?</h1>

    <button>
      <img src="../assets/mail.png" alt="Email Me" />
      Email Me
    </button>
  </div>
</template>

<style lang="scss">
.contact-me {
  background-color: #eebf63;
  border-radius: 25px;
  height: 11%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 100px 0;
  h1 {
    margin: 50px;
    padding: 25px;
    color: #fff;
    font-size: 48px;
    line-height: 62px;
  }
  button {
    border: none;
    height: 4.3rem;
    background-color: #fff;
    width: 16.25rem;
    font-size: 24px;
    line-height: 36px;
    border-radius: 10px;
    margin: 77px 75px;
    cursor: pointer;
  }
}
</style>
