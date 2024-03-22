<template>
    <div class="item-container">
        <div class="item">
            <span>{{ item.product.name }}<br>₱{{ item.product.price }}</span><br/>
            <button class="qty-button" @click="decreaseQuantity">-</button>
            <span>{{ item.quantity }}</span>
            <button class="qty-button" @click="increaseQuantity">+</button>
            <button class="remove-button" @click="removeItem">Remove</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['item'],
        data() {
            return {
                quantity: this.item.quantity
            };
        },
        methods: {
            increaseQuantity() {
                if (this.quantity < 99) this.quantity++;
                this.updateQuantity();
            },
            decreaseQuantity() {
                if (this.quantity > 1) this.quantity--;
                this.updateQuantity();
            },
            updateQuantity() {
                this.$emit('update', this.quantity);
            },
            removeItem() {
                this.$emit('remove');
            }
        }
    };
</script>