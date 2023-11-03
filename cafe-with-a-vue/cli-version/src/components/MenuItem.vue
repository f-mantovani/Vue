<script>
  export default {
    name: "Menu Item",
    props: ['item', 'addToShoppingCart']
  }
</script>

<template>
  <div>
    <img
        :src="item.image.source"
        :alt="item.image.alt"
      />
    <div>
      <h3>{{ item.name }}</h3>
      <p v-if="item.inStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <div>
        <label for="add-item-quantity"
          >Quantity: {{ item.quantity }}</label
        >
        <input
          v-model.number="item.quantity"
          id="add-item-quantity"
          type="number"
        />
        <button @click="addToShoppingCart(item.quantity)">
          Add to Shopping Cart
        </button>
      </div>
    </div>
  </div>  
</template>