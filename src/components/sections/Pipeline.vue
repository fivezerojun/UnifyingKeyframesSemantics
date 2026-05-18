<script setup>
const pipelineFigure = "./figures/pipeline.png"
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Pipeline</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="23" :md="22" :lg="21" :xl="20">
        <figure class="pipeline-figure">
          <img
            :src="pipelineFigure"
            alt="Pipeline overview of Unifying Precise Keyframes and Semantic Control via Multi-level Diffusion"
          />
          <figcaption>
            Given a text prompt, sparse keyframes, and a keyframe mask, our model generates a motion sequence that aligns with both precise spatio-temporal constraints and text-driven motion semantics. The framework consists of four components: <strong>(a) Condition Encoding</strong> encodes text and keyframe inputs; <strong>(b) Local Guidance</strong> incorporates keyframe embeddings with noisy motion features to guide local transitions around keyframes; <strong>(c) Global Guidance</strong> integrates text and keyframe features to modulate global motion dynamics; and <strong>(d) Inference Refinement</strong> enforces precise spatial adherence through trajectory and pose refinement. Here, <strong>(cf)</strong> and <strong>(ct)</strong> denote concatenation along the feature dimension and token dimension, respectively.
          </figcaption>
        </figure>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.pipeline-figure {
  margin: 18px 0 0;
}

.pipeline-figure img {
  display: block;
  width: 100%;
}

.pipeline-figure figcaption {
  color: #333333;
  font-size: 18px;
  line-height: 1.65;
  margin: 18px auto 0;
  max-width: 1120px;
  text-align: justify;
}

@media (max-width: 768px) {
  .pipeline-figure figcaption {
    font-size: 16px;
    line-height: 1.55;
    text-align: left;
  }
}
</style>
