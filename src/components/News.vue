<template>
    <v-container>
        <v-row class="list__cafes-title">
            <v-col>
                <h2 class="text-center text-h3 py-3">Новости</h2>
            </v-col>
        </v-row>
        <v-row class="list__cafes-content">
            <v-col md="6" v-for="news in News" :key="news.id">
                <v-card>
                    <v-card-title>
                        <h3 class="text-h5">{{ news.title }}</h3>
                    </v-card-title>
                    <v-card-text>
                        <p class="text-body-1">{{ news.content }}</p>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'News',
    data() {
        return {
            News: [
                {
                    id: 0,
                    title: 'Сегодня в первый день работаем с Vuetify!',
                    content: 'Очень интересная вещь, мне понравилась, создал сначала проект VUE3, после уже установил в проект Vuetify!',
                },
                {
                    id: 1,
                    title: 'Создаем Таск-менеджер!',
                    content: 'Работа начата 13.03.24. Постараемся делать в быстром темпе!'
                },
                {
                    id: 2,
                    title: 'Заголовок новости',
                    content: 'Текст новости',
                },
                {
                    id: 3,
                    title: 'Заголовок новости',
                    content: 'Текст новости',
                }
            ]
        }
    },
}
</script>