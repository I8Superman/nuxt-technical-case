<template>
  <div class="campaign">
    <img v-bind:src="imgurl">
    <h3>{{ title }}</h3>
    <h4>{{ description }}</h4>
  </div>
</template>

<script>
export default {
  name: 'CampaignCard',
  props: {
    title: String,
    description: String,
    imgurl: String
  },
  created() {
    // console.log(this.title)
    console.log(this.imgurl)
  }
}
</script>
    
<style lang="scss" scoped>
.campaign {
  padding: 20px;
  border: solid 1px black;
  margin: 20px;
  display: inline-block;

  img {
    width: 350px;
  }
}
</style>