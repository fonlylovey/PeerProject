
<script setup>
import {ref} from 'vue'
import "../../peer-stream.js";
const peerStream = ref();
const inputText = ref();



function callUEFUnction()
{
  console.log("像素流对象", peerStream.value);
  peerStream.value.emitMessage(inputText.value);
}

</script>

<template>
  
	<div id="UEDIV" class="viewer">
    <video is="peer-stream" ref ='peerStream' id="ws://127.0.0.1:11188/" > </video>
  </div>
  <div class="container">
    <button @click="callUEFUnction" class="action-button">调用</button>
    <input class="text-input" type="text" v-model="inputText" placeholder="请输入内容">
  </div>
</template>

<style scoped>
.viewer{
  position: absolute;
  background-color: aquamarine;
  width: 100%;
  height: 100%;
}
.container {
  position: relative;
  max-width: 600px;
  margin: 50px auto;
  padding: 20px;
  font-family: 'Arial', sans-serif;
}

h1 {
  color: #2c3e50;
  text-align: center;
}

.input-group {
  display: 100%;
  gap: 10px;
  margin-top: 30px;
}

.text-input {
  padding: 12px 15px;
  border: 2px solid #3498db;
  border-radius: 4px;
  font-size: 16px;
  transition: border-color 0.3s;
}

.action-button {
  width: 128px;
  height: 48px;
  margin: 20px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 0 25px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.action-button:hover {
  background-color: #2980b9;
}

.action-button:active {
  transform: translateY(1px);
}

</style  >
