<template>
  <div>
    <!-- <Transition name="para"> -->
    <div v-if="open" class="backdrop" @click="$emit('close')"></div>
  <dialog open >
    <slot></slot>
  </dialog>
  <!-- </Transition> -->
  </div>
 
</template>

<script>
import { Template } from 'webpack';

export default {
  // props: ['Open'],
    emits: ["close"],
    components: { Template }
};
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: 10;
  background-color: rgba(0, 0, 0, 0.75);
}

dialog {
  position: fixed;
  top: 30vh;
  width: 30rem;
  left: calc(50% - 15rem);
  margin: 0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 12px;
  padding: 1rem;
  background-color: white;
  z-index: 100;
  border: none;
}
/* .modal-enter-active {
   animation: modal 0.3s ease-out;
}
.modal-leave-active {
  animation: modal 0.3s ease-in;
} */
/* @keyframes modal {
  0% {
    transform: translateX(0) scale(1);
  }
  70% {
    transform: translateX(-120x) scale(1,1);
  }
  100% {
    transform: translateX(-150px) scale(1);
  }
} */
</style>