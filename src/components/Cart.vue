<template>
    <div>
        <h1>Shopping Cart</h1>
        <div v-for="(item, index) in cart" :key="index">
            <cart-item :item="item" @update="updateQuantity(index, $event)" @remove="removeFromCart(index)"></cart-item>
        </div>
        <hr>
        <h2>Total Price: ₱{{ totalPrice }}</h2>
    </div>
</template>
  
<script>
    import CartItem from '@/components/CartItem.vue';
  
    export default {
        components: {
            CartItem
        },
        props: ['cart'],
        computed: {
            totalPrice() {
                return this.cart.reduce((total, item) => total + (item.quantity * item.product.price), 0);
            }
        },
        methods: {
            updateQuantity(index, quantity) {
                this.$emit('update-quantity', index, quantity);
            },
            removeFromCart(index) {
                alert('Successfully removed!');
                this.$emit('remove-from-cart', index);
            }
        },
    };
</script>