<script setup>
const teaserFigure = "./figures/teaser.png"
</script>

<template>
  <el-row justify="center">
    <el-col :xs="24" :sm="23" :md="22" :lg="21" :xl="20">
      <figure class="teaser-figure">
        <img
          :src="teaserFigure"
          alt="Teaser figure for Unifying Precise Keyframes and Semantic Control via Multi-level Diffusion"
        />
        <figcaption>
          Our method enables interactive motion generation and editing with precise spatio-temporal control.
          <strong>(a) Text-conditioned Motion In-betweening:</strong>
          given textual descriptions, keyframes shown in orange, and sparse keyjoint signals shown as orange spheres, our method generates motions shown in blue that strictly satisfy the spatio-temporal constraints while aligning with textual semantics.
          <strong>(b) Semantics-preserving Motion Editing:</strong>
          starting from the generated source motion in (a), a user can provide a keyframe shown in orange to specify local edits, such as placing the character on the ground and lowering the hands in the last frame. The resulting edited motion preserves the original <em>flip forward</em> semantics, keeps unmodified segments in blue, and changes only the constrained segments shown in pink. Frames are slightly spaced for visualization.
        </figcaption>
      </figure>
    </el-col>
  </el-row>
</template>

<style scoped>
.teaser-figure {
  margin: 24px 0 0;
}

.teaser-figure img {
  display: block;
  width: 100%;
}

.teaser-figure figcaption {
  color: #333333;
  font-size: 18px;
  line-height: 1.65;
  margin: 16px auto 0;
  max-width: 1120px;
  text-align: justify;
}

@media (max-width: 768px) {
  .teaser-figure figcaption {
    font-size: 16px;
    line-height: 1.55;
    text-align: left;
  }
}
</style>
