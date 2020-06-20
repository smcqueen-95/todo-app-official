<template>
    <div>
        <form @submit="addTodo">
          
               <b-input type="text" v-model="title" name="title" class="title w-50" placeholder="Add Task"></b-input> 
             <input type="submit" value="Submit" class="btn btn-outline-info">
               
           
               </form>
    </div>

</template>


<script>


export default {
    name: "AddTodo",
    data(){
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            }
            //send up to parent
            this.$emit('add-todo', newTodo);

            this.title= '';
        }
    }
}
</script>

<style scoped>

form {
    display: flex;
}

input[type="text"]{
    flex: 10;
    padding:5px;
    margin-left: 50px;
    margin-right: 50px;
    margin-top: 20px;
    margin-bottom: 10px;
    width: 50%;
}

input[type="submit"]{
    flex: 2;
    margin-left: 50px;
    margin-right: 50px;
    margin-top: 20px;
    margin-bottom: 10px;
}

</style>