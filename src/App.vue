<script setup>
import { ref, onMounted, computed, watch } from 'vue'

const todos = ref([]);
const name = ref('');

const input_content=ref('');
const input_category = ref(null);

const todos_asc = computed(()=>todos.value.sort((a, b)=> {
  return b.createdAt - a.createdAt;
}))

const addTodo=()=>{
  if(input_content.value.trim()===''||input_category.value ===null){
    return
  }
  console.log(addTodo);
  todos.value.push()
};

watch(name, (newVal)=>{
  localStorage.setItem('name', newVal);
})

onMounted(()=> {
  localStorage.setItem('name', newVal);
})
</script>

<template>
  <main class='app'>
    <section class="greeting">
      <h2 class = "title">
        Whats up, <input type="text" placeholder="name here"
        v-model="name"/>

      </h2>  
    </section>
    <section class='create-todo'>
      <h3>CREATE A TODO</h3>

      <form @submit.prevent="addTodo">
        <h4>What's on your todo list?</h4>
        <input 
        type="text" 
        placeholder="e.g make a video"
        v.model="input_connect"
        />
        <h4>pick a category</h4>

        <div class="options">
          <label>
            <input 
              type="radio"
              name="category"
              id="category1"
              value="business"
              v_model="input_category"/>
            <span class="bubble business"></span>
            <div>Business</div>
          </label>

          <label>
            <input 
              type="radio"
              name="category"
              value="personal"
              v-model="input_category" />
            <span class="bubble personal"></span>
            <div>Personal</div>  
          </label>
        </div>
      </form>
    </section>
  </main>

</template>