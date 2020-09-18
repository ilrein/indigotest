<template>
  <sui-container>
    <div class="about">
      <h1>
        This product is randomly generated and has no basis in reality.
      </h1>
    </div>

    <a
      class="leave"
      @click="leave"
    >
      Leave this page to go somewhere else
    </a>

    <div>
      <sui-modal v-model="open">
        <sui-modal-header>
          Are you sure you want to leave?
        </sui-modal-header>
        <sui-modal-actions>
          <sui-button negative @click.native="ok">
            OK
          </sui-button>
          <sui-button positive @click.native="cancel">
            Cancel
          </sui-button>
        </sui-modal-actions>
      </sui-modal>
    </div>
  </sui-container>
</template>

<script>
export default {
  data() {
    return {
      open: false,
    };
  },
  methods: {
    leave() {
      this.open = true;
    },
    ok() {
      this.open = true;
      window.location.href = 'https://www.linkedin.com/in/ilia-reingold-71150b98/';
    },
    cancel() {
      this.open = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.about {
  margin-bottom: 1rem;
}

.leave {
  cursor: pointer;
}
</style>
