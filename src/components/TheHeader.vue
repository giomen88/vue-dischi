<template>
    <header>
        <div>
            <img src="../assets/img/logo.png" alt="" class="logo img-fluid">
        </div>
    </header>
</template>

<script>
export default {
    name: 'TheHeader',
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';

header {
    background-color: $bg-secondary;
    height: 70px;
    display: flex;
    align-items: center;
    padding: 5px;

    img {
        width: 50px;
    }
}
</style>