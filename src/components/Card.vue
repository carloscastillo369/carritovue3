<template>
    <div class="col-12 col-sm-4 col-md-3 col-lg-2 mb-3 mb-3">
        <div class="card">
            <img :src="`/img/${producto.imagen}.jpg`" alt="" class="card-img-top">
            <div class="card-body">
                <h5 class="card-title">{{producto.nombre}}</h5>
                <p class="card-text">$ <span>{{producto.precio}}</span></p>
                <button class="btn btn-dark" @click="agregar(producto)">Comprar</button>
            </div>
        </div>
    </div>
</template>

<script>
import { mapActions, mapState } from "vuex"

export default {
    name: 'Card',
    props: {
        producto:{}
    },
    methods: {
        ...mapActions(['agregarCarrito']),
        agregar(producto){
            console.log(producto)
            this.agregarCarrito(producto)
        }
    },
    computed: {
        ...mapState(['carrito'])
    }
}
</script>

<style>

</style>