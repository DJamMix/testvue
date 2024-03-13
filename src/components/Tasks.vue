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
        <v-form fast-fail @submit.prevent>
            <v-text-field
                v-model="firstName"
                label="Название задачи"
            ></v-text-field>

            <v-select
                :items="statuses"
                label="Выберите статус задачи"
                required
            >
            </v-select>

            <v-textarea
                v-model="lastName"
                label="Опишите задачу"
            ></v-textarea>

            <v-btn class="mt-2" type="submit" block>Создать задачу</v-btn>
        </v-form>
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
                    <div class="d-flex justify-space-between">
                        <v-card-title>
                            <h3 class="text-h5">{{ task.title }}</h3>
                        </v-card-title>
                        <v-card-title>
                            <h3 class="text-h6">Статус: Новое</h3>
                        </v-card-title>
                    </div>
                    <v-card-title>
                        <h3 class="text-h6">Дата: 00.00.0000</h3>
                    </v-card-title>
                    <v-card-text>
                        <p class="text-body-1">{{ task.content }}</p>
                    </v-card-text>
                    <div class="pa-2 d-flex ga-2 justify-end">
                        <v-btn @click="showEdit(task.id)">Редактировать</v-btn>
                        <v-btn>Удалить</v-btn>
                    </div>
                    <v-card :id="'showEdit' + task.id" class="pa-5 d-none">
                        <v-form fast-fail @submit.prevent>
                            <v-text-field
                                v-model="task.title"
                                label="Изменить название задачи"
                            ></v-text-field>

                            <v-select
                                :items="statuses"
                                label="Изменить статус задачи"
                                required
                            >
                            </v-select>

                            <v-textarea
                                v-model="task.content"
                                label="Можете изменить содержимое задачи"
                            ></v-textarea>

                            <v-btn class="mt-2" type="submit" block>Сохранить</v-btn>
                        </v-form>
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
            showEditTask: '',
            statuses: [
                'Новое',
                'В работе',
                'Отменено',
                'Выполнено'
            ],
        }
    },
    methods: {
        showEdit(id)
        {
            let idblock = 'showEdit' + id;
            this.$el.setAttribute('id', idblock);
            if(this.$el.classList.contains('d-none')) {
                document.getElementById(idblock).classList.remove('d-none');
            } else {
                document.getElementById(idblock).classList.add('d-none');
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