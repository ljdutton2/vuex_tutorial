<template>
    <div>
        <h3>
            Add Todo
        </h3>
        <div class="add">
            <form @submit="onSubmit">
                
                <input type="text" v-model="title" placeholder="add Todo">
                <input type="submit" value="submit">
                <i class="fas fa-unicorn"></i>
                
            </form>
        </div>
    </div>
</template>

<script scoped>
    import {mapActions} from 'vuex';
    export default {
        name: "AddTodo",
        data(){
            return {title:''}
        },
        methods: {
            ...mapActions(['addTodo']),
            onSubmit(e) {
                e.preventDefault();
                this.addTodo(this.title)
            }
        }
    }
</script>
<style>
    form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #41b883;
  outline: 0;
}
input[type="submit"] {
  flex: 2;
  background: #41b883;
  color: #fff;
  border: 1px #41b883 solid;
  cursor: pointer;
}
</style>