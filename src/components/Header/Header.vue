<template>
    <header class="header">
            <div class="header__content">
                <nav class="menu">
                    <ul class="menu__list">
                        <li class="menu__item logo">
                            <a href="#">
                                <img class="logo" src="../../assets/img/logo.png" alt="logo">
                            </a>
                        </li>
                        <li class="menu__item">
                            <a class="menu__link" href="#">Lobby</a>
                        </li>
                        <li class="menu__item">
                            <a class="menu__link" href="#">Categories</a>
                        </li>
                        <li class="menu__item">
                            <a class="menu__link" href="#">Promotions</a>
                        </li>
                        <li class="menu__item">
                            <a class="menu__link" href="#">Tournaments</a>
                        </li>
                    </ul>
                </nav>
                <div class="header__btn-box">
                    <button class="header__btn login">Login</button>
                    <button class="header__btn registration">Register</button>
                </div>
            </div>
    </header>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style lang="scss" scoped>
    @import "Header.scss";
</style>