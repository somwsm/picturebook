<template>
    <v-app>
        <v-card class="horizontal">
            <v-container fluid grid-list-md pa-2>
                <v-layout>
                    <v-card class="cards">
                        <v-card-title>
                            地域
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="regioncd" :mandatory="false">
                                <v-radio :label="`カントー(${count[0][0].toString()})`" value="カントー"></v-radio>
                                <v-radio :label="`ジョウト(${count[0][1].toString()})`" value="ジョウト"></v-radio>
                                <v-radio :label="`ホウエン(${count[0][2].toString()})`" value="ホウエン"></v-radio>
                                <v-radio :label="`シンオウ(${count[0][3].toString()})`" value="シンオウ"></v-radio>
                                <v-radio :label="`イッシュ(${count[0][4].toString()})`" value="イッシュ"></v-radio>
                                <v-radio :label="`カロス(${count[0][5].toString()})`" value="カロス"></v-radio>
                                <v-radio :label="`アローラ(${count[0][6].toString()})`" value="アローラ"></v-radio>
                            </v-radio-group>
                        </v-card-text>
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            タイプ1
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="type1cd" :mandatory="false">
                                <v-radio :label="`ノーマル(${count[1][0].toString()})`" value="ノーマル"></v-radio>
                                <v-radio :label="`ほのお(${count[1][1].toString()})`" value="ほのお"></v-radio>
                                <v-radio :label="`みず(${count[1][2].toString()})`" value="みず"></v-radio>
                                <v-radio :label="`くさ(${count[1][3].toString()})`" value="くさ"></v-radio>
                                <v-radio :label="`でんき(${count[1][4].toString()})`" value="でんき"></v-radio>
                                <v-radio :label="`こおり(${count[1][5].toString()})`" value="こおり"></v-radio>
                                <v-radio :label="`かくとう(${count[1][6].toString()})`" value="かくとう"></v-radio>
                                <v-radio :label="`どく(${count[1][7].toString()})`" value="どく"></v-radio>
                                <v-radio :label="`じめん(${count[1][8].toString()})`" value="じめん"></v-radio>
                                <v-radio :label="`ひこう(${count[1][9].toString()})`" value="ひこう"></v-radio>
                                <v-radio :label="`エスパー(${count[1][10].toString()})`" value="エスパー"></v-radio>
                                <v-radio :label="`むし(${count[1][11].toString()})`" value="むし"></v-radio>
                                <v-radio :label="`いわ(${count[1][12].toString()})`" value="いわ"></v-radio>
                                <v-radio :label="`ゴースト(${count[1][13].toString()})`" value="ゴースト"></v-radio>
                                <v-radio :label="`ドラゴン(${count[1][14].toString()})`" value="ドラゴン"></v-radio>
                                <v-radio :label="`あく(${count[1][15].toString()})`" value="あく"></v-radio>
                                <v-radio :label="`はがね(${count[1][16].toString()})`" value="はがね"></v-radio>
                                <v-radio :label="`フェアリー(${count[1][17].toString()})`" value="フェアリー"></v-radio>
                            </v-radio-group>
                        </v-card-text>
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            タイプ2
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="type2cd" :mandatory="false">
                                <v-radio :label="`ノーマル(${count[2][0].toString()})`" value="ノーマル"></v-radio>
                                <v-radio :label="`ほのお(${count[2][1].toString()})`" value="ほのお"></v-radio>
                                <v-radio :label="`みず(${count[2][2].toString()})`" value="みず"></v-radio>
                                <v-radio :label="`くさ(${count[2][3].toString()})`" value="くさ"></v-radio>
                                <v-radio :label="`でんき(${count[2][4].toString()})`" value="でんき"></v-radio>
                                <v-radio :label="`こおり(${count[2][5].toString()})`" value="こおり"></v-radio>
                                <v-radio :label="`かくとう(${count[2][6].toString()})`" value="かくとう"></v-radio>
                                <v-radio :label="`どく(${count[2][7].toString()})`" value="どく"></v-radio>
                                <v-radio :label="`じめん(${count[2][8].toString()})`" value="じめん"></v-radio>
                                <v-radio :label="`ひこう(${count[2][9].toString()})`" value="ひこう"></v-radio>
                                <v-radio :label="`エスパー(${count[2][10].toString()})`" value="エスパー"></v-radio>
                                <v-radio :label="`むし(${count[2][11].toString()})`" value="むし"></v-radio>
                                <v-radio :label="`いわ(${count[2][12].toString()})`" value="いわ"></v-radio>
                                <v-radio :label="`ゴースト(${count[2][13].toString()})`" value="ゴースト"></v-radio>
                                <v-radio :label="`ドラゴン(${count[2][14].toString()})`" value="ドラゴン"></v-radio>
                                <v-radio :label="`あく(${count[2][15].toString()})`" value="あく"></v-radio>
                                <v-radio :label="`はがね(${count[2][16].toString()})`" value="はがね"></v-radio>
                                <v-radio :label="`フェアリー(${count[2][17].toString()})`" value="フェアリー"></v-radio>
                            </v-radio-group>
                        </v-card-text>
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            たかさ
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="heightcd" :mandatory="false">
                                <v-radio :label="`~0.4(${count[3][0].toString()})`" value="1"></v-radio>
                                <v-radio :label="`0.5~0.9(${count[3][1].toString()})`" value="2"></v-radio>
                                <v-radio :label="`1.0~1.4(${count[3][2].toString()})`" value="3"></v-radio>
                                <v-radio :label="`1.5~1.9(${count[3][3].toString()})`" value="4"></v-radio>
                                <v-radio :label="`2.0~2.4(${count[3][4].toString()})`" value="5"></v-radio>
                                <v-radio :label="`2.5~2.9(${count[3][5].toString()})`" value="6"></v-radio>
                                <v-radio :label="`3.0~3.9(${count[3][6].toString()})`" value="7"></v-radio>
                                <v-radio :label="`4.0~5.9(${count[3][7].toString()})`" value="8"></v-radio>
                                <v-radio :label="`6.0~(${count[3][8].toString()})`" value="9"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-spacer></v-spacer>

                    <v-card class="cards">
                        <v-card-title>
                            おもさ
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="weightcd" :mandatory="false">
                                <v-radio :label="`~9.9(${count[4][0].toString()})`" value="1"></v-radio>
                                <v-radio :label="`10.0~29.9(${count[4][1].toString()})`" value="2"></v-radio>
                                <v-radio :label="`30.0~59.9(${count[4][2].toString()})`" value="3"></v-radio>
                                <v-radio :label="`60.0~99.9(${count[4][3].toString()})`" value="4"></v-radio>
                                <v-radio :label="`100.0~149.9(${count[4][4].toString()})`" value="5"></v-radio>
                                <v-radio :label="`150.0~209.9(${count[4][5].toString()})`" value="6"></v-radio>
                                <v-radio :label="`210.0~279.9(${count[4][6].toString()})`" value="7"></v-radio>
                                <v-radio :label="`280.0~359.9(${count[4][7].toString()})`" value="8"></v-radio>
                                <v-radio :label="`360.0~(${count[4][8].toString()})`" value="9"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            せいべつ
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="gendercd" :mandatory="false">
                                <v-radio :label="`オスメス(${count[5][0].toString()})`" value="MF"></v-radio>
                                <v-radio :label="`オスのみ(${count[5][1].toString()})`" value="M"></v-radio>
                                <v-radio :label="`メスのみ(${count[5][2].toString()})`" value="F"></v-radio>
                                <v-radio :label="`せいべつなし(${count[5][3].toString()})`" value="GL"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>
                    
                    <v-card class="cards">
                        <v-card-title>
                            段階
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="stagecd" :mandatory="false">
                                <v-radio :label="`1(${count[6][0].toString()})`" value="1"></v-radio>
                                <v-radio :label="`2(${count[6][1].toString()})`" value="2"></v-radio>
                                <v-radio :label="`3(${count[6][2].toString()})`" value="3"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            タマゴグループ1
                        </v-card-title>
                        <v-card-text class="radio">
                             <v-radio-group v-model="egg1cd" :mandatory="false">
                                <v-radio :label="`かいじゅう(${count[7][0].toString()})`" value="かいじゅう"></v-radio>
                                <v-radio :label="`こうぶつ(${count[7][1].toString()})`" value="こうぶつ"></v-radio>
                                <v-radio :label="`しょくぶつ(${count[7][2].toString()})`" value="しょくぶつ"></v-radio>
                                <v-radio :label="`すいちゅう1(${count[7][3].toString()})`" value="すいちゅう1"></v-radio>
                                <v-radio :label="`すいちゅう2(${count[7][4].toString()})`" value="すいちゅう2"></v-radio>
                                <v-radio :label="`すいちゅう3(${count[7][5].toString()})`" value="すいちゅう3"></v-radio>
                                <v-radio :label="`ドラゴン(${count[7][6].toString()})`" value="ドラゴン"></v-radio>
                                <v-radio :label="`ひこう(${count[7][7].toString()})`" value="ひこう"></v-radio>
                                <v-radio :label="`ひとがた(${count[7][8].toString()})`" value="ひとがた"></v-radio>
                                <v-radio :label="`ふていけい(${count[7][9].toString()})`" value="ふていけい"></v-radio>
                                <v-radio :label="`むし(${count[7][10].toString()})`" value="むし"></v-radio>
                                <v-radio :label="`フェアリー(${count[7][11].toString()})`" value="ようせい"></v-radio>
                                <v-radio :label="`りくじょう(${count[7][12].toString()})`" value="りくじょう"></v-radio>
                                <v-radio :label="`メタモン(${count[7][13].toString()})`" value="メタモン"></v-radio>
                                <v-radio :label="`みはっけん(${count[7][14].toString()})`" value="みはっけん"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            タマゴグループ2
                        </v-card-title>
                        <v-card-text class="radio">
                             <v-radio-group v-model="egg2cd" :mandatory="false">
                                <v-radio :label="`かいじゅう(${count[8][0].toString()})`" value="かいじゅう"></v-radio>
                                <v-radio :label="`こうぶつ(${count[8][1].toString()})`" value="こうぶつ"></v-radio>
                                <v-radio :label="`しょくぶつ(${count[8][2].toString()})`" value="しょくぶつ"></v-radio>
                                <v-radio :label="`すいちゅう1(${count[8][3].toString()})`" value="すいちゅう1"></v-radio>
                                <v-radio :label="`すいちゅう2(${count[8][4].toString()})`" value="すいちゅう2"></v-radio>
                                <v-radio :label="`すいちゅう3(${count[8][5].toString()})`" value="すいちゅう3"></v-radio>
                                <v-radio :label="`ドラゴン(${count[8][6].toString()})`" value="ドラゴン"></v-radio>
                                <v-radio :label="`ひこう(${count[8][7].toString()})`" value="ひこう"></v-radio>
                                <v-radio :label="`ひとがた(${count[8][8].toString()})`" value="ひとがた"></v-radio>
                                <v-radio :label="`ふていけい(${count[8][9].toString()})`" value="ふていけい"></v-radio>
                                <v-radio :label="`むし(${count[8][10].toString()})`" value="むし"></v-radio>
                                <v-radio :label="`ようせい(${count[8][11].toString()})`" value="ようせい"></v-radio>
                                <v-radio :label="`りくじょう(${count[8][12].toString()})`" value="りくじょう"></v-radio>
                                <v-radio :label="`メタモン(${count[8][13].toString()})`" value="メタモン"></v-radio>
                                <v-radio :label="`みはっけん(${count[8][14].toString()})`" value="みはっけん"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            努力値1
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="effort1cd" :mandatory="false">
                                <v-radio :label="`HP(${count[9][0].toString()})`" value="HP"></v-radio>
                                <v-radio :label="`攻撃(${count[9][1].toString()})`" value="Atk"></v-radio>
                                <v-radio :label="`防御(${count[9][2].toString()})`" value="Def"></v-radio>
                                <v-radio :label="`特攻(${count[9][3].toString()})`" value="SpAtk"></v-radio>
                                <v-radio :label="`特防(${count[9][4].toString()})`" value="SpDef"></v-radio>
                                <v-radio :label="`素早さ(${count[9][5].toString()})`" value="Speed"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>

                    <v-card class="cards">
                        <v-card-title>
                            努力値2
                        </v-card-title>
                        <v-card-text class="radio">
                            <v-radio-group v-model="effort2cd" :mandatory="false">
                                <v-radio :label="`HP(${count[10][0].toString()})`" value="HP"></v-radio>
                                <v-radio :label="`攻撃(${count[10][1].toString()})`" value="Atk"></v-radio>
                                <v-radio :label="`防御(${count[10][2].toString()})`" value="Def"></v-radio>
                                <v-radio :label="`特攻(${count[10][3].toString()})`" value="SpAtk"></v-radio>
                                <v-radio :label="`特防(${count[10][4].toString()})`" value="SpDef"></v-radio>
                                <v-radio :label="`素早さ(${count[10][5].toString()})`" value="Speed"></v-radio>
                            </v-radio-group>
                        </v-card-text> 
                    </v-card>
                </v-layout>
            </v-container>
        </v-card>
    </v-app>
</template>

<script>
export default {
    props:["pokemon", "data", "count", "region", "type1", "type2", "height", "weight", "gender", "stage", "egg1", "egg2", "effort1", "effort2"],
    data: function() {
        return {
            
        }
    },
    computed: {
        regioncd: {
            get () {
                return this.region;
            },
            set (newregion) {
                this.$emit('changere', newregion);
            }
        },
        type1cd: {
            get () {
                return this.type1;
            },
            set (newtype1) {
                this.$emit('changety1', newtype1);
            }
        },
        type2cd: {
            get () {
                return this.type2;
            },
            set (newtype2) {
                this.$emit('changety2', newtype2);
            }
        },
        heightcd: {
            get () {
                return this.height;
            },
            set (newheight) {
                this.$emit('changehei', newheight);
            }
        },
        weightcd: {
            get () {
                return this.weight;
            },
            set (newweight) {
                this.$emit('changewei', newweight);
            }
        },
        gendercd: {
            get () {
                return this.gender;
            },
            set (newgender) {
                this.$emit('changegen', newgender);
            }
        },
        stagecd: {
            get () {
                return this.stage;
            },
            set (newstage) {
                this.$emit('changesta', newstage);
            }
        },
        egg1cd: {
            get () {
                return this.egg1;
            },
            set (newegg1) {
                this.$emit('changeegg1', newegg1);
            }
        },
        egg2cd: {
            get () {
                return this.egg2;
            },
            set (newegg2) {
                this.$emit('changeegg2', newegg2);
            }
        },
        effort1cd: {
            get () {
                return this.effort1;
            },
            set (neweffort1) {
                this.$emit('changeeff1', neweffort1);
            }
        },
        effort2cd: {
            get () {
                return this.effort2;
            },
            set (neweffort2) {
                this.$emit('changeeff2', neweffort2);
            }
        },
    }
}
</script>

<style>
.horizontal {
    overflow-x: auto;
    white-space: nowrap;
    -webkit-overflow-scrolling: touch;
}
.cards{
    display: inline-block;
    margin-right: 5px;
}
.radio{
    height: 160px;
    overflow: scroll;
}
</style>
