<script setup lang='ts'>
import { ref } from 'vue'

const tree = ref({
  label: 'Top Level',
  children: [
    { label: 'First Level' },
    { label: 'First Level', children: [{ label: 'Second Level' }] },
  ],
})

const rate = ref(2.5)
const radio = ref('1')
</script>

<template>
  <div class="block">
    <h1>Basic (4)</h1>
    <ComponentA msg="a" />
    <component-b msg="b" />
    <ComponentC msg="c" />
    <ComponentD />
    <h3>Recursive Components</h3>
    <recursive :data="tree" />
  </div>

  <div class="block">
    <h1>Namespaced (4)</h1>
    <!-- Index -->
    <Book />
    <UiButton />
    <UiNestedCheckbox />
    <!-- Global -->
    <Avatar />
  </div>

  <div class="block">
    <h1>Markdown (2)</h1>
    <MarkdownA />
    <MarkdownB />
  </div>

  <div class="block">
    <h1>Custom Resolvers (1)</h1>
    <MyCustom />
    <CarbonSvg />
  </div>

  <div class="block">
    <h1>UI Library (2)</h1>
    <van-rate
      v-model="rate"
      color="#ffd21e"
      void-icon="star"
      void-color="#eee"
    />
    <br>
    <br>
    <van-radio-group v-model="radio">
      <van-radio name="1">
        Radio 1
      </van-radio>
      <br>
      <van-radio name="2">
        Radio 2
      </van-radio>
    </van-radio-group>
    <br>
  </div>
</template>

<style scoped>
.block {
  padding: 0px 20px 10px 20px;
  margin: 20px 20px;
  border: 1px solid #888;
  border-radius: 5px;
}
</style>
