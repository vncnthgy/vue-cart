<template>
    <div>
        <h1>Product List</h1>
        <div class="item-container" v-for="product in products" :key="product.id">
            <div class="item">
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
                    { id: 1, name: 'NVIDIA RTX 4090', price: 8000 },
                    { id: 2, name: 'NVIDIA RTX 4080', price: 7000 },
                    { id: 3, name: 'NVIDIA RTX 4070', price: 6000 },
                    { id: 4, name: 'NVIDIA RTX 4060', price: 5000 },
                    { id: 5, name: 'NVIDIA RTX 3090', price: 4000 },
                    { id: 6, name: 'NVIDIA RTX 3080', price: 3000 },
                    { id: 7, name: 'NVIDIA RTX 3070', price: 2000 },
                    { id: 8, name: 'NVIDIA RTX 3060', price: 1000 },
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