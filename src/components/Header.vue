<template>
   <header class="header">
      <div class="header-top">
         <div class="grid wide">
            <div class="row">
               <div class="col l-12 m-12 s-12">
                  <div class="header-top-content">
                     <div class="header-top-side logo">
                        <img
                           :src="`${require(`@/assets/images/LogoDark.png`)}`"
                           alt="logo"
                        />
                     </div>
                     <div class="header-top-side">
                        <i class="fa-solid fa-headphones-simple"></i>
                        <p><span class="header-top-side-label">Zalo: </span>035 329 2241</p>
                     </div>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </header>
</template>

<script>
export default {
   name: "HeaderComponent",
};
</script>

<style lang="scss" scoped>
@use "@/assets/scss/colors.scss" as *;
@use "@/assets/scss/variables.scss" as *;

.logo {
   width: 85px;
}

.header {
   &-top {
      background-color: white;

      &-content {
         color: $secondaryColor;
         font-size: 13px;
			font-weight: bold;
         height: 45px;
         display: flex;
         justify-content: space-between;
         align-items: center;
         width: 100%;
      }

      &-side {
         display: flex;
         align-items: baseline;

         i {
            color: #4ad295;
         }

         p {
            margin-left: 6px;
         }

			&-label {
				color: #4ad295;
			}
      }
   }
}
</style>
