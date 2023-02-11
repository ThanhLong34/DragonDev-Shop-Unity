<template>
   <div class="welcome">
      <div class="grid wide">
         <div class="row">
            <div class="col l-12 m-12 s-12">
               <div class="content">
                  <div class="content-header">
                     <h1>Chào mừng bạn đến với</h1>
                     <h1 class="shop-name">DragonDev Shop Unity</h1>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
export default {
   name: "WelcomeComponent",
};
</script>

<style lang="scss" scoped>
@use "@/assets/scss/colors.scss" as *;
@use "@/assets/scss/variables.scss" as *;

.welcome {
   padding-top: 52px;
   padding-bottom: 52px;
   background-image: url("@/assets/images/bg.jpg");
   background-position: center top !important;
}

.content {
   color: white;
	line-height: 1.3;

   &-header {
      h1 {
         font-size: 32px;
         text-transform: uppercase;
      }

      .shop-name {
         color: $primaryColor;
         margin-top: 16px;
      }
   }
}
</style>
