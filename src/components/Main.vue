<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Pipeline from './sections/Pipeline.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import Table from './sections/Table.vue'
import QualitativeResults from './sections/QualitativeResults.vue'
import Limitation from './sections/Limitation.vue'
import Comment from './sections/Comment.vue'

export default {
  components: {
    Title,
    Abstract,
    Pipeline,
    BibTeX,
    Carousel,
    Video,
    Table,
    QualitativeResults,
    Limitation,
    Comment,
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
  <Limitation/>
  <BibTeX/>
  <!-- <Comment/> -->
</template>
