<template>
  <div class="container">
    <n-card bordered>
      <n-flex justify="space-between">
        <n-h5 prefix="bar">
          {{ props.proj.name }}
        </n-h5>
        <n-button secondary type="primary" size="small">
          进入
        </n-button>
      </n-flex>
      <n-progress type="line" :percentage="95" indicator-placement="inside" />
      <n-hr />
      <TimeLineModule :nodes="props.proj.nodes" />
    </n-card>
  </div>
</template>

<script setup lang="ts">
import type { PropType } from 'vue'

import {
  NButton,
  NCard,
  NFlex,
  NH5,
  NHr,
  NProgress,
} from 'naive-ui'

import type { Project } from '@/api/model/proj'

import TimeLineModule from '../project-info-general/TimeLineModule.vue'

const props = defineProps({
  proj: {
    type: Object as PropType<Project>,
    required: true
  }
})
</script>

<style scoped>
.container {
  min-width: 32%;
}
</style>
