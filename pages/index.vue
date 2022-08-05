<template>
  <div class="container">
    <h1>Welcome!</h1>
    <h2>See open campaigns below</h2>
    <div class="campaigns-slider">
      <div class="campaigns-slider-right" @click="scrollJump('left')">
        <img src="../assets/svgs/scroll-arrow.svg" alt="" class="left-arrow">
      </div>
      <div class="campaigns-slider-left" @click="scrollJump('right')">
        <img src="../assets/svgs/scroll-arrow.svg" alt="" class="right-arrow">
      </div>
      <div @scroll="checkScrollBtnVisibility" class="campaigns-slider-wrapper">
        <CampaignCard v-for="(campaign, index) in campaigns" :key="index" :title="campaign.title"
          :description="campaign.description" :imgurl="campaign.imageURL" />
      </div>
    </div>
  </div>
</template>

<!-- :url="campaign.imageURL" :description="campaign.description"
      :title="campaign.title" :uid="campaign.uid" -->

<style lang="scss" scoped>
.container {
  padding: 50px;

  .campaigns-slider {
    overflow-x: scroll;
    position: relative;

    &-wrapper {
      display: flex;
      overflow-x: auto;
      height: fit-content;

      &::-webkit-scrollbar {
        display: none;
      }
    }

    &-right,
    &-left {
      position: absolute;
      width: 30px;
      z-index: 10;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transition: all 0.3s;
      opacity: 1;

      &:hover {
        cursor: pointer;
        background-color: rgba(0, 0, 0, 0.3);
      }

      img {
        width: 80%;
      }
    }

    &-left {
      opacity: 0;

      img {
        transform: rotate(180deg);
      }
    }

    &-right {
      right: 0;
    }
  }
}
</style>

<script>
const campaigns = [{
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/CJhc8MG_fl_5Df_nJHGso",
  description: "Vi søger ambassadører der kan skabe opmærksomhed omkrig Foto Factory.",
  title: "Copy of fesfes",
  uid: "qUm0vueM7"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/TORCSDfv2dqHWkzQxYSFN",
  description: `Hello! 

We're currently looking for tiktokkers to be in our videos for Pico's own TikTok account. If interested please join the campaign, and we will then message you when we spot a trend we think you'd be a good fit for. 

One hour of your time will be rewarded with a gift card for 2 x Pico Trio to enjoy with a friend any time you want.  `,
  title: "fesfes",
  uid: "Sp5hr9zuc"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x",
  description: "You can choose 2 clothes from our new winter collection",
  title: "Test2",
  uid: "C-7zfkTsV"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/eEsUrsA4NW40xSji-DsUo",
  description: `We are excited to kick off our ZENZ TikTok campaign. We would love for you to be one of our first influencers to promote ZENZ Organic on TikTok!

In this campaign we want you to share with your followers that ZENZ Organic is more than just a quality beauty and haircare brand, but our products are also made from natural and organic ingredients. ZENZ Organic are developed by hairdressers, and we prioritize health and sustainability together with a high quality. 

The campaign period is from 15st of July - 15st of August. When you have joined the campaign you will receive a voucher code so you can order your favorite products from our website.  

For this campaign you need to use the hashtags: #ZENZOrganic and #ZENZOrganicProducts #ZenzNetherlands #ZenzAmbassador and tag @ZENZOrganic`,
  title: "ZENZ TikTok Kickoff Campaign NLh",
  uid: "IUVRvbhM-r342awfdwafse"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/0EyFa2VzF2FMER4slWZuk",
  description: "Products from Frederik Bagger (worth up to 3000NOK)",
  title: "Frederik Bagger Norwegian Launch",
  uid: "IUVRvbhdawM-r342awfdwafse"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/CJhc8MG_fl_5Df_nJHGso",
  description: "Vi søger ambassadører der kan skabe opmærksomhed omkrig Foto Factory.",
  title: "Copy of fesfes",
  uid: "qUm0vueM7"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/TORCSDfv2dqHWkzQxYSFN",
  description: `Hello! 

We're currently looking for tiktokkers to be in our videos for Pico's own TikTok account. If interested please join the campaign, and we will then message you when we spot a trend we think you'd be a good fit for. 

One hour of your time will be rewarded with a gift card for 2 x Pico Trio to enjoy with a friend any time you want.  `,
  title: "fesfes",
  uid: "Sp5hr9zuc"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/K3OkZOAFtkVplTVUkwn2x",
  description: "You can choose 2 clothes from our new winter collection",
  title: "Test2",
  uid: "C-7zfkTsV"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/eEsUrsA4NW40xSji-DsUo",
  description: `We are excited to kick off our ZENZ TikTok campaign. We would love for you to be one of our first influencers to promote ZENZ Organic on TikTok!

In this campaign we want you to share with your followers that ZENZ Organic is more than just a quality beauty and haircare brand, but our products are also made from natural and organic ingredients. ZENZ Organic are developed by hairdressers, and we prioritize health and sustainability together with a high quality. 

The campaign period is from 15st of July - 15st of August. When you have joined the campaign you will receive a voucher code so you can order your favorite products from our website.  

For this campaign you need to use the hashtags: #ZENZOrganic and #ZENZOrganicProducts #ZenzNetherlands #ZenzAmbassador and tag @ZENZOrganic`,
  title: "ZENZ TikTok Kickoff Campaign NLh",
  uid: "IUVRvbhM-r342awfdwafse"
}, {
  imageURL: "https://dreaminfluencers.s3.eu-central-1.amazonaws.com/userContent/0EyFa2VzF2FMER4slWZuk",
  description: "Products from Frederik Bagger (worth up to 3000NOK)",
  title: "Frederik Bagger Norwegian Launch",
  uid: "IUVRvbhdawM-r342awfdwafse"
}];

export default {
  name: "IndexPage",
  data() {
    return {
      campaigns: campaigns,
      loading: true,
      error: null,
      btnVisible: {
        left: true,
        right: false
      }
    };
  },
  computed: {
    // scrollBtnVisibility(btn) {
    //   const wrapper = this.$el.querySelector('.campaigns-slider-wrapper');
    //   const wrapperWidth = wrapper.getBoundingClientRect().width;
    //   const maxScroll = wrapperWidth + wrapper.scrollLeft;
    //   if (btn === 'left' && wrapper.scrollLeft > 0) {
    //     return true;
    //   } else if (btn === 'right' && wrapper.scrollWidth === maxScroll) {
    //     return true;
    //   } else {
    //     return false;
    //   }
    // }
  },
  methods: {
    // Calculate wrapper width and scroll by that amount
    scrollJump(direction) {
      const wrapper = this.$el.querySelector('.campaigns-slider-wrapper');
      const wrapperWidth = wrapper.getBoundingClientRect().width;
      wrapper.scrollBy({
        left: direction === 'left' ? wrapperWidth : -(wrapperWidth),
        behavior: 'smooth'
      });
    },
    checkScrollBtnVisibility() {
      const btnRight = this.$el.querySelector('.campaigns-slider-right');
      const btnLeft = this.$el.querySelector('.campaigns-slider-left');
      const wrapper = this.$el.querySelector('.campaigns-slider-wrapper');
      const wrapperWidth = wrapper.getBoundingClientRect().width;
      const maxScroll = wrapper.scrollWidth - wrapperWidth;
      if (wrapper.scrollLeft === 0) {
        console.log('left btn should be gone')
        btnLeft.style.opacity = 0;
      } else if (wrapper.scrollLeft >= maxScroll) {
        console.log('right btn should be gone')
        btnRight.style.opacity = 0;
      } else {
        console.log('both btns should be visible')
        btnLeft.style.opacity = 1;
        btnRight.style.opacity = 1;

      }
    }
  }
}
</script>
