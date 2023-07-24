<template>
  <div>
    <!-- Пример использования компонента "Button" -->
    <Button :buttonText="saveButtonText" :handleClick="handleSaveClick" :isDisabled="true"/>
  </div>
</template>

<script>
import Button from '../components/Button.vue'; // Импортируем компонент "Button"

export default {
  components: {
    Button, // Регистрируем компонент "Button" внутри "CustomButtonExample"
  },
  data() {
    return {
      saveButtonText: 'Сохранить',
    };
  },
  methods: {
    handleSaveClick() {
        // if (this.isDisabled){
            // console.log('Кнопка заблокирована и не может быть нажата.');
        // }
      console.log('Кнопка "Сохранить" была нажата!');
    },
  },
};
</script>