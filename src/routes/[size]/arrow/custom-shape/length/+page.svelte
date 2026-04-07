<script lang="ts">
  import type { PageData } from './$types'
  export let data: PageData

  const goldenPath = 'M 0 48 L 30 0 L 30 32 L 60 32 L 60 64 L 30 64 L 30 96 L 0 48 Z'
  const vbW = 60 
  const vbH = 96 
</script>

<div class="test-box test-box--{data.w}x{data.h} test-box--expected" style="width: {data.w}px; height: {data.h}px">
  <svg class="expected-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 {vbW} {vbH}" style="width: {vbW}px; height: {vbH}px;">
    <path d={goldenPath} />
  </svg>
</div>

<style>
  .expected-svg {
    position: absolute;
    top: 50%;
    left: 50%;
    transform-origin: 0px 48px; 
    transform: translateY(-50%) rotate(45deg);
  }
  path { fill: orange; stroke: none; }
</style>