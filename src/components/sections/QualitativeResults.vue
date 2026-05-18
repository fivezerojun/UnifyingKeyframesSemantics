<script setup>
const examples = [
  {
    prompt: "A person initially running and decelerating to walking",
    videos: [
      {
        method: "OmniControl",
        src: "./videos/comparison/run2walk/omnicontrol.mp4",
      },
      {
        method: "CondMDI",
        src: "./videos/comparison/run2walk/condmdi.mp4",
      },
      {
        method: "MaskControl",
        src: "./videos/comparison/run2walk/maskcontrol.mp4",
      },
      {
        method: "Ours",
        src: "./videos/comparison/run2walk/ours.mp4",
        highlight: true,
      },
    ],
  },
]
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Qualitative Results</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="23" :md="22" :lg="21" :xl="20">
        <section v-for="example in examples" :key="example.prompt" class="qualitative-example">
          <p class="prompt">
            <span class="prompt-label">Text prompt</span>
            <span class="prompt-text">“{{ example.prompt }}”</span>
          </p>

          <el-row :gutter="18">
            <el-col
              v-for="video in example.videos"
              :key="video.method"
              :xs="24"
              :sm="12"
              :md="12"
              :lg="12"
              :xl="12"
            >
              <article class="video-card" :class="{ 'ours-card': video.highlight }">
                <header class="video-card-header">
                  <span>{{ video.method }}</span>
                </header>
                <video
                  :src="video.src"
                  controls
                  muted
                  loop
                  playsinline
                  preload="metadata"
                ></video>
              </article>
            </el-col>
          </el-row>
        </section>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.qualitative-example {
  margin-top: 18px;
}

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

.video-card {
  border: 1px solid #dcdfe6;
  margin-bottom: 18px;
  overflow: hidden;
}

.ours-card {
  border-color: #67c23a;
}

.video-card-header {
  align-items: center;
  background: #f5f7fa;
  color: #202124;
  display: flex;
  font-size: 17px;
  font-weight: 700;
  justify-content: center;
  min-height: 42px;
  padding: 8px 12px;
}

.ours-card .video-card-header {
  background: #f0f9eb;
  color: #2f7d20;
}

video {
  aspect-ratio: 16 / 9;
  background: #000000;
  display: block;
  width: 100%;
}

@media (max-width: 768px) {
  .prompt {
    font-size: 16px;
  }
}
</style>
