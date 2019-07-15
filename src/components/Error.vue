<template>
  <div class="error">
    <img
      alt="error-logo"
      src="@/assets/teen-groot.png"
      style="max-height:300px;"
    />

    <h1>ERROR</h1>
    <h2>Some roots goes wrong</h2>
  </div>
</template>

<script>
export default {
  name: 'Error'
}
</script>

<style lang="scss" scoped>
.error {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;

  img {
    margin-bottom: 30px;
  }

  h1,
  h2 {
    margin: 15px 0;
  }
  h2 {
    margin-top: 0;
  }
}
</style>
