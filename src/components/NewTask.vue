<template>
    <div class="new-task">
        <input class='form' type="text" placeholder="input new task" id="new-task" name="new-task" required>
        <button type="submit" id="btn-create">add task</button>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.new-task {
    justify-content: center;
    align-items: center;
    text-align: center;
    margin-top: 50px;
}

.form {
    border-radius: 12px;
    border: 2px solid #73AD21;
    padding: 15px;
    width: 400px;
    height: 15px;
}

button {
    background-color: #3498db; 
    border: none;
    color: white;
    padding: 7px 15px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 12px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 12px;
}
</style>