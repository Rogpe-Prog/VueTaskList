<template>
  <div class="task" :class="stateClass">
      <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
    props: {
        task: { type: Object, required: true }
    },
    computed: {
        stateClass(){
            return {
                pending: this.task.pending,
                done: !this.task.pending
            }
        }
    }

}
</script>

<style>
    .task {
        box-sizing: border-box;
        width: 200px;
        height: 100px;
        padding: 8px;
        border-radius: 8px;
        font-size: 1rem;
        font-weight: 100;
        cursor: pointer;
        user-select: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .pending {
        border-left: 12px solid #b73229;
        background-color: #f44336;
    }

    .done {
        color: #DDD;
        border-left: 12px solid #0a8f08;
        background-color: #4caf50;
        text-decoration: line-through;
    }
</style>