<script setup>
const prompt = "A man crawls to the target"
const videoSrc = "./videos/limitation/limitation.mp4"
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Limitation</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="22" :md="18" :lg="14" :xl="12">
        <p class="limitation-note">
          The generated motion may deviate slightly from the text description when textual semantics conflict with the spatio-temporal constraints.
        </p>

        <p class="prompt">
          <span class="prompt-label">Text prompt</span>
          <span class="prompt-text">“{{ prompt }}”</span>
        </p>

        <article class="limitation-card">
          <video
            :src="videoSrc"
            controls
            muted
            loop
            playsinline
            preload="metadata"
          ></video>
        </article>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.prompt {
  background: #f5f7fa;
  border-left: 4px solid #409eff;
  color: #202124;
  font-size: 18px;
  line-height: 1.55;
  margin: 0 0 18px;
  padding: 12px 16px;
}

.prompt-label {
  color: #606266;
  font-weight: 700;
  margin-right: 10px;
}

.prompt-text {
  font-weight: 600;
}

.limitation-card {
  border: 1px solid #dcdfe6;
  overflow: hidden;
}

video {
  aspect-ratio: 16 / 9;
  background: #000000;
  display: block;
  width: 100%;
}

.limitation-note {
  color: #303133;
  font-size: 17px;
  line-height: 1.65;
  margin: 18px 0 14px;
  text-align: center;
}

@media (max-width: 768px) {
  .prompt {
    font-size: 16px;
  }

  .limitation-note {
    font-size: 16px;
    text-align: left;
  }
}
</style>
