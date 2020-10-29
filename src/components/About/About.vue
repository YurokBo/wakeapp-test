<template>
    <section class="about">
        <div class="container">
            <div class="about__content">
                <div class="about__title-box">
                    <h1 class="about__title">
                        Sign up <strong>&</strong> get
                        <span>Welcome</span> <span>Bonus</span>
                    </h1>
                    <div class="about__text">
                        <p>€ 100 <strong>+</strong> 55 free spins</p>
                    </div>
                    <button class="about__btn">
                        Deposit now
                    </button>
                </div>
                <Winners />
                <Info />
            </div>
        </div>
    </section>
</template>

<script>
    import Winners from "./Winners/Winners";
    import Info from "./Info/Info";
    export default {
        name: "About",
        components: {Info, Winners}
    }
</script>

<style lang="scss" scoped>
    @import "About";
</style>