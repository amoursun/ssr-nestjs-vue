
<template>
  <div>
    <Search />
    <template v-if="indexData">
      <Slider :data="indexData[0].components" />
      <Rectangle :data="indexData[1].components" />
    </template>
    <template v-else>
      <img src="https://gw.alicdn.com/tfs/TB1v.zIE7T2gK0jSZPcXXcKkpXa-128-128.gif" class="loading">
    </template>
  </div>
</template>


<script lang="ts" setup>
import Rectangle from '@/components/rectangle/index.vue'
import Search from '@/components/search/index.vue'
import Slider from '@/components/slider/index.vue'
import { mapState } from 'ssr-hoc-vue3'
import { IndexData } from '~/typings/data'

const indexData = mapState<IndexData>().indexStore.value.data
</script>
