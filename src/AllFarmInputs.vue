<template>
  <ul class="content white-text align-center">
    <singleFarmInput class="card input-card pointer" v-for="input in inputs" v-bind:input="input" v-bind:key="input.id" @display-full="$emit('show-modal', input)" v-bind:id="inputs.indexOf(input)"/>
    <li class="card pointer">
      <a href="./create-input-form.html">
        <button class="add-button pointer material-icons">add</button>
      </a>
    </li>
  </ul>
</template>

<script>
import singleFarmInput from './SingleFarmInput.vue';

export default {
  components: {
    singleFarmInput
  },
  name: 'allFarmInputs',
  props: {
    singleInput: {}
  },
  data() {
    return {
      inputs: [
        {
          id: '1',
          name: 'Feed(P.K.C)',
          batch: '11-18',
          price: '36000.00',
          unitquantity: 'tonnes',
          qtyused: '4',
          currenttotal: '144000',
          percentagecost: '25',
        },
        {
          id: '2',
          name: 'Feed(P.K.C)',
          batch: '08-17',
          price: '36000.00',
          unitquantity: 'tonnes',
          qtyused: '4',
          currenttotal: '144000',
          percentagecost: '25',
        },
        {
          id: '3',
          name: 'Feed(P.K.C)',
          batch: '01-19',
          price: '36000.00',
          unitquantity: 'tonnes',
          qtyused: '4',
          currenttotal: '144000',
          percentagecost: '10',
        },
      ],
    };
  },
  created() {
    fetch('http://localhost:8000/api/v1/inputs', {
      headers: { 'Content-Type': 'application/json' },
      mode: 'cors',
    })
      .then(data => data.json())
      .then((json) => {
        this.inputs = json;
      })
      .catch();
  }
};
</script>
