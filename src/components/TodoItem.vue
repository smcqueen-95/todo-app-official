<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <b-form-group>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
        <b-button inline @click="$emit('del-todo', todo.id)" class="btn btn-outline-danger btn-sm float-right" variant="outline-danger">Delete</b-button>
    <div class="date">
    <label for="datepicker-buttons-sm">Choose a Date</label>
    <b-form-datepicker
      id="datepicker-buttons" size="sm"
      today-button
      reset-button
      close-button
      locale="en"
    ></b-form-datepicker>
</div>
           
  
    </b-form-group>
    
   <div class="time">
    <label for="timepicker-buttons-sm">Choose a Time to Start Your Tasks</label>
    <b-form-timepicker
      id="timepicker-buttons" size="sm"
      now-button
      reset-button
      locale="en"
    ></b-form-timepicker>
  </div>

    </div>
   

</template>



<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }

}
}
</script>

<style scoped>

.todo-item{
    border-bottom: 1px black groove;
    margin-right: 50px;
    margin-left: 50px;
    margin-top: 20px;
    height: 135px;
}

.is-complete{
    text-decoration: line-through;
}

.btn{
    margin-top: 20px;
}
.date{
    position: relative;
    top:0px;
    width: 30%;
    margin-top:45px;
}
.time{
    top: 0px;
    width: 25%;
    margin-left: 390px;
    margin-top: 0px;
    margin-bottom: 100px;
    position: relative;
}


</style>