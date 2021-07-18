<template>
<div class="row mb-3">
  <div class="col-md-4">
    <div class="badge badge-success mt-2">less than 450 ms Great</div>
  </div>
  <div class="col-md-4">
    <div class="badge badge-warning mt-2">from 451 to 600 ms Good</div>
  </div>
  <div class="col-md-4">
    <div class="badge badge-danger mt-2">above 600 ms Not Bad</div>
  </div>
</div>
</template>

<script>
export default {
  name: "ScoreSheet"
}
</script>

<style>
.badge{
  font-size: 20px;
}
</style>