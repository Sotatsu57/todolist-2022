<script setup>
import { ref } from "vue";

const items = ref([{ name: "課題1" }, { name: "課題2" }]);
const newItemName = ref("");

const addItem = () => {
  items.value.push({ name: newItemName.value });
};

const completeItem = () => {
  items.value.pop();
};
</script>

<template>
  <div>
    <div>やること（最後に追加したものから終わらせよう!）</div>
    <button @click="completeItem">完了する</button>
    <div v-for="item in items" :key="item.name">
      <div class="name">やること: {{ item.name }}</div>
    </div>
    <div>
      <label>
        今一番やらないといけないこと
        <input v-model="newItemName" type="text" />
      </label>
      <button @click="addItem">追加する</button>
    </div>
  </div>
</template>

<style></style>
