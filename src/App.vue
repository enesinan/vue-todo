<template>
<AppHeader />
<div class="w-full flex">
<DcHeros />
</div>
</template>

<script>
import AppHeader from "./assets/components/AppHeader";
import DcHeros from './assets/components/DcHeros.vue';
export default {
  components: { AppHeader, DcHeros},
 
};
</script>

<style>

</style>