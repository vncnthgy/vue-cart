<template>
    <div>
        <div class="item-container" v-for="product in products" :key="product.id">
            <div class="item">
                <img :src="'/images/' + product.image_path" width="100" height="100"/>
                <span>{{ product.name }}<br>₱{{ product.price }}</span>
                <button class="add-button" @click="addToCart(product)">Add to Cart</button>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
        data() {
            return {
                products: [
                    { id: 1, name: 'NVIDIA RTX 4090', price: 90000, image_path: 'rtx1.png'},
                    { id: 2, name: 'NVIDIA RTX 4080', price: 80000, image_path: 'rtx2.png'},
                    { id: 3, name: 'NVIDIA RTX 4070', price: 70000, image_path: 'rtx3.png'},
                    { id: 4, name: 'NVIDIA RTX 4060', price: 60000, image_path: 'rtx4.png'},
                    { id: 5, name: 'NVIDIA RTX 3090', price: 80000, image_path: 'rtx5.png'},
                    { id: 6, name: 'NVIDIA RTX 3080', price: 70000, image_path: 'rtx6.png'},
                    { id: 7, name: 'NVIDIA RTX 3070', price: 60000, image_path: 'rtx7.png'},
                    { id: 8, name: 'NVIDIA RTX 3060', price: 50000, image_path: 'rtx8.png'},
                ],
            };
        },
        methods: {
            addToCart(product) {
                alert('Successfully added!');
                this.$emit('add-to-cart', product);
            }
        },
    };
</script>