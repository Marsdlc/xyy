<template>
  <div>
    <el-card style="width: 80%;margin-left: 10%">
      <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">

        <el-row>
          <el-col :span="8">
            <span>
              &nbsp;
            </span>
          </el-col>
          <el-col :span="8">
            <span>
              1111111111
            </span>
          </el-col>
          <el-col :span="8">
            <span>
              &nbsp;
            </span>
          </el-col>
        </el-row>

        <!--只需要修改这里面这部分内容就可以-->
        <!--有几个视频就把这部分复制几份-->
        <el-row>
          <el-col :span="16">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="/test.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8">
            <el-form-item label="分值:" prop="video1score">
              <el-select
                v-model="ruleForm.video1score"
                placeholder="请选择分值">
                <el-option label="10" value="10"></el-option>
                <el-option label="20" value="20"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <!--有几个视频就把这部分复制几份-->

        <el-row>
          <el-col :span="16">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="/test.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8">
            <el-form-item label="分值:" prop="video1score">
              <el-select
                v-model="ruleForm.video2score"
                placeholder="请选择分值">
                <el-option label="10" value="10"></el-option>
                <el-option label="20" value="20"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <!--只需要修改这里面这部分内容就可以-->

        <el-row>
          <el-col :span="8">
            <span>
              &nbsp;
            </span>
          </el-col>
          <el-col :span="8">
            <span>
              1111111111
            </span>
          </el-col>
          <el-col :span="8">
            <span>
              &nbsp;
            </span>
          </el-col>
        </el-row>

        <el-row>
          <el-col :span="6">
            <el-form-item label="性别:" prop="sex">
              <el-select
                v-model="ruleForm.sex"
                placeholder="请选择性别">
                <el-option label="男" value="男"></el-option>
                <el-option label="女" value="女"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="年龄:" prop="age">
              <el-select
                v-model="ruleForm.age"
                placeholder="请选择年龄">
                <el-option label="10" value="10"></el-option>
                <el-option label="20" value="20"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="学历:" prop="education">
              <el-select
                v-model="ruleForm.education"
                placeholder="请选择学历">
                <el-option label="本科" value="本科"></el-option>
                <el-option label="硕士" value="硕士"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="屏幕尺寸:" prop="screenSize">
              <el-select
                v-model="ruleForm.screenSize"
                placeholder="请选择屏幕尺寸">
                <el-option label="1920*1080" value="1920*1080"></el-option>
                <el-option label="2560*1440" value="2560*1440"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>

        <el-row>
          <el-col :span="9"></el-col>
          <el-col :span="6">
            <el-form-item>
              <el-button type="primary" @click="submitForm('ruleForm')">
                Submit
              </el-button>
              <el-button @click="resetForm('ruleForm')">Reset</el-button>
            </el-form-item>
          </el-col>
          <el-col :span="9"></el-col>
        </el-row>

      </el-form>
    </el-card>

  </div>
</template>

<script>
import axios from "axios";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'index',
  data() {
    return {
      // 调整视频播放窗口的长和宽
      videoWidth: '320',
      videoHeight: '240',

      ruleForm: {
        video1score: '',
        video2score: '',
        sex: '',
        age: '',
        education: '',
        screenSize: ''
      },
      rules: {
        video1score: [
          {
            required: true,
            message: '请选择分值',
            trigger: 'change',
          },
        ],
        sex: [
          {
            required: true,
            message: '请选择性别',
            trigger: 'change',
          },
        ],
        age: [
          {
            required: true,
            message: '请选择年龄',
            trigger: 'change',
          },
        ],
        education: [
          {
            required: true,
            message: '请选择学历',
            trigger: 'change',
          },
        ],
        screenSize: [
          {
            required: true,
            message: '请选择屏幕尺寸',
            trigger: 'change',
          },
        ]
      }
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          axios.post('http://119.23.182.248:8000/xyy/xyy', this.ruleForm).then(res => {
            alert(res.data);
          })
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
}

</script>


<style scoped>
</style>