<template>
  <transition name="modal-fade">
    <div class="modal-backdrop" @click.self="$emit('close')">
      <div class="modal">
        <div class="modal-content">
          <slot></slot>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'Modal'
}
</script>

<style>
.modal-backdrop {
  position: fixed;
  z-index: 100;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: #00000042;
}

.modal {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 480px;
}

.modal-content {
  width: 100%;
  height: 100%;
  padding: 3em 2em;
  background-color: #fff;
}

.modal-backdrop:is(.modal-fade-enter, .modal-fade-leave-active) {
  opacity: 0;
}

.modal-backdrop:is(.modal-fade-enter, .modal-fade-leave-active) .modal-content {
  transform: translateY(-30px);
}

.modal-backdrop:is(.modal-fade-enter-active, .modal-fade-leave-active) {
  transition: opacity 0.5s ease;
}

.modal-backdrop:is(.modal-fade-enter-active, .modal-fade-leave-active)
  .modal-content {
  transition: transform 0.5s ease;
}
</style>
