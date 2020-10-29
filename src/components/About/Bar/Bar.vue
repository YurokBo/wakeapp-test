<template>
    <div class="bar">
        <ul class="bar__list">
            <li class="bar__item"
                v-for="bar in bars"
                :key="bar"
            >
                <a href="" class="bar__link">
                    <img :src=bar.barIcon alt="{{ bar.barText }}" class="bar__icon">
                    <span class="bar__text">{{ bar.barText }}</span>
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Bar",

        data() {
            return {
                bars: [
                    {barIcon: require('@/assets/img/bar-menu.svg'), barText: 'menu', isMenu: true},
                    {barIcon: require('@/assets/img/bar-promotions.svg'), barText: 'promotions', isMenu: false},
                    {barIcon: require('@/assets/img/bar-deposit.svg'), barText: 'deposit', isMenu: false},
                    {barIcon: require('@/assets/img/bar-support.svg'), barText: 'support', isMenu: false},
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    .bar {
        display: none;
    }

    @media (max-width: 576px) {
        .bar {
            display: block;
            padding: 16px 0 14px;
            margin-bottom: 12px;

            &__list {
                display: flex;
                justify-content: space-around;
                align-items: center;
                text-align: center;

                font-size: 7px;
                letter-spacing: 0.01em;
            }

            &__link {
                display: flex;
                flex-direction: column;
                align-items: center;
            }

            &__icon {
                margin-bottom: 4px;
            }
        }
    }
</style>