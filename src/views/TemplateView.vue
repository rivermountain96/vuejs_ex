<script setup>
const rawHtml = '<a href="">Link</a>';
const pid = 10;
const isButtonDisabled = true;
const objectOfAttrs = {
  id: "container",
  class: "wrapper",
};
const number = 20;
const ok = false;
const message = "안녕하세요";
const id = 30;

const sayHello = (msg) => {
  alert(msg);
};

const url = "https://google.com";
const attributeName = "href";
const items = [
  { id: 0, title: "html" },
  { id: 1, title: "css" },
  { id: 2, title: "javascript" },
];

const onSubmit = () => {
  alert("제출되었습니다.");
};
</script>

<template>
  <div class="layout">
    <p>{{ rawHtml }}</p>
    <p><span v-html="rawHtml"></span></p>
    <hr />
    <h2>속성 바인딩</h2>
    <div v-bind:id="pid"></div>
    <div :id="pid"></div>
    <h2>불리언 바인딩</h2>
    <button :disabled="true">버튼</button>
    <button :disabled="isButtonDisabled">버튼</button>
    <button :disabled="!isButtonDisabled">버튼</button>
    <h2>여러속성 바인딩</h2>
    <div v-bind="objectOfAttrs"></div>
    <h2>javascript expression</h2>
    {{ number + 1 }}
    {{ ok ? "예" : "아니오" }}
    {{ message.split("").reverse().join("") }}
    <div :id="`list-${id}`"></div>
    <h2>함수 호출</h2>
    <!-- <span :title="sayHello('안녕')"></span> -->
    <!-- <div>
      {{ sayHello("안녕") }}
    </div> -->
    <h2>디렉티브</h2>
    <a v-bind:href="url">구글</a>
    <a :[attributeName]="url"> 구글 </a>
    <div v-for="item in items" :key="item.id">
      {{ item.title }}
    </div>
    <h2>v-on</h2>
    <div>
      <button type="button" v-on:click="sayHello('안녕')">안녕</button>
      <button type="button" @click="sayHello('안녕')">안녕</button>
      <!-- <button type="button" @mouseover="sayHello('안녕')">안녕</button> -->
    </div>
    <form action="" @submit.prevent="onSubmit">
      <button>제출</button>
    </form>
  </div>
</template>

<style></style>
