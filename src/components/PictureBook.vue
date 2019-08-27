<template>
    <v-app>
        <v-card style="top:-470px">
            <v-layout wrap align-center justify-start>
                <v-flex>
                    <v-col
                    v-for="datum in data"
                    :key="datum.name"
                    >
                        <v-card class="data">
                            <v-list-item>
                                <v-list-item-avatar
                                size="125"
                                tile
                                >
                                    <v-img :src="datum.image"></v-img>
                                </v-list-item-avatar>
                                <v-list-item-content class="align-self-start">
                                    <v-list-item-title
                                    v-text="datum.name"
                                    ></v-list-item-title>

                                    <v-list-item-subtitle>
                                        番号:{{datum.number}} 段階:{{datum.stage}}
                                    </v-list-item-subtitle>
                                        <div>
                                            タイプ:{{datum.type1}} {{datum.type2}}
                                        </div>
                                        <div>
                                            たかさ:{{datum.height}}m おもさ:{{datum.weight}}kg
                                        </div>
                                        <div>
                                            性別:{{datum.genderv}}
                                        </div>
                                        <div>
                                            タマゴグループ:{{datum.egg1}} {{datum.egg2}}
                                        </div>
                                        <div>
                                            努力値:{{datum.effort1v}} {{datum.effort2v}}
                                        </div>
                                </v-list-item-content>

                                <v-card-actions>
                                    <v-btn @click="datum.dialog=true">種族値を見る</v-btn>
                                </v-card-actions>

                                <v-dialog v-model="datum.dialog" scrollable max-width="80%">
                                    <v-card>
                                        <v-card-title>種族値 ({{datum.name}})</v-card-title>
                                        <v-divider></v-divider>
                                        <v-card-text height="300px">
                                            HP:{{datum.hp}}
                                            <v-spacer></v-spacer>
                                            Attack:{{datum.attack}}
                                            <v-spacer></v-spacer>
                                            Defense:{{datum.defense}}
                                            <v-spacer></v-spacer>
                                            Special Attack:{{datum.spattack}}
                                            <v-spacer></v-spacer>
                                            Special Defense:{{datum.spdefense}}
                                            <v-spacer></v-spacer>
                                            Speed:{{datum.speed}}
                                            <v-spacer></v-spacer>
                                            Sum:{{datum.sum}}
                                        </v-card-text>
                                    </v-card>
                                </v-dialog>
                            </v-list-item>
                        </v-card>
                    </v-col>
                </v-flex>
            </v-layout>
        </v-card>
    </v-app>
</template>

<script>
export default {
    props:["data"],
    data: function() {
        return {

        }
    },
    methods: {

    }
}
</script>

<style>
.data {
    margin: -10px;
}
</style>
