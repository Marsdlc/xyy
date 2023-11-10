<template>
  <div>
    <el-card style="width: 80%;margin-left: 10%">
      <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">

        <el-row>
          <p>
            Welcome to our User Study! ! (˶ᴖ ᴗ ᴖ˶)ა
          </p>
          <p>
            In this study, you will be asked to evaluate the quality of 18 provided videos and determine whether they
            are real or fake.
          </p>
          <p>
            <span>Among these videos, </span>
            <span style="font-weight: bold">some are entirely real</span>
            <span>, while the remaining videos have undergone at least some forms of </span>
            <span style="font-weight: bold">visual manipulation</span>
            <span>, with potential manipulations in </span>
            <span style="font-weight: bold">sound and textual information</span>
            <span> as well. It's worth noting that in certain instances, these potential manipulations </span>
            <span style="font-weight: bold">may only occur in a small segment </span>
            <span>of the video.</span>
          </p>
          <h3>Task 1: Evaluate Video Quality</h3>
          <p>
            Use a rating scale from 1 (poor quality) to 5 (excellent quality) to assess the video. Please check if the
            person in the video appears genuine, including facial expressions, movements, and speech. Look for any
            obvious issues. Does the speech sound unusual? Is the speaking rhythm unusual?
          </p>
          <h3>Task 2: Authenticity Judgment</h3>
          <p>
            In this part, you will be required to determine whether the provided video is real or fake. Based on the
            content you observe, select one of the following options for each video:
          </p>
          <ol>
            <li>
              <span style="font-weight: bold">Real</span>: You think the video seems genuine.
            </li>
            <li>
              <span style="font-weight: bold">Fake</span>: You think the video has undergone manipulations and shows
              evident traces or inconsistencies.
            </li>
          </ol>
        </el-row>

        <el-divider></el-divider>

        <!--有几个视频就把这部分复制几份-->
        <!--    1    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/dfdc_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="dfdc1score">
              <el-select
                v-model="ruleForm.dfdc1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="dfdc1fr">
              <el-select
                v-model="ruleForm.dfdc1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    2    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/fakeav_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="fakeav2score">
              <el-select
                v-model="ruleForm.fakeav2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="fakeav2fr">
              <el-select
                v-model="ruleForm.fakeav2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    3    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/ours_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="ours1score">
              <el-select
                v-model="ruleForm.ours1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="ours1fr">
              <el-select
                v-model="ruleForm.ours1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    4    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/real_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="real3score">
              <el-select
                v-model="ruleForm.real3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="real3fr">
              <el-select
                v-model="ruleForm.real3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    5    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/wild_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="wild2score">
              <el-select
                v-model="ruleForm.wild2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="wild2fr">
              <el-select
                v-model="ruleForm.wild2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    6    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/lavdf_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="lavdf1score">
              <el-select
                v-model="ruleForm.lavdf1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="lavdf1fr">
              <el-select
                v-model="ruleForm.lavdf1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    7    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/dfdc_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="dfdc3score">
              <el-select
                v-model="ruleForm.dfdc3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="dfdc3fr">
              <el-select
                v-model="ruleForm.dfdc3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    8    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/lavdf_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="lavdf2score">
              <el-select
                v-model="ruleForm.lavdf2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="lavdf2fr">
              <el-select
                v-model="ruleForm.lavdf2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    9    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/real_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="real2score">
              <el-select
                v-model="ruleForm.real2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="real2fr">
              <el-select
                v-model="ruleForm.real2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    10    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/lavdf_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="lavdf3score">
              <el-select
                v-model="ruleForm.lavdf3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="lavdf3fr">
              <el-select
                v-model="ruleForm.lavdf3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    11    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/ours_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="ours2score">
              <el-select
                v-model="ruleForm.ours2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="ours2fr">
              <el-select
                v-model="ruleForm.ours2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    12    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/real_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="real1score">
              <el-select
                v-model="ruleForm.real1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="real1fr">
              <el-select
                v-model="ruleForm.real1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    13    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/wild_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="wild1score">
              <el-select
                v-model="ruleForm.wild1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="wild1fr">
              <el-select
                v-model="ruleForm.wild1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    14    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/wild_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="wild3score">
              <el-select
                v-model="ruleForm.wild3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="wild3fr">
              <el-select
                v-model="ruleForm.wild3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    15    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/fakeav_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="fakeav3score">
              <el-select
                v-model="ruleForm.fakeav3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="fakeav3fr">
              <el-select
                v-model="ruleForm.fakeav3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    16    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/fakeav_1.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="fakeav1score">
              <el-select
                v-model="ruleForm.fakeav1score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="fakeav1fr">
              <el-select
                v-model="ruleForm.fakeav1fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    17    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/dfdc_2.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="dfdc2score">
              <el-select
                v-model="ruleForm.dfdc2score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="dfdc2fr">
              <el-select
                v-model="ruleForm.dfdc2fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <el-divider></el-divider>
        <!--    18    -->
        <el-row>
          <el-col :span="8">
            <video :width="videoWidth" :height="videoHeight" controls>
              <source src="../src/video/ours_3.mp4" type="video/mp4">
            </video>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Score:" prop="ours3score">
              <el-select
                v-model="ruleForm.ours3score"
                placeholder="Please select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
                <el-option label="4" value="4"></el-option>
                <el-option label="5" value="5"></el-option>
              </el-select>
            </el-form-item>
          </el-col>

          <el-col :span="8" style="margin-top: 100px">
            <el-form-item label="Real/Fake:" prop="ours3fr">
              <el-select
                v-model="ruleForm.ours3fr"
                placeholder="Please select">
                <el-option label="Real" value="Real"></el-option>
                <el-option label="Fake" value="Fake"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>
        <!--有几个视频就把这部分复制几份-->

        <el-divider></el-divider>

        <el-row>
          <el-col :span="6">
            <el-form-item label="Your Name:" prop="name" :label-width="'110px'">
              <el-input
                v-model="ruleForm.name"
                placeholder="Please insert">
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="Gender:" prop="sex">
              <el-select
                v-model="ruleForm.sex"
                placeholder="Please select">
                <el-option label="Female" value="Female"></el-option>
                <el-option label="Male" value="Male"></el-option>
                <el-option label="Others" value="Others"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="Age:" prop="age">
              <el-select
                v-model="ruleForm.age"
                placeholder="Please select">
                <el-option label="20-30" value="20-30"></el-option>
                <el-option label="30-40" value="30-40"></el-option>
                <el-option label="40-50" value="40-50"></el-option>
                <el-option label="50+" value="50+"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="6">
            <el-form-item label="Screen Size:" prop="screenSize" :label-width="'110px'">
              <el-select
                v-model="ruleForm.screenSize"
                placeholder="Please select">
                <el-option label="smaller than 13 inches" value="smaller than 13 inches"></el-option>
                <el-option label="13-16 inches" value="13-16 inches"></el-option>
                <el-option label="17-22 inches" value="17-22 inches"></el-option>
                <el-option label="23-26 inches" value="23-26 inches"></el-option>
                <el-option label="27-31 inches" value="27-31 inches"></el-option>
                <el-option label="32 inches or larger" value="32 inches or larger"></el-option>
              </el-select>
            </el-form-item>
          </el-col>
        </el-row>

        <el-row>
          <el-col :span="24">
            <el-form-item style="text-align: center; margin-left: -100px">
              <el-button type="primary" @click="submitForm('ruleForm')">
                Submit
              </el-button>
              <el-button @click="resetForm('ruleForm')">Reset</el-button>
            </el-form-item>
          </el-col>
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
        sex: '',
        age: '',
        name: '',
        education: '',
        screenSize: '',
        dfdc1score: '',
        dfdc1fr: '',
        dfdc2score: '',
        dfdc2fr: '',
        dfdc3score: '',
        dfdc3fr: '',
        lavdf1score: '',
        lavdf1fr: '',
        lavdf2score: '',
        lavdf2fr: '',
        lavdf3score: '',
        lavdf3fr: '',
        fakeav1score: '',
        fakeav1fr: '',
        fakeav2score: '',
        fakeav2fr: '',
        fakeav3score: '',
        fakeav3fr: '',
        ours1score: '',
        ours1fr: '',
        ours2score: '',
        ours2fr: '',
        ours3score: '',
        ours3fr: '',
        real1score: '',
        real1fr: '',
        real2score: '',
        real2fr: '',
        real3score: '',
        real3fr: '',
        wild1score: '',
        wild1fr: '',
        wild2score: '',
        wild2fr: '',
        wild3score: '',
        wild3fr: ''
      },
      rules: {
        sex: [
          {
            required: true,
            message: 'Please select gender',
            trigger: 'change',
          },
        ],
        age: [
          {
            required: true,
            message: 'Please select age',
            trigger: 'change',
          },
        ],
        name: [
          {
            required: true,
            message: 'Please insert name',
            trigger: 'change',
          },
        ],
        screenSize: [
          {
            required: true,
            message: 'Please select screen size',
            trigger: 'change',
          },
        ],
        dfdc1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        dfdc1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        dfdc2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        dfdc2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        dfdc3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        dfdc3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        lavdf1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        lavdf1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        lavdf2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        lavdf2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        lavdf3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        lavdf3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        fakeav1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        fakeav1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        fakeav2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        fakeav2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        fakeav3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        fakeav3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        ours1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        ours1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        ours2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        ours2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        ours3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        ours3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        real1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        real1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        real2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        real2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        real3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        real3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        wild1score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        wild1fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        wild2score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        wild2fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
        wild3score: [
          {
            required: true,
            message: 'Please select score',
            trigger: 'change',
          },
        ],
        wild3fr: [
          {
            required: true,
            message: 'Please select real or fake',
            trigger: 'change',
          },
        ],
      }
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          axios.post('http://47.103.148.176:8000/xyy/xyy', this.ruleForm).then(res => {
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