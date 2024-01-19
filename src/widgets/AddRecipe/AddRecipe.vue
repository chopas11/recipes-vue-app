<script>
import Input from "../../components/Input/Input.vue";
import Button from "../../components/Button/Button.vue";
import {Icon} from '@iconify/vue';
import noImage from "../../assets/images/no-image.png"

export default {
  name: "AddRecipe",
  components: {Button, Input, Icon},
  data () {
    return {
      formVisible: true,
      dishName: "",
      dishIngredients: "",
      dishTime: "",
      dishDescription: "",
      dishCover: "",
    }
  },
  methods: {
    uploadCover (event) {
      const reader = new FileReader();
      let file = "1231";
      // var name = event.target.files[0].name;
      reader.addEventListener("load", function () {
        localStorage.setItem("newImage", this.result);
      });
      reader.readAsDataURL(event.target.files[0]);
    },
    addRecipe() {
      if (this.dishName === "" || this.dishIngredients === "" || this.dishTime === "" ||
          this.dishDescription === "") {
        console.log("Заполните поля");
      } else {
        let image = null;
        if ( localStorage.getItem("newImage") === null ) {
          image = noImage;
        } else {
          image = localStorage.getItem("newImage");
        }

        const newDish = {
          id: new Date().valueOf(),
          label: this.dishName,
          time: this.dishTime,
          ingredients: this.dishIngredients,
          description: this.dishDescription,
          views: 0,
          likes: 0,
          image: image,
        };

        let dishes = JSON.parse(localStorage.getItem('recipes'));
        if (dishes === null) dishes = [];
        localStorage.setItem('recipes', JSON.stringify([...dishes, newDish]));
        this.formVisible = false;
        localStorage.removeItem("newImage");
      }



    },
  },
}
</script>

<template>
  <div class="addRecipe" v-if="formVisible">
    <div class="text-center">
      <h2>Добавление рецепта</h2>
    </div>
    <div class="flex flex-row gap-3">
      <div class="basis-1/2">
        <span class="geologica text-lg">Введите название блюда</span>
        <input v-model="dishName" class="input mt-2" placeholder="Название блюда" />
      </div>
      <div class="basis-1/4">
        <span class="geologica text-lg">Введите количество игредиентов</span>
        <input v-model="dishIngredients" class="input mt-2" placeholder="Количество ингредиентов" />
      </div>
      <div class="basis-1/4">
        <span class="geologica text-lg">Введите количество времени</span>
        <input v-model="dishTime" class="input mt-2" placeholder="Количество времени" />
      </div>
    </div>
    <div class="flex flex-row gap-3 mt-10 items-end">
      <div class="basis-3/5">
        <span class="geologica text-lg">Введите описание рецепта</span>
        <input v-model="dishDescription" class="input mt-2" placeholder="Описание рецепта" />
      </div>
      <div class="basis-1/5">
        <span class="geologica text-lg">Загрузите фото блюда</span>
        <input type="file" @change="uploadCover" class="input mt-2" placeholder="Фото" />
      </div>
      <div class="basis-1/5">
        <span class="geologica text-sm ">*необязательно</span>
      </div>
    </div>
    <div class="text-center mt-10">
      <Button @click="addRecipe" styles="green">Добавить рецепт</Button>
    </div>
  </div>

  <div class="text-center mt-20" v-else>
    <div class="inline-block rounded-full" style="background: var(--green-light-color)">
      <Icon icon="mdi:tick-circle-outline" color="#e6cfdf" width="300" height="300" />
    </div>
    <h2 class="mt-10 mb-5">Рецепт успешно добавлен</h2>
  </div>

  <div class="text-center mt-2">
    <Button @click="this.$emit('back')" styles="green">Вернуться на главную</Button>
  </div>




</template>

<style scoped>

.input {
  background: var(--lil-light-color);
  padding: 12px 20px;
  border-radius: 50px;
  font-size: 14px;
  outline: none;
  width: 100%;
}

</style>