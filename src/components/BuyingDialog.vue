<template>
   <div class="buying-dialog overlay" @click.self="closeDialog">
      <div class="dialog">
         <div class="dialog-content">
            <p class="dialog-desc">
               Để mua source code game này bạn chỉ cần gửi <span>email của bạn</span> và
               <span>tên game</span> tới Zalo mình để tiến hành giao dịch nhé.
            </p>
            <div class="flex jc-space-between ai-center">
               <div class="info-admin">
                  <p class="dialog-row-text">
                     <span class="dialog-label">Zalo: </span>
                     <span class="dialog-value">0353292241</span>
                  </p>
                  <p class="dialog-row-text">
                     <span class="dialog-label">Tên: </span>
							<span class="dialog-value">Thành Long</span>
                  </p>
               </div>
               <div class="avatar">
                  <img
                     :src="`${require(`@/assets/images/dino_cute.jpg`)}`"
                     alt="image"
                  />
               </div>
            </div>
         </div>
         <div class="dialog-btns">
            <a class="btn tertiary-btn" :href="linkDownload" target="_blank">
               DOWNLOAD
            </a>
            <button class="btn primary-btn close-btn" @click="closeDialog">
               OK
            </button>
         </div>
      </div>
   </div>
</template>

<script>
export default {
   name: "BuyingDialog",
   emits: ["onCloseDialog"],
	props: {
		linkDownload: String,
	},
   setup(_, { emit }) {
      function closeDialog() {
         emit("onCloseDialog");
      }
      return { closeDialog };
   },
};
</script>

<style lang="scss" scoped>
@use "@/assets/scss/colors.scss" as *;
@use "@/assets/scss/variables.scss" as *;

@keyframes showDialog {
	from {
		opacity: 0;
		transform: scale(0.6);
	} to {
		opacity: 1;
		transform: scale(1);
	}
}

.overlay {
   position: fixed;
   inset: 0;
   background-color: rgba(0, 0, 0, 0.4);
   display: flex;
   align-items: center;
   justify-content: center;
   z-index: 99;
}

.dialog {
   border-radius: $borderRadius;
   box-shadow: $boxShadowCard;
   z-index: 100;
   padding: 20px;
   background-color: white;
   max-width: 380px;
	animation: showDialog 0.3s ease;

   &-content {
      margin-bottom: 24px;
		font-size: 18px;
   }

	&-row-text {
		& + & {
			margin-top: 12px;
		}
	}

   &-desc {
      text-align: left;
		line-height: 1.4;
      span {
         color: $primaryColor;
      }
   }

	&-label {
		color: $primaryColor;
	}

   .close-btn {
      margin-top: 12px;
   }
}

.avatar {
	max-width: 160px;
}
</style>
