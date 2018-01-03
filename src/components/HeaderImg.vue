<template>
  <div class="header-img">
    <img :src="pictureUrl" alt="头像">
    <input type="file" class="choose-img" @change="onFileChange">
  </div>
</template>

<style>
.header-img {
  margin-bottom: 30px;
}
.header-img,
.header-img img {
  position: relative;
  width: 218px;
  height: 218px;
  box-shadow: 0 0 10px #ffffff;
  border-radius: 5px;
}
.header-img .choose-img {
  width: 218px;
  height: 218px;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  opacity: 0;
}
</style>

<script>
export default {
  data() {
    return {
      images: [],
      pictureUrl: "../../static/img/headerImg.jpg"
    };
  },
  methods: {
    onFileChange(e) {
      var files = e.target.files || e.dataTransfer.files;
      if (!files.length) return;

      var _this = this;
      var reader = null;
      // 浏览器是否兼容FileReader
      if(window.FileReader){
        reader = new window.FileReader();
        reader.readAsDataURL(files[0]);
        reader.onload = function(e) {
          _this.pictureUrl = e.target.result;
        };
      }
    }
  }
};
</script>