<template>
  <img
    class="area-profile-icon"
    :src="user.icon_image_url"
    :alt="imageCaption"
    v-if="user.icon_image_url !== undefined">
  <img
    class="area-profile-icon"
    src="~assets/images/pc/common/icon_user_noimg.png"
    :alt="imageCaption"
    v-else>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  computed: {
    imageCaption() {
      return `${this.user.user_display_name}'s icon'`
    }
  }
}
</script>

<style lang="scss" scoped>
.area-profile-icon {
  grid-area: profile-icon;
  height: 36px;
  width: 36px;
  border-radius: 50%;
  object-fit: cover;
}
</style>
