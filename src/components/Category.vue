<template>
    <div class="container">
        <div class="sub-container col-3 grey"><b>Category</b>
            <TaskCard></TaskCard>
        </div>
    </div>
</template>

<script>
import TaskCard from '../components/TaskCard'

export default {
    components: {
        TaskCard
    }
}
</script>

<style>
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 100%;
}

.sub-container {
    padding: 20px;
    min-height: 500px;
    border-radius: 20px;
}
</style>