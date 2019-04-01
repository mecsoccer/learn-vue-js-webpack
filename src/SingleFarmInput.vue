<template>
  <li class="card input-card pointer" @click="$emit('display-full')">
    <p>{{ input.name }}</p>
    <div class="fit centered abs-1 radius-5 white-bkg dk-text">{{ input.percentagecost }}%</div>
  </li>
</template>

<script>
export default {
  props: {
    input: {
      type: Object,
      required: true
    }
  }
}
</script>
