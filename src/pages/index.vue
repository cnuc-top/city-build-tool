<style lang='stylus'>
.main {
  border: 2px solid #CCC;
  width: 300px;
  height: 650px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  // align-items: center;
}

.build-top {
  height: 600px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.build-main {
  position: relative;
  margin: 0 auto;

  .build-structure, .build-secound, .build-frame {
    position: absolute;
    bottom: 0px;
  }

  .build-frame {
    z-index: 1;
  }

  .build-secound {
    z-index: 2;
    opacity: 0.8;
  }
}

.nb-build {
  &__form {
    padding: 30px;
    border: 2px solid #CCC;
    width: 400px;
  }
}
</style>
<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="12">
        <div class="main">
          <div class="build-top">
            <div class="build-main" :style="{width: width + 'px', height: height + 'px'}">
              <build-structure v-show="form.showStructure" :path="structure" :width="width" :height="height" :layers="layers" :layersNow="process.layers"></build-structure>
              <build-secound :width="width" :height="height" :layers="layers" :secounds="secounds" :process="process.second"></build-secound>
              <build-frame v-show="form.showFrame" :width="width" :height="height" :secounds="secounds"></build-frame>
            </div>
          </div>
          <build-base   v-show="form.showBase" :process="process.basic" :width="width" :height="height"></build-base>
        </div>
      </el-col>
      <el-col :span="12">
        <div class="nb-build__form">
          <el-form :model="form" label-width="100px">
            <el-form-item label="显示">
              <el-checkbox label="框架" name="frame" v-model="form.showFrame"></el-checkbox>
              <el-checkbox label="地基" name="frame" v-model="form.showBase"></el-checkbox>
              <el-checkbox label="结构" name="frame" v-model="form.showStructure"></el-checkbox>
            </el-form-item>
            <el-form-item label="基础结构">
              <el-slider v-model="process.basic"></el-slider>
            </el-form-item>
            <el-form-item label="主体结构">
              <el-slider v-model="process.layers" :min="0" :max="layers"></el-slider>
            </el-form-item>
            <el-form-item label="二次结构">
              <el-slider v-model="process.second" :min="0" :max="layers"></el-slider>
            </el-form-item>
          </el-form>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import BuildBase from '@/components/Build/BuildBase'
import BuildStructure from '@/components/Build/BuildStructure'
import BuildSecound from '@/components/Build/BuildSecound'
import BuildFrame from '@/components/Build/BuildFrame'
import BuildData from '@/common/data/ningbo/nbc'
export default {
  components: { BuildBase, BuildStructure, BuildSecound, BuildFrame },

  props: {
  },

  data() {
    return {
      ...BuildData,
      form: {
        showFrame: true,
        showBase: true,
        showStructure: true,
        visibles: {
          frame: true
        }
      }
    }
  },

  computed: {},

  mounted() {

  },

  methods: {}
}
</script>
