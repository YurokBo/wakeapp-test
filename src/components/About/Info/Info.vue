<template>
    <div class="info">
        <div class="container">
            <ul class="info__list">
                <li class="info__item" v-for="item in items" :key="item">
                    <img class="info__item-img" :src=item.img alt="icon">
                    <div class="info__item-text">
                        <span>{{item.digit}}</span>
                        <span>{{item.text}}</span>
                    </div>
                </li>

            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Info",

        data () {
            return {
                items: [
                    {img: require('@/assets/img/info-payouts.png'), digit: '€ 6.483.67', text: 'Fast Payouts'},
                    {img: require('@/assets/img/info-payouts.png'), digit: '24/7', text: 'Support'},
                    {img: require('@/assets/img/info-payouts.png'), digit: '250K', text: 'games'},
                    {img: require('@/assets/img/info-payouts.png'), digit: '1250K', text: 'Top Providers'},
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "Info";
</style>