<template>
  <transition name="modal">
    <div v-if="isShown" class="modal-screen">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    isShown: Boolean,
  }
}
</script>

<style lang="scss" scoped>
.modal-screen {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, .75);
  opacity: 1;
  z-index: 99;
  transition: .3s;
  backdrop-filter: blur(3px);
}

// modal (transionタグの効果)開始時の style
.modal-enter {
  opacity: 0
}

// modal (transionタグの効果)終了時の style
.modal-leave-to {
  opacity: 0;
}
</style>
