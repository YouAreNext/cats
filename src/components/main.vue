<template>
    <div class="main_container">
        <div class="wrapper wrapper_main">
            <div class="main_title">
                Ты сегодня покормил кота?
            </div>
            <div class="items_container">
                <div class="item_container"  v-on:click="chooseItem(key,$event)" :class="{item_container_disabled : !item.status, item_container_order : item.isActive}" v-for="(item,key) in items" :key="key"> 
                    <div class="item" >
                        <div class="item_wrapper">
                            <div class="item_img">
                                <img src="../assets/images/background/cat_bg.jpg" alt="">
                            </div>
                            <div class="item_content">
                                <div class="item_pretitle">
                                    Сказачное заморское яство
                                </div>
                                <div class="item_title">
                                    Нямушка
                                    <span>{{ item.name}}</span>
                                </div>
                                <div class="item_description">
                                    <span>
                                        {{ item.portion }} порций
                                    </span>
                                    <span>
                                        {{ item.mouse }}
                                    </span>
                                    <span v-if="item.happy">
                                        Клиент доволен
                                    </span>
                                </div>
                                <div class="item_weight">
                                    {{ item.weight }}
                                    <span>
                                        кг
                                    </span>
                                </div>
                            </div>
                            <div class="item_borders">
                                <div class="item_border item_border_left">

                                </div>
                                <div class="item_border item_border_bottom">
                                    
                                </div>
                                <div class="item_border item_border_right">
                                    
                                </div>
                            
                                <div class="item_border item_border_top">
                                    
                                </div>
                                <div class="border_diag">

                                </div>
                            </div>
                            
                            
                        </div>
                        
                    </div>

                    <div class="item_buy_text" v-if="item.isActive">
                        Головы щучьи с чесноком да свежайшая сёмгушка.
                    </div>
                    <div class="item_buy_text" v-else-if="!item.status">
                        Печалька, с курой закончился.
                    </div>
                    <div class="item_buy_text" v-else>
                        Чего сидишь? Порадуй котэ, <span v-on:click.stop="chooseItem(key,$event)"><span class="dashed">купи</span>.</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                items: {
                    0:{
                        name: 'с фуа-гра',
                        weight: '0,5',
                        status: 1,
                        portion: 10,
                        mouse: 'мышь в подарок',
                        happy: 0,
                        isActive: false
                    },
                    1:{
                        name: 'с рыбой',
                        weight: '2',
                        status: 1,
                        portion: 40,
                        mouse: '2 мыши в подарок',
                        happy: 0,
                        isActive: false
                    },
                    2:{
                        name: 'с курой',
                        weight: '5',
                        status: 0,
                        portion: 100,
                        mouse: '5 мышей в подарок',
                        happy: 1,
                        isActive: false
                    }
                }
            }
        },
        methods:{
            chooseItem(key,event){
                if(this.items[key].status != 0){
                    this.items[key].isActive = !this.items[key].isActive;
                    
                }
                
            }
           
        },
        computed:{
            
        }
    };
</script>

