<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Pipeline from './sections/Pipeline.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import ImageSliderInner from './sections/ImageSliderInner.vue'
import ImageSelector from './sections/ImageSelector.vue'
import Table from './sections/Table.vue'
import QualitativeResults from './sections/QualitativeResults.vue'
import Collapse from './sections/Collapse.vue'
import SeletionForComparison from './sections/SeletionForComparison.vue'
import Comment from './sections/Comment.vue'
import Model3D from './sections/Model3D.vue'
import GaussianSplats3D from './sections/GaussianSplats3D.vue'

export default {
  components: {
    Title,
    Abstract,
    Pipeline,
    BibTeX,
    Carousel,
    Video,
    ImageSliderInner,
    ImageSelector,
    Collapse,
    Table,
    QualitativeResults,
    SeletionForComparison,
    Comment,
    Model3D,
    GaussianSplats3D
  }
}
</script>

<template>
  <Title/>
  <Carousel/>
  <Video/>
  <Abstract/>
  <Pipeline/>
  <Table/>
  <QualitativeResults/>
  <!-- <Collapse/> -->
  <!-- <Model3D/> -->
  <!-- <GaussianSplats3D/> -->
  <!-- <SeletionForComparison/> -->
  <!-- <ImageSliderInner/> -->
  <!-- <ImageSelector/> -->
  <!-- <BibTeX/> -->
  <!-- <Comment/> -->
</template>
