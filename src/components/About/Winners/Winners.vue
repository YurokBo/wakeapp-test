<template>
    <div class="winners">
        <h4 class="winners__title">
            last winners
        </h4>
        <div class="winners__info">
            <ul class="winners__list">
                <li class="winners__item" v-for="item in winnersList" :key="[item]">
                    <div class="winners__avatar" >
                        <img class="avatar" :src="item.ava" alt="avatar">
                        <img class="status" :src="item.status" alt="status">
                        <div class="winners__income">
                            € <span>{{ item.income }}</span>
                        </div>
                    </div>
                    <div class="winners__name">
                        <span>{{ item.name }}</span> just won
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Winners",
        data() {
            return {
                winnersList: [
                    {name: 'Wild98', income: '11.574.60', ava: require('@/assets/img/winners-ava-1.png'), status: require('@/assets/img/crown.png')},
                    {name: 'Luliana', income: '8.200.66', ava: require('@/assets/img/winners-ava-2.png'), status: require('@/assets/img/crown.png')},
                    {name: 'Farisha', income: '6.483.67', ava: require('@/assets/img/winners-ava-3.png'), status: require('@/assets/img/crown.png')},
                ],

            }
        },

    }

</script>

<style lang="scss" scoped>
    @import "Winners";
</style>