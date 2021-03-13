<template>
    <div>
        <Navbar></Navbar>
        <NewTask></NewTask>
        <Category></Category>
        <TaskCard></TaskCard>
    </div>
  
</template>

<script>
import Navbar from '../components/Navbar'
import NewTask from '../components/NewTask'
import Category from '../components/Category'


export default {
  components: {
      Navbar,
      NewTask,
      Category
  }
};
</script>

<style>
    * {
    margin: 20px 5px;
    padding: 0; 
    max-width: 100%;   
}

body {
    background-color: #396298;
}

.grey {
    background-color: rgb(214, 214,214);
}

.white {
    background-color: snow;
}
</style>