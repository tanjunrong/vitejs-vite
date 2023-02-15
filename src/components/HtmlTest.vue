<script setup>
</script>

<template>
  <text> 在 HTML 4 中，em 表示 emphasized text，strong 表示 strong emphasized text，故 strong 的强度要更强。而在 HTML 5
    中，strong 的定义改成了 important text。当然 emphasized 和 strong emphasized 乃至 important 之间怎么界定很模糊，关键是在自己编写
    HTML 代码的时候保持使用上一致。b 和 i 仅仅表示「这里应该用粗体显示」或者「这里应该用斜体显示」。
  </text>
  <p></p>
    <em style="font-style:oblique ">HTML 着重元素 (&lt;em&gt;) ,em 表示 emphasized text</em>
    <em>第二<em>第三</em></em>
  <p><strong>第3</strong></p>
  <p>分段</p>
  <p>第五</p>
  <p>第六</p>

</template>

<style scoped>
</style>
