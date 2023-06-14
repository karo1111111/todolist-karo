<script setup lang="ts">
import { ref, computed } from 'vue'


const tasks = ref<Task[]>([//空のタスク配列を初期値として持つリアクティブな変数を作成
])

//多分なんかこれでいけた気がするけど自信ない


const completedtasks = computed(() => tasks.value.filter((task) => task.state === 'Completed'))

const notcompletedtasks = computed(() => tasks.value.filter((task) => task.state === 'NOTCompleted'))




interface Task {
  name: string
  state: string
}

const newTaskName = ref('')



const addTasks = () => {
  tasks.value.push({ name: newTaskName.value, state: 'NOTCompleted' });
  newTaskName.value = ''; // 入力欄を空にする
};





const changeState = (taskName: string) => {
  const taskIndex = tasks.value.findIndex((task) => task.name === taskName);
  if (taskIndex !== -1) {
    tasks.value[taskIndex].state = 'Completed';
  }
}

</script>


<template>
<div>
    <div>Completed</div>

    <ul>
        <li v-for="task in completedtasks" :key="task.name" >
        <div>名前: {{ task.name }}</div>
      </li>
    </ul>

    <div>NotCompleted</div>
    <ul>
      <li v-for="task in notcompletedtasks" :key="task.name">
        <div>名前: {{ task.name }} <button @click="() => changeState(task.name)">完了</button></div>
      </li>
    </ul>

    <div>
      <label>
        名前
        <input v-model="newTaskName" type="text" />
      </label>


      <button @click="addTasks">追加</button>
    </div>
</div>
</template>

<style>
</style>