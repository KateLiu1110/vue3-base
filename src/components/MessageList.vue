<template lang="">
    <div>
        <input type="text" placeholder="探索消息" v-model="searchTerm">
      <h2>{{options.title}}</h2>
      <p>用戶： {{options.user.name}}, 開關： {{options.user.active? "是" :" 否"}}</p>
      <ul>
        <li v-for="msg in searchMessages" :key="msg.id">{{msg.content}}</li>
      </ul>
      <!-- <button @click="messages = []">刪除全部</button>
      <button @click="options.title='這是標題'">修改標題</button>
      <button @click="options.user.name='李四'">修改用戶</button> -->
    </div>
  </template>
  <script>
  import { ref , reactive, computed , watch} from "vue";
  export default {
    setup() {
      // ref
      const messages = ref([
        { id: 1, content: "這是一條消息提醒1" },
        { id: 2, content: "這是一條消息提醒2" },
        { id: 3, content: "這是一條消息提醒3" },
        { id: 4, content: "這是一條消息提醒4" },
        { id: 5, content: "這是一條消息提醒5" },
      ]);
    
      // reactive
      const options =reactive({
          title : "消息列表",
          user:{
              name: "張三",
              active: true
          }
      });

      // computed
      const searchTerm = ref('');
      const searchMessages= computed(()=>{
        if(searchTerm.value==='')return messages.value;
        return messages.value.filter((msg)=>{
            return msg.content.includes(searchTerm.value);
        })
      });
      return { messages , options , searchTerm, searchMessages};
    },
  };
  </script>
  <style lang=""></style>
  