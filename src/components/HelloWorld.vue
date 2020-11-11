<template>
    <div>
<div class="todo" v-for="(todo, i) in todolist" :key="`${i} -- ${todo}`">
    <p>{{i + 1}}: {{todo}}</p>
    <button @click="deleteTodo(i)">remove</button>
</div>
        <div class="enterTodo">
        <input type="text" v-model="todoForm">
        <button @click="addTodo">ADD TODO</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        data() {
            return {
                todolist: [
                    ' має бути масив тудушок який ми ітеруємо',
                    ' створити input та кнопку - при вводі в інпут та при кліці на кнопку add маємо пушити в масив нову тудушку',
                    ' біля кожної тудушки має бути кнопка remove - при кліці на яку ремуваємо конкретний айтем',
                    ' Стилі по бажанню'
                ],
                todoForm: ''
            }
        },
        methods: {
            addTodo () {
               this.todolist.push(this.todoForm)
            },

            deleteTodo (i) {
                this.todolist.splice(i, 1)
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo {
    text-align: left;
    margin-left: 30px;
}
    .enterTodo {
        margin-top: 60px;
    }

    div :hover {
        background-color: aqua;
    }
</style>
