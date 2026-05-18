<script lang="ts" setup>
const metrics = [
  { prop: "keyframeError", label: "Keyframe Error", direction: "↓" },
  { prop: "ssSimilarity", label: "SS Similarity", direction: "↑" },
  { prop: "rPrecision", label: "R-Precision (Top 3)", direction: "↑" },
  { prop: "mmDist", label: "MM Dist", direction: "↓" },
  { prop: "fid", label: "FID", direction: "↓" },
  { prop: "skatingRatio", label: "Skating Ratio", direction: "↓" },
  { prop: "diversity", label: "Diversity", direction: "→" },
  { prop: "jitter", label: "Jitter", direction: "↓" },
]

const tableData = [
  {
    method: "Real",
    keyframeError: "0.000",
    ssSimilarity: "1.000",
    rPrecision: "0.800",
    mmDist: "2.522",
    fid: "–",
    skatingRatio: "0.041",
    diversity: "8.076",
    jitter: "6.885",
  },
  {
    method: "OmniControl",
    keyframeError: "12.883",
    ssSimilarity: "0.449",
    rPrecision: "0.566",
    mmDist: "4.486",
    fid: "7.115",
    skatingRatio: "0.080",
    diversity: "6.533",
    jitter: "61.715",
  },
  {
    method: "CondMDI",
    keyframeError: "10.128",
    ssSimilarity: "0.726",
    rPrecision: "0.723",
    mmDist: "3.028",
    fid: "0.667",
    skatingRatio: "0.072",
    diversity: "7.788",
    jitter: "67.203",
  },
  {
    method: "MaskControl",
    keyframeError: "3.255",
    ssSimilarity: "0.567",
    rPrecision: "0.801",
    mmDist: "2.526",
    fid: "0.155",
    skatingRatio: "0.046",
    diversity: "7.893",
    jitter: "18.037",
  },
  {
    method: "Ours",
    keyframeError: "0.000",
    ssSimilarity: "0.804",
    rPrecision: "0.803",
    mmDist: "2.495",
    fid: "0.023",
    skatingRatio: "0.043",
    diversity: "8.038",
    jitter: "16.172",
    best: true,
  },
]

const tableRowClassName = ({ row }: { row: { method: string, best?: boolean } }) => {
  if (row.best) return "ours-row"
  if (row.method === "Real") return "real-row"
  return ""
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Quantitative Results</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="23" :md="22" :lg="21" :xl="20">
        <p class="table-caption">
          <strong>Quantitative comparison of keyframe in-betweening on the HumanML3D test set.</strong>
          We select the first and last frames along with five randomly sampled intermediate frames from the ground truth motions as keyframe constraints. Bold denotes the best results.
        </p>

        <div class="table-shell">
          <el-table
            :data="tableData"
            :row-class-name="tableRowClassName"
            border
            scrollbar-always-on
          >
            <el-table-column prop="method" label="Method" fixed min-width="150">
              <template #default="{ row }">
                <strong v-if="row.best">{{ row.method }}</strong>
                <span v-else>{{ row.method }}</span>
              </template>
            </el-table-column>

            <el-table-column
              v-for="metric in metrics"
              :key="metric.prop"
              :prop="metric.prop"
              align="center"
              min-width="132"
            >
              <template #header>
                <span class="metric-header">
                  {{ metric.label }}
                  <span class="metric-direction">{{ metric.direction }}</span>
                </span>
              </template>
              <template #default="{ row }">
                <strong v-if="row.best">{{ row[metric.prop] }}</strong>
                <span v-else>{{ row[metric.prop] }}</span>
              </template>
            </el-table-column>
          </el-table>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.table-caption {
  color: #333333;
  font-size: 18px;
  line-height: 1.6;
  margin: 18px auto 16px;
  max-width: 1120px;
  text-align: justify;
}

.table-shell {
  border: 1px solid #dcdfe6;
  overflow: hidden;
}

.metric-header {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  justify-content: center;
  line-height: 1.2;
  white-space: normal;
}

.metric-direction {
  color: #606266;
  font-weight: 700;
}

:deep(.el-table th.el-table__cell) {
  background: #f5f7fa;
  color: #202124;
  font-weight: 700;
}

:deep(.el-table .real-row td.el-table__cell) {
  background: #fafafa;
}

:deep(.el-table .ours-row td.el-table__cell) {
  background: #f0f9eb;
}

:deep(.el-table .cell) {
  word-break: normal;
}

@media (max-width: 768px) {
  .table-caption {
    font-size: 16px;
    line-height: 1.55;
    text-align: left;
  }
}
</style>
