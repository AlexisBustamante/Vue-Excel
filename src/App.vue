<template>
<v-app>
    <v-app-bar app dark>
        <div class="d-flex align-center">
            <v-img alt="Vuetify Logo" class="shrink mr-2" contain src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png" transition="scale-transition" width="40" />

            <v-img alt="Vuetify Name" class="shrink mt-1 hidden-sm-and-down" contain min-width="100" src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png" width="100" />
        </div>

        <v-spacer></v-spacer>

        <v-btn href="https://github.com/AlexisBustamante" target="_blank" text>
            <span class="mr-2">Latest Release</span>
            <v-icon>mdi-open-in-new</v-icon>
        </v-btn>
    </v-app-bar>

    <v-main>

        <v-container grid-list-xs>
            <v-col cols="6" xs="12" sm="12" md="6" xl="6">
            </v-col>
            <v-card dark>
                <v-card-text>
                    <v-row>
                        <v-col>
                            <v-text-field v-model="filename"  label="FileName" :rules="rules" hide-details="auto"></v-text-field>
                        </v-col>
                        <v-col>

                            <v-btn color="green" dark @click="exportExcel">Exportar</v-btn>

                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
            <v-row>
                <v-col cols="6" xs="12" sm="12" md="6" xl="6">
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                    <v-data-table dark dense :headers="headers" :items="desserts" item-key="name"></v-data-table>
                </v-col>
            </v-row>

            <v-row>

            </v-row>

        </v-container>
    </v-main>
</v-app>
</template>

<script>
import XLSX from 'xlsx';

export default {
    name: 'App',
    components: {

    },

    data: () => ({
        bookType: 'xlsx',
        filename: 'fileName',
        itemsE: ['xlsx', 'csv', 'txt'],
        select: ['xlsx'],
        rules: [
            value => !!value || 'Required.',
            value => (value && value.length >= 3) || 'Min 4 characters',
        ],
        desserts: [{
                name: 'Frozen Yogurt',
                calories: 159,
                fat: 6.0,
                carbs: 24,
                protein: 4.0,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%',
            },
            {
                name: 'Eclair',
                calories: 262,
                fat: 16.0,
                carbs: 23,
                protein: 6.0,
                iron: '7%',
            },
            {
                name: 'Cupcake',
                calories: 305,
                fat: 3.7,
                carbs: 67,
                protein: 4.3,
                iron: '8%',
            },
            {
                name: 'Gingerbread',
                calories: 356,
                fat: 16.0,
                carbs: 49,
                protein: 3.9,
                iron: '16%',
            },
            {
                name: 'Jelly bean',
                calories: 375,
                fat: 0.0,
                carbs: 94,
                protein: 0.0,
                iron: '0%',
            },
            {
                name: 'Lollipop',
                calories: 392,
                fat: 0.2,
                carbs: 98,
                protein: 0,
                iron: '2%',
            },
            {
                name: 'Honeycomb',
                calories: 408,
                fat: 3.2,
                carbs: 87,
                protein: 6.5,
                iron: '45%',
            },
            {
                name: 'Donut',
                calories: 452,
                fat: 25.0,
                carbs: 51,
                protein: 4.9,
                iron: '22%',
            },
            {
                name: 'KitKat',
                calories: 518,
                fat: 26.0,
                carbs: 65,
                protein: 7,
                iron: '6%',
            },
        ],
        headers: [{
                text: 'Dessert (100g serving)',
                align: 'start',
                sortable: false,
                value: 'name',
            },
            {
                text: 'Calories',
                value: 'calories'
            },
            {
                text: 'Fat (g)',
                value: 'fat'
            },
            {
                text: 'Carbs (g)',
                value: 'carbs'
            },
            {
                text: 'Protein (g)',
                value: 'protein'
            },
            {
                text: 'Iron (%)',
                value: 'iron'
            },
        ],
    }),
    methods: {
        exportExcel:function() {
            let data = XLSX.utils.json_to_sheet(this.desserts)
            const workbook = XLSX.utils.book_new()
            XLSX.utils.book_append_sheet(workbook, data, this.filename)
            XLSX.writeFile(workbook, `${this.filename}.xlsx`)
        }
    },
};
</script>
