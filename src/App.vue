<template>
    <v-app>
        <div class="title">
            <h3>
                ポケモン図鑑
            </h3>
        </div>
        <v-layout>
            <v-flex>
                <refine 
                :pokemon="pokemon"
                :data="data" 
                :count="count"
                :region="region" 
                :type1="type1" 
                :type2="type2"
                :height="height"
                :weight="weight"
                :gender="gender"
                :stage="stage"
                :egg1="egg1"
                :egg2="egg2"
                :effort1="effort1"
                :effort2="effort2"
                @changere="changere" 
                @changety1="changety1" 
                @changety2="changety2"
                @changehei="changehei"
                @changewei="changewei"
                @changegen="changegen"
                @changesta="changesta"
                @changeegg1="changeegg1"
                @changeegg2="changeegg2"
                @changeeff1="changeeff1"
                @changeeff2="changeeff2"
                ></refine>

                <v-btn 
                @click="apply()"
                class="button">絞り込み</v-btn>
                <v-btn 
                @click="clear()"
                class="button">リセット</v-btn>

                <picturebook :data="data"></picturebook>
            </v-flex>
        </v-layout>
    </v-app>
</template>

<script>
import pokemon from "./pokemon.json";
import Refine from "./components/Refine.vue"
import Picturebook from "./components/PictureBook.vue"

var data = pokemon["individual"];

function counter(data) {
    var size = data.length;
    var i;
    var countr = [];
    var countt1 = [];
    var countt2 = [];
    var counthe = [];
    var countwe = [];
    var countge = [];
    var countst = [];
    var counteg1 = [];
    var counteg2 = [];
    var countef1 = [];
    var countef2 = [];
    
    for(i = 0; i < 18; i++){
        if(i < 3){
            countst[i] = 0;
        }
        if(i < 4){
            countge[i] = 0;
        }
        if(i < 6){
            countef1[i] = 0;
            countef2[i] = 0;
        } 
        if(i < 7){
            countr[i] = 0;
        } 
        if(i < 9){
            counthe[i] = 0;
            countwe[i] = 0;
        }
        if(i < 15){
            counteg1[i] = 0;
            counteg2[i] = 0;
        }
        countt1[i] = 0;
        countt2[i] = 0;
    }

    for(i = 0; i < size; i++){
        switch(data[i].region){
            case "カントー":
                countr[0]++;
                break;
            case "ジョウト":
                countr[1]++;
                break;
            case "ホウエン":
                countr[2]++;
                break;
            case "シンオウ":
                countr[3]++;
                break;
            case "イッシュ":
                countr[4]++;
                break;
            case "カロス":
                countr[5]++;
                break;
            case "アローラ":
                countr[6]++;
                break; 
        }

        switch(data[i].type1){
            case "ノーマル":
                countt1[0]++;
                break;
            case "ほのお":
                countt1[1]++;
                break;
            case "みず":
                countt1[2]++;
                break;
            case "くさ":
                countt1[3]++;
                break;
            case "でんき":
                countt1[4]++;
                break;
            case "こおり":
                countt1[5]++;
                break;
            case "かくとう":
                countt1[6]++;
                break; 
            case "どく":
                countt1[7]++;
                break;
            case "じめん":
                countt1[8]++;
                break;
            case "ひこう":
                countt1[9]++;
                break;
            case "エスパー":
                countt1[10]++;
                break;
            case "むし":
                countt1[11]++;
                break;
            case "いわ":
                countt1[12]++;
                break;
            case "ゴースト":
                countt1[13]++;
                break;
            case "ドラゴン":
                countt1[14]++;
                break;
            case "あく":
                countt1[15]++;
                break;
            case "はがね":
                countt1[16]++;
                break;
            case "フェアリー":
                countt1[17]++;
                break;
        }

        switch(data[i].type2){
            case "ノーマル":
                countt2[0]++;
                break;
            case "ほのお":
                countt2[1]++;
                break;
            case "みず":
                countt2[2]++;
                break;
            case "くさ":
                countt2[3]++;
                break;
            case "でんき":
                countt2[4]++;
                break;
            case "こおり":
                countt2[5]++;
                break;
            case "かくとう":
                countt2[6]++;
                break; 
            case "どく":
                countt2[7]++;
                break;
            case "じめん":
                countt2[8]++;
                break;
            case "ひこう":
                countt2[9]++;
                break;
            case "エスパー":
                countt2[10]++;
                break;
            case "むし":
                countt2[11]++;
                break;
            case "いわ":
                countt2[12]++;
                break;
            case "ゴースト":
                countt2[13]++;
                break;
            case "ドラゴン":
                countt2[14]++;
                break;
            case "あく":
                countt2[15]++;
                break;
            case "はがね":
                countt2[16]++;
                break;
            case "フェアリー":
                countt2[17]++;
                break;
        }

        if(data[i].height < 0.5){
            counthe[0]++;
        }else if(0.5 <= data[i].height && data[i].height< 1.0){
            counthe[1]++;
        }else if(1.0 <= data[i].height && data[i].height< 1.5){
            counthe[2]++;
        }else if(1.5 <= data[i].height && data[i].height< 2.0){
            counthe[3]++;
        }else if(2.0 <= data[i].height && data[i].height< 2.5){
            counthe[4]++;
        }else if(2.5 <= data[i].height && data[i].height< 3.0){
            counthe[5]++;
        }else if(3.0 <= data[i].height && data[i].height< 4.0){
            counthe[6]++;
        }else if(4.0 <= data[i].height && data[i].height< 6.0){
            counthe[7]++;
        }else if(6.0 <= data[i].height){
            counthe[8]++;
        }

        if(data[i].weight < 10){
            countwe[0]++;
        }else if(10 <= data[i].weight && data[i].weight< 30){
            countwe[1]++;
        }else if(30 <= data[i].weight && data[i].weight< 60){
            countwe[2]++;
        }else if(60 <= data[i].weight && data[i].weight< 100){
            countwe[3]++;
        }else if(100 <= data[i].weight && data[i].weight< 150){
            countwe[4]++;
        }else if(150 <= data[i].weight && data[i].weight< 210){
            countwe[5]++;
        }else if(210 <= data[i].weight && data[i].weight< 280){
            countwe[6]++;
        }else if(280 <= data[i].weight && data[i].weight< 360){
            countwe[7]++;
        }else if(360 <= data[i].weight){
            countwe[8]++;
        }

        switch(data[i].gender){
            case "MF":
                countge[0]++;
                break;
            case "M":
                countge[1]++;
                break;
            case "F":
                countge[2]++;
                break;
            case "GL":
                countge[3]++;
                break;
        }

        switch(data[i].stage){
            case 1:
                countst[0]++;
                break;
            case 2:
                countst[1]++;
                break;
            case 3:
                countst[2]++;
                break;
        }

        switch(data[i].egg1){
            case "かいじゅう":
                counteg1[0]++;
                break;
            case "こうぶつ":
                counteg1[1]++;
                break;
            case "しょくぶつ":
                counteg1[2]++;
                break;
            case "すいちゅう1":
                counteg1[3]++;
                break;
            case "すいちゅう2":
                counteg1[4]++;
                break;
            case "すいちゅう3":
                counteg1[5]++;
                break;
            case "ドラゴン":
                counteg1[6]++;
                break; 
            case "ひこう":
                counteg1[7]++;
                break;
            case "ひとがた":
                counteg1[8]++;
                break;
            case "ふていけい":
                counteg1[9]++;
                break;
            case "むし":
                counteg1[10]++;
                break;
            case "フェアリー":
                counteg1[11]++;
                break;
            case "りくじょう":
                counteg1[12]++;
                break;
            case "メタモン":
                counteg1[13]++;
                break;
            case "みはっけん":
                counteg1[14]++;
                break;
        }

        switch(data[i].egg2){
            case "かいじゅう":
                counteg2[0]++;
                break;
            case "こうぶつ":
                counteg2[1]++;
                break;
            case "しょくぶつ":
                counteg2[2]++;
                break;
            case "すいちゅう1":
                counteg2[3]++;
                break;
            case "すいちゅう2":
                counteg2[4]++;
                break;
            case "すいちゅう3":
                counteg2[5]++;
                break;
            case "ドラゴン":
                counteg2[6]++;
                break; 
            case "ひこう":
                counteg2[7]++;
                break;
            case "ひとがた":
                counteg2[8]++;
                break;
            case "ふていけい":
                counteg2[9]++;
                break;
            case "むし":
                counteg2[10]++;
                break;
            case "フェアリー":
                counteg2[11]++;
                break;
            case "りくじょう":
                counteg2[12]++;
                break;
            case "メタモン":
                counteg2[13]++;
                break;
            case "みはっけん":
                counteg2[14]++;
                break;
        }

        switch(data[i].effort1){
            case "HP":
                countef1[0]++;
                break;
            case "Atk":
                countef1[1]++;
                break;
            case "Def":
                countef1[2]++;
                break;
            case "SpAtk":
                countef1[3]++;
                break;
            case "SpDef":
                countef1[4]++;
                break;
            case "Speed":
                countef1[5]++;
                break;
        }

        switch(data[i].effort2){
            case "HP":
                countef2[0]++;
                break;
            case "Atk":
                countef2[1]++;
                break;
            case "Def":
                countef2[2]++;
                break;
            case "SpAtk":
                countef2[3]++;
                break;
            case "SpDef":
                countef2[4]++;
                break;
            case "Speed":
                countef2[5]++;
                break;
        }
    }

    var count = [countr, countt1, countt2, counthe, countwe, countge, countst, counteg1, counteg2, countef1, countef2];
    return count;
}

function initialState() {
    return {
        pokemon: pokemon,
        data: data,
        count: counter(data),
        refine: data,
        region:"",
        type1: "",
        type2: "",
        height: "",
        heightlist: [0, 0.5, 1.0, 1.5, 2.0, 2.4, 3.0, 4.0, 6.0],
        weight: "",
        weightlist: [0, 10, 30, 60, 100, 150, 210, 280, 360],
        gender: "",
        stage: "",
        egg1: "",
        egg2: "",
        effort1: "",
        effort2: "",
        edited: false
    }
}

export default {
    name: 'App',
    components: {
        Refine,
        Picturebook
    },
    data() {
        return initialState()
    },
    methods: {
        apply () {
            this.data = this.refine;
        },
        clear () {
            Object.assign(this.$data, initialState());
        },
        changere (newregion) {
            this.region = newregion;
            var reregion = this.region;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.region == reregion){
                    return true;
                }
            });
            this.count = counter(this.refine);
        },
        changety1 (newtype1) {
            this.type1 = newtype1;
            var retype1 = this.type1;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.type1 == retype1){
                    return true;
                }
            });
            this.count = counter(this.refine);
        },
        changety2 (newtype2) {
            this.type2 = newtype2;
            var retype2 = this.type2;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.type2 == retype2){
                    return true;
                }
            });
            this.count = counter(this.refine);
        },
        changehei (newheight) {
            this.height = parseInt(newheight);
            var reheight0 = this.heightlist[parseInt(this.height) - 1];
            var reheight1 = this.heightlist[parseInt(this.height)];

            this.refine = this.refine.filter(function(datum) {
                if(reheight0 <= datum.height && datum.height < reheight1){
                    return true;
                }
            }); 
            this.count = counter(this.refine);
        },
        changewei (newweight) {
            this.weight = newweight;
            var reweight0 = this.weightlist[parseInt(this.weight) - 1];
            var reweight1 = this.weightlist[parseInt(this.weight)];

            this.refine = this.refine.filter(function(datum) {
                if(reweight0 <= datum.weight && datum.weight < reweight1){
                    return true;
                }
            });    
            this.count = counter(this.refine);
        },
        changegen (newgender) {
            this.gender = newgender;
            var regender = this.gender;
            this.refine = this.refine.filter(function(datum) {
                if(datum.gender == regender){
                    return true;
                }
            });
            this.count = counter(this.refine);
        },
        changesta (newstage) {
            this.stage = newstage;
            var restage = parseInt(this.stage);

            this.refine = this.refine.filter(function(datum) {
                if(datum.stage == restage){
                    return true;
                }
            });    
            this.count = counter(this.refine);
        },
        changeegg1 (newegg1) {
            this.egg1 = newegg1;
            var reegg1 = this.egg1;
      
            this.refine = this.refine.filter(function(datum) {
                if(datum.egg1 == reegg1){
                    return true;
                }
            });
            this.count = counter(this.refine);
        },
        changeegg2 (newegg2) {
            this.egg2 = newegg2;
            var reegg2 = this.egg2;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.egg2 == reegg2){
                    return true;
                }
            }); 
            this.count = counter(this.refine);
        },
        changeeff1 (neweffort1) {
            this.effort1 = neweffort1;
            var reeffort1 = this.effort1;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.effort1 == reeffort1){
                    return true;
                }
            });       
            this.count = counter(this.refine);
        },
        changeeff2 (neweffort2) {
            this.effort2 = neweffort2;
            var reeffort2 = this.effort2;
            
            this.refine = this.refine.filter(function(datum) {
                if(datum.effort2 == reeffort2){
                    return true;
                }
            }); 
            this.count = counter(this.refine);
        },
    }
};
</script>

<style>
.button{
    top:-480px; 
    margin-left: 5px;
}
.title{
    padding: 0.4em 0.5em;/*文字の上下 左右の余白*/
    color: #494949;/*文字色*/
    background: #f4f4f4;/*背景色*/
    border-left: solid 5px #e83929;/*左線*/
    border-bottom: solid 3px #d7d7d7;/*下線*/
}
</style>
