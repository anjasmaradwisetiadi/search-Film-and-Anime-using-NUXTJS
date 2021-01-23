<template>
  <section class="justify-center items-center text-center">
    <!-- content -->
    <div
      v-if="toggleModal"
      class="fixed inset-0 flex justify-center items-center z-50 fixed"
    >
      <div class="relative mx-auto w-auto max-w-2x1">
        <div class="bg-blue-500 w-40 text-white">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Error
            minima tenetur itaque fugit exercitationem ab tempore eveniet non
            consectetur
          </p>
          <button
            class="relative bg-green-400 hover:bg-green-700 px-4 py-2 mt-4 text-white"
            @click="closeModal(!toggleModal)"
          >
            close
          </button>
        </div>
      </div>
    </div>

    <div v-if="toggleModal" class="height_window" :style="heightShadow"></div>
  </section>
</template>
<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: {
    toggleModal: {
      type: Boolean,
      default: false,
    },
    windowHeight: {
      type: Number,
      default: 0,
    },
    windowWidth: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      displayModal: true,
    };
  },
  computed: {
    heightShadow() {
      return {
        height: this.windowHeight+'px',
        width: `${this.windowWidth}px`,
      };
    },
  },

  methods: {
    closeModal(data: boolean) {
      this.$emit('closedModal', data);
    },
  },
});
</script>

<style lang="scss" scoped>
.height_window {
  z-index: 10;
  position: fixed;
  opacity: 50%;
  background-color: #374151;
}
</style>
