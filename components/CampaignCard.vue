<template>
  <div class="campaign">
    <div class="campaign-image" :style="{ backgroundImage: `url(${imgurl})` }">
    </div>
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
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
  flex: 0 0 300px;
  padding: 20px;
  border: solid 1px black;
  margin: 20px;
  display: inline-block;

  &-image {
    width: 100%;
    height: 250px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  img {
    width: 350px;
  }
}
</style>