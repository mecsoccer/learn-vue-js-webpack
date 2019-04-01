<template>
  <div class="modal" v-on:click="$emit('close-modal')">
    <div class="card-expand">
        <p class="align-center white-text twenty underline">{{ input.name }}</p>
        <table class="centered white-text">
            <tr>
                <td>Min. Quantity:</td>
                <td>{{ input.unitquantity }}</td>
            </tr>
            <tr>
                <td>Current Price:</td>
                <td>&#8358;{{ input.price }}</td>
            </tr>
            <tr>
                <td>Qty Used:</td>
                <td>{{ input.qtyused }}</td>
            </tr>
            <tr>
                <td>Current Total:</td>
                <td>&#8358;{{ input.currenttotal }}</td>
            </tr>
            <tr>
                <td>Percentage Cost:</td>
                <td>{{ input.percentagecost }}</td>
            </tr>
        </table>
        <div class="centered fit">
            <button class="update-input-btn">
                <a href="./update-input-form.html" class="format-link">Update</a>
            </button>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'modal-app',
  props: {
    input: {
      type: Object,
      required: true
    },
  },
};
</script>
