<template>
  <div class="about">
    <h1 class='about__headline'>{{ headline }}</h1>
    <div class='about__content'> {{content}} </div>
  </div>
</template>

<script>

export default {
  name: "About",
    data() {
      return {
        headline: "About Notemaster App",
        content: "By means of this app, You can add any notes You want. So, no worries, You may forget something"
      };
    },
};
</script>

<style scoped lang="scss">
.about{
  &__headline{
    color: red;
  }

  &__content{
    color: purple;
  }


}


</style>
