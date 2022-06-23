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
}
</script>
    
<style lang="scss" scoped>
.campaign {
  flex: 0 0 300px;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 20px -5px rgba(0, 0, 0, 0.75);
  margin: 20px;
  display: inline-block;
  height: fit-content;

  &-image {
    width: 100%;
    height: 250px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
}
</style>