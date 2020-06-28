<template>
    <div class="container">
        <div id="taskApp" class="col-sm-8 col-sm-offset-2">
            <h1>{{title}}</h1>

            <div class="panel panel-default">
                <h3 class="text-center">Add a New Task</h3>
                <form v-on:submit="addTask" class="app-form">
                    <input type="text" class="form-control" v-model="tasks.title">
                    <input type="submit" value="Add" class="btn btn-block btn-primary">
                </form>
            </div>

            <table class="table">
                <thead>
                <tr>
                    <th>Dne</th> <th>Task</th> <th>Delete</th>
                </tr>
                </thead>
                <tbody>
                    <tr v-for="task in tasks" :key="task.title">
                        <td>
                            <input type="checkbox" v-model="task.done">
                        </td>
                        <td>
                            <span :class="{taskDone: task.done}">
                              {{ task.title }}
                            </span>
                        </td>
                        <td>
                            <button v-on:click="deleteTask(task)" class="btn btn-block btn-danger">
                                Delete
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Task',
        props:{
            title: String
        },
        data() {
            return {
                tasks: [
                    { title: 'Homeworks', done: true },
                    { title: 'Workshops University', done: false },
                    { title: 'Pay Services', done: false }
                ]
            }
        },
        methods: {
            addTask: function (e) {
                e.preventDefault();
                this.tasks.push({
                    title: this.tasks.title,
                    done: false
                });
                this.tasks.title = '';
            },
            deleteTask: function (task) {
                this.tasks.splice(
                    this.tasks.indexOf(task),
                    1
                )
            }
        }
    }
</script>

<style scoped>
    .app-form input{
        border-radius: 0;
    }
    .taskDone {
        text-decoration: line-through;
    }
</style>
