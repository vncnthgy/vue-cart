<template>
    <div class="product">
        <div class="right"><cart :cart="cart" @update-quantity="updateQuantity" @remove-from-cart="removeFromCart"></cart></div>
    </div>
</template>

<script>
  import Product from '@/components/Product.vue';
  import Cart from '@/components/Cart.vue';

  export default {
    components: {
      Product,
      Cart
    },
    data() {
      return {
        cart: []
      };
    },
    methods: {
      addToCart(product) {
        const index = this.cart.findIndex(item => item.product.id === product.id);
        if (index !== -1) {
          this.cart[index].quantity++;
        } else {
          this.cart.push({ product, quantity: 1 });
        }
      },
      updateQuantity(index, quantity) {
        this.cart[index].quantity = quantity;
      },
      removeFromCart(index) {
        this.cart.splice(index, 1);
      }
    }
  };
</script>