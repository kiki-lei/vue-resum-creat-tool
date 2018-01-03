<template>
  <div class="skills">
    <!-- 标题 -->
    <div class="titleBox">
      <span class="title">技能特点</span>
      <a href="javascrpt:void(0);" class="add addBtn" @click="addSkills">
        <mu-icon value="add" color="#ffffff" />
      </a>
    </div>

    <!-- 添加弹窗 -->
    <div class="popBox">      
      <mu-dialog :open="dialog" title="添加技能点" @close="close">
        <h4>已经掌握的技术</h4>
        <mu-text-field hintText="请输入名称..." type="type" fullWidth />
        <mu-slider v-model="value1" class="skill-exp" :step="10" :min="0" :max="100" />{{value1}}

        <mu-flat-button slot="actions" @click="close" primary label="取消"/>
        <mu-flat-button slot="actions" primary @click="close" label="确定"/>
      </mu-dialog>
    </div>
  </div>
</template>

<style>
.titleBox {
  margin-top: 30px;
  border-bottom: 1px solid #ffffff;
  padding-bottom: 10px;
}
.title {
  font-size: 16px;
}
.addBtn {
  float: right;
}
</style>

<script>
export default {
  data () {
    return {
      dialog: false,
      value1: 100
    }
  },
  methods: {
    addSkills () {
      this.dialog = true
    },
    close () {
      this.dialog = false
    }
  }
}
</script>