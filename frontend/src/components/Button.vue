<template>
  <button @click="click" class="button">
    <slot>Button</slot>
  </button>
</template>

<script>
export default {
  props: {
    onClick: {
      type: Function
    }
  },
  methods: {
    click() {
      if (this.onClick) {
        this.onClick();
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "~Vars";

.button {
  font-family: 'Cabin', sans-serif;
  background: $button;
  border: none;
  border-radius: 100px;
  color: #fff;
  cursor: pointer;
  padding: 13px 30px;
  font-size: 13px;
  transition: background 0.2s ease-in-out;

  &:hover {
    background: darken($button, 10);
  }
}

.button--small {
  background: $buttonlight;
  font-size: 12px;
  padding: 10px 25px;

  &:hover {
    background: darken($buttonlight, 20);
  }
}

.button--disabled,
.button--disabled:hover {
  background: white;
  color: $lightgrey;
  border: 1px solid $lightgrey;
  pointer-events: none;
}

.button--high-margin {
  padding: 13px 60px;
}

.button--landing {
  padding: 15px 45px;
  font-size: 15px;
}

.button--line {
  background: none;
  border: 2px solid $darkblue;
  padding: 10px 30px;
  color: $darkblue;

  &:hover {
    background: $darkblue;
    color: $white;
  }
}

.button--blue {
  background: $darkblue;

  &:hover {
    background: darken($darkblue, 5);
  }
}

.button-back {
  padding: 13px 50px;
}
</style>
