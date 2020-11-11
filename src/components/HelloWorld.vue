<template>
    <div>
        <input type="text" v-model="toDoText" >
        <button @click="addToDo"> add toDO</button>
        <div v-for="(item, i) in toDoList" :key="i" class="d-flex">
            <p>{{i+1+") " +item}}</p>
            <button @click="removeElement(i)">REMOVE</button>

        </div>
    </div>
</template>

<script>
    export default {
        name: "HelloWorld",
        data() {
            return {
                toDoList: [
                    "Помити посуд",
                    "Пропилососити",
                    "Приготовити їжу",
                    "Сходити за покупками",
                ],
                toDoText: "",
            }
        },
        methods: {
            addToDo(){
                this.toDoList.push(this.toDoText);
            },
            removeElement(id){
                this.toDoList.splice(id,1)
            }

        }

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.d-flex{
    display: flex;
    justify-content: center;
}
    button{
        margin: 10px;
    }
</style>
