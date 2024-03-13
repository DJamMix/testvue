<template>
    <v-row class="list__cafes-title">
        <v-col>
            <h2 class="text-center text-h3 py-3">Задачи</h2>
        </v-col>
    </v-row>
    <v-row class="list__cafes-title">
        <v-col>
            <h3 class="text-center text-h4 py-4">Создание задачи</h3>
        </v-col>
    </v-row>
    <v-container class="d-flex justify-center mb-6 flex-column">
        <v-container>
            <v-col md="8">
                <v-textarea label="Заголовок задачи" rows="1"></v-textarea>
            </v-col>
            <v-col md="8">
                <v-textarea label="Текст задачи"></v-textarea>
            </v-col>
        </v-container>
        <v-container class="d-flex ml-4 justify-start">
            <v-btn>Создать</v-btn>
        </v-container>
    </v-container>
    <v-row class="list__cafes-title">
        <v-col>
            <h3 class="text-center text-h4 py-4">Список задач</h3>
        </v-col>
    </v-row>
    <v-container>
        <v-row class="list__cafes-content">
            <v-col class="" md="12" v-for="task in tasks" :key="task.id">
                <v-card>
                    <v-card-title>
                        <h3 class="text-h5">{{ task.title }}</h3>
                    </v-card-title>
                    <v-card-text>
                        <p class="text-body-1">{{ task.content }}</p>
                    </v-card-text>
                    <div class="pa-2 d-flex ga-2 justify-end">
                        <v-btn @click="showEdit()">Редактировать</v-btn>
                        <v-btn>Удалить</v-btn>
                    </div>
                    <v-card v-if="showEditTask">
                        <v-row class="list__cafes-title">
                            <v-col>
                                <h3 class="text-center text-h5 py-5">Редактирование задачи</h3>
                            </v-col>
                        </v-row>
                        <v-col md="8">
                            <input class="width100" type="text b-blue" v-model="task.title">
                        </v-col>
                        <v-col md="8">
                            <textarea v-model="task.content" class="width100" rows="5"></textarea>
                        </v-col>
                        <div class="pa-2">
                            <v-btn>Сохранить</v-btn> 
                        </div>
                    </v-card>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'Tasks',
    components: {

    },
    data() {
        return {
            tasks: [
                {
                    id: 0,
                    title: 'Заголовок задачи',
                    content: 'Текст задачи',
                },
                {
                    id: 1,
                    title: 'Заголовок задачи',
                    content: 'Текст задачи',
                },
                {
                    id: 2,
                    title: 'Заголовок задачи',
                    content: 'Текст задачи',
                },
            ],
            createtask: {
                title: '',
                content: '',
            },
            showEditTask: false,
        }
    },
    methods: {
        showEdit()
        {
            if(this.showEditTask == false) {
                this.showEditTask = true
            } else {
                this.showEditTask = false
            }
        }
    }
}
</script>

<style lang="sass" scoped>
    input
        border: 1px solid grey
        border-radius: 10px
        font-size: 16px
        padding: 5px
        outline: none
    textarea
        border: 1px solid grey
        border-radius: 10px
        font-size: 16px
        padding: 5px
        outline: none
    .width100
        width: 100%
</style>