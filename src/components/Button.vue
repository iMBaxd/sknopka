<template>
  <button
    :class="{ 'btn': true, 'btn-active': isActive, 'btn-disabled': isDisabled }"
    :disabled="isDisabled"
    @click="handleClickEvent"
  >
    {{ buttonText }}
  </button>
</template>

<script>
export default {
  name: 'CustomButton',
  props: {
    buttonText: {
      type: String,
      default: "Сохранить",
    },
    handleClick: {
      type: Function,
      required: true,
    },
    isActive: {
      type: Boolean,
      default: true,
    },
    isDisabled: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleClickEvent() {
      if (this.isActive && !this.isDisabled) {
        this.handleClick();
      } else {
        console.log('Кнопка заблокирована и не может быть нажата.');
      }
    },
  },
};
</script>

<style>
.btn {
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

.btn-active {
  background-color: #007bff;
  color: #fff;
}

.btn-disabled {
  background-color: #ccc;
  color: #999;
  cursor: not-allowed;
}
</style>