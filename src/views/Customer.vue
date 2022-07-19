<template>
    <div>
        <Nav></Nav>
        <Content></Content>
        <Footer></Footer>
    </div>
</template>

<script>
import Nav from '../components/Nav.vue'
import Content from './Content.vue'
import Footer from '../components/Footer.vue'

export default {
    components: {
    Nav,
    Content,
    Footer
}
}
</script>

<style>
    body{
        background-color: #f2f2f2;
    }
</style>