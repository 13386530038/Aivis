
<template>
  <div class="w-full h-full overflow-y-scroll	 overflow-x-hidden	">
    <el-button type="primary"  >确认</el-button>
    <div  class="mt-2 pl-2 " v-for="(i,idx)  in modelConfig" :key="idx">
      <el-row>
        <el-col :span="10">
          <span>
            {{ i[0] }}
          </span>
        </el-col>
        <el-col :span="14">
            <el-input v-if="!['true','false','True','False',true,false].includes(i[1])" v-model="i[1]" >
              {{i[0]}}
            </el-input>
            <el-switch v-else v-model="i[1]" active-value="true" inactive-value="false" />
        </el-col>
      </el-row>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';
const props = defineProps({
  config: {
    type: Object,
    required:true
  }
})
let modelConfig = ref(Object.entries(props.config))
</script>
