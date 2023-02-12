<template>
   <div class="project-list">
      <div class="grid wide">
         <div class="row">
            <div class="col l-12 m-12 s-12">
               <p class="tip-text">
                  Tip: Đối với các game dành cho điện thoại bạn nên chơi Demo trên thiết bị điện thoại nhé!
               </p>
            </div>
            <div
               class="col l-4 m-6 s-12"
               v-for="item in projects"
               :key="item.id"
            >
               <div class="project">
                  <div class="project-image">
                     <img
                        :src="`${require(`@/assets/images/${item.avatar}`)}`"
                        alt="image"
                     />
                  </div>
                  <div class="project-info">
                     <div class="project-name">{{ item.name }}</div>
                     <div class="flex jc-space-between">
                        <div class="project-category">Unity</div>
                        <div class="project-price">{{ item.price }} VNĐ</div>
                     </div>
                  </div>
                  <div class="btns">
                     <a
                        class="btn primary-btn demo-btn"
                        target="_blank"
                        :href="item.linkDemo"
                        >DEMO</a
                     >
                     <button
                        class="btn secondary-btn buy-btn"
                        @click="openBuyingDialog(item.linkDownload)"
                     >
                        MUA SOURCE CODE
                     </button>
                  </div>
               </div>
            </div>
         </div>
      </div>
      <BuyingDialog
         v-if="isShowBuyingDialog"
         :linkDownload="linkDownload"
         @onCloseDialog="isShowBuyingDialog = false"
      />
   </div>
</template>

<script>
import BuyingDialog from "@/components/BuyingDialog.vue";

export default {
   name: "ProjectList",
   components: {
      BuyingDialog,
   },
   data() {
      return {
         projects: [
            {
               id: 1,
               avatar: "AvoidStone.png",
               name: "Avoid Stone",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/avoid-stone",
               linkDownload:
                  "https://drive.google.com/file/d/1ZfSRwjq0Avh0QEhvqcKcvFmSlOrYPkDI/view?usp=share_link",
            },
            {
               id: 2,
               avatar: "BeachArchering.png",
               name: "Beach Archering",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/beach-archering",
               linkDownload:
                  "https://drive.google.com/file/d/1UrYm3L0pOrB92bNcmZRQ319RuUyhOy2m/view?usp=share_link",
            },
            {
               id: 3,
               avatar: "BirdHunting.png",
               name: "Bird Hunting",
               price: "100.000",
               linkDemo: "https://thanhlong0304.itch.io/bird-hunting",
               linkDownload:
                  "https://drive.google.com/file/d/14d6WYRFWJaV9f71oTEH9ObiB2E8LliN1/view?usp=share_link",
            },
            {
               id: 4,
               avatar: "BrickBreaker.png",
               name: "Brick Breaker",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/brick-breaker",
               linkDownload:
                  "https://drive.google.com/file/d/1Axye2RrgMm6lsMVENLAUbBwx62_SHM4g/view?usp=share_link",
            },
            {
               id: 5,
               avatar: "FlappyBird.png",
               name: "Flappy Bird",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/flappy-bird",
               linkDownload:
                  "https://drive.google.com/file/d/1o-fY-G2aHJDN-Qh6uD2f1--DJBT8-DNc/view?usp=sharing",
            },
            {
               id: 6,
               avatar: "MummyJumping.png",
               name: "Mummy Jumping",
               price: "100.000",
               linkDemo: "https://thanhlong0304.itch.io/mummy-jumping",
               linkDownload:
                  "https://drive.google.com/file/d/1TdqDjhwl_Kx5MjiGo-wrDOuIxo9PqS98/view?usp=sharing",
            },
            {
               id: 7,
               avatar: "NinjaJumping.png",
               name: "Ninja Jumping",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/ninja-jumping",
               linkDownload:
                  "https://drive.google.com/file/d/15IdTBpxXYVYeU_cJfUyyqcXBWI5APCxL/view?usp=share_link",
            },
            {
               id: 8,
               avatar: "RacingBoy.png",
               name: "Racing Boy",
               price: "50.000",
               linkDemo: "https://thanhlong0304.itch.io/racing-boy",
               linkDownload:
                  "https://drive.google.com/file/d/16tKA-qMalqqakNXG2LykcA7cMJwHeqV6/view?usp=sharing",
            },
         ],
         isShowBuyingDialog: false,
         linkDownload: "",
      };
   },
   methods: {
      openBuyingDialog(linkDownload) {
         this.linkDownload = linkDownload;
         this.isShowBuyingDialog = true;
      },
   },
};
</script>

<style lang="scss" scoped>
@use "@/assets/scss/colors.scss" as *;
@use "@/assets/scss/variables.scss" as *;

.tip-text {
	font-size: 18px;
	color: $tertiaryColor;
	line-height: 1.3;
   margin-bottom: 20px;
}

.project-list {
   padding: 40px 0;
}

.project {
   margin-bottom: 30px;
   border-radius: $borderRadius;
   overflow: hidden;
   box-shadow: $boxShadowCard;
   background-color: white;

   &-image {
      img {
         width: 100%;
         height: 240px;
         object-fit: contain;
         object-position: center;
         aspect-ratio: 1/1;
      }
   }

   &-info {
      padding: 15px 12px;
   }

   &-name {
      text-align: left;
      margin-bottom: 12px;
      color: $secondaryColor;
   }

   &-category {
      color: #7d879c;
   }

   &-price {
      border-radius: $borderRadius;
      padding: 6px 8px;
      background-color: rgba($primaryColor, 0.18);
      color: $primaryColor;
   }

   .btns {
      padding: 6px 12px 15px 12px;

      .demo-btn {
         margin-bottom: 12px;
      }
   }
}
</style>
