<template>
    <section class="games">
        <div class="container">
            <div class="games__filter">
                <ul class="games__filter-list">
                    <li class="games__filter-item"
                        v-for="(filterItem, index) in filterItems"
                        :key="filterItem"
                        :class="{isActive:filterItem.isActive,'active':activeIndex === index}"

                        @click="onClickBlock(index)"

                    >
                        <img :src=filterItem.filterIcon alt="filterIcon" class="filter-icon">
                        <div class="filter-text">{{ filterItem.filterText }}</div>
                    </li>
                </ul>
            </div>
            <div class="games__providers">
                <ul class="games__providers-list">
                    <li class="games__providers-item"
                        v-for="providerItem in gamesProvidersItems"
                        :key="providerItem"
                        :class="{ noLogo: providerItem.isLogo, more: providerItem.isMore }"
                    >
                        <a href="#" class="games__providers-link" :class="{ more: providerItem.isMore }">
                            <img :src=providerItem.providerLogo alt="provider logo" class="games__providers-logo">
                            <span class="games__providers-title">{{ providerItem.providerTitle }}</span>
                        </a>
                    </li>
                </ul>
                <div class="games__providers-form">
                    <form class="form">
                        <button class="form__btn"></button>
                        <input class="form__input" type="text" placeholder="FIND THE GAME">
                    </form>
                </div>
            </div>
            <div class="games__block">
                <ul class="games__block-list">
                    <li class="games__block-item" v-for="game in gamesInfo" :key="game">
                        <a href="#" class="games__block-link">
                            <img :src=game.gamePic alt="game picture">
                            {{ info[0].game_provider }}
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>

<script>
    import axios from 'axios'

    export default {
        name: "Games",

        data() {
            return {
                filterItems: [
                    {
                        id: 1,
                        filterIcon: require('@/assets/img/filter-star.png'),
                        filterText: 'All games',
                        isActive: true
                    },
                    {
                        id: 2,
                        filterIcon: require('@/assets/img/filter-crown.png'),
                        filterText: 'TOp games',
                        isActive: false
                    },
                    {
                        id: 3,
                        filterIcon: require('@/assets/img/filter-casino.png'),
                        filterText: 'Live Casino',
                        isActive: false
                    },
                    {
                        id: 4,
                        filterIcon: require('@/assets/img/filter-slots.png'),
                        filterText: 'Slots Games',
                        isActive: false
                    },
                    {
                        id: 5,
                        filterIcon: require('@/assets/img/filter-roulette.png'),
                        filterText: 'Roulette',
                        isActive: false
                    },
                    {
                        id: 6,
                        filterIcon: require('@/assets/img/filter-dice.png'),
                        filterText: 'Table Games',
                        isActive: false
                    },
                    {
                        id: 7,
                        filterIcon: require('@/assets/img/filter-card.png'),
                        filterText: 'Card Games',
                        isActive: false
                    },
                ],
                gamesProvidersItems: [
                    {isLogo: true, providerTitle: 'All providers'},
                    {providerLogo: require('@/assets/img/netent-logo.png'), providerTitle: 'Netent'},
                    {providerLogo: require('@/assets/img/go-logo.png'), providerTitle: 'Play\'n Go'},
                    {providerLogo: require('@/assets/img/microgaming-logo.png'), providerTitle: 'Microgaming'},
                    {isLogo: true, isMore: true, providerTitle: '...'},
                ],
                gamesInfo: [
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                    {gamePic: require('@/assets/img/divine-ways.jpg')},
                    {gamePic: require('@/assets/img/holy-diver.jpg')},
                ],
                activeIndex: -1,
                info: [],
            }
        },

        methods: {
            onClickBlock(index) {
                if (this.activeIndex === index) {
                    this.activeIndex = -1;
                } else {
                    this.activeIndex = index;
                }
            },


        },

        created() {

            axios
                .get('https://57d10932-44d0-4d3a-98a9-6dda8c67bdd3.mock.pstmn.io')
                .then(response => (console.log(this.info = response.data)))

        }
    }
</script>

<style lang="scss" scoped>
    @import "Games";
</style>