<script lang="ts" setup>

import { ElIcon } from 'element-plus'
import { Document, Files, Picture, Film } from '@element-plus/icons-vue'

// logo地址，没有则置为""即可
const logo = ''

// 标题
const title = 'Unifying Precise Keyframes and Semantic Control via Multi-level Diffusion'

// 标题颜色
const title_color = '#000000'

// 标题补充，没有则置为''即可
const title_supp = ''

// 标题补充颜色
const title_supp_color = '#42B883'

// 按钮颜色
const btn_color = '#444444'

// 作者清单（包含作者姓名、头像、主页、地址序号）
const authors = [
  {
    name: "Linjun Wu",
    icon: "",
    homepage: "",
    address_flag: "1"
  },
  {
    name: "Jiejia Yu",
    icon: "",
    homepage: "",
    address_flag: "1"
  },
  {
    name: "Leyang Jin",
    icon: "",
    homepage: "",
    address_flag: "2"
  },
  {
    name: "He Wang",
    icon: "",
    homepage: "",
    address_flag: "3"
  },
  {
    name: "Bowen Zheng",
    icon: "",
    homepage: "",
    address_flag: "1"
  },
  {
    name: "Xu Yang",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Hao Jiang",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Fei Xia",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Fei Ling",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Jun Deng",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Xiaogang Jin",
    icon: "",
    homepage: "",
    address_flag: "1*"
  },
]

// 地址清单（包含地址名称、头像、主页、地址序号）
const addresses = [
  {
    address_flag: "1",
    name: "State Key Lab of CAD&CG, Zhejiang University",
    icon: "",
    homepage: ""
  },
  {
    address_flag: "2",
    name: "Hangzhou Research Institute of AI and Holographic Technology",
    icon: "",
    homepage: ""
  },
  {
    address_flag: "3",
    name: "UCL Centre for Artificial Intelligence, Department of Computer Science, University College London",
    icon: "",
    homepage: ""
  },
  {
    address_flag: "4",
    name: "TiMi L1 Studio, Tencent",
    icon: "",
    homepage: ""
  },
]

// 共一和通讯提示
const con_and_corresponding_author = 
  "*: Corresponding Author."

// 最新消息
const news = "CVPR 2026 Poster"

// 强调内容
const emphases = [
  "🎉 [CVPR 2026] Poster"
]

// 提供引导资料链接
const buttons = [
  {
    disabled: true,
    name: "Paper",
    component: Document,
  },
  // {
  //   disabled: false,
  //   name: "Code",
  //   link: "",
  //   component: Files,
  // },
  {
    disabled: false,
    name: "Poster",
    link: "./figures/Poster.png",
    component: Picture,
  },
  {
    disabled: false,
    name: "Video",
    link: "https://www.youtube.com/watch?v=qtKtr4O8TAI",
    component: Film,
  },
]

</script>

<template>
  <div>

    <!-- 最新消息提示 -->
    <el-row justify="center">
      <el-col :span="24">
        <el-alert :title="news" type="success" />
      </el-col>
    </el-row>

    <!-- 文章logo -->
    <el-row v-if="logo" justify="center">
      <el-image :src="logo" class="logo" fit="cover" />
    </el-row>

    <!-- 文章标题 -->
    <el-row justify="center">
      <el-col :span="20">
        <h1 class="paper-title">
          <span v-if="title" :style="{color:title_color}"> {{ title }}</span>
          <span v-if="title_supp" :style="{color:title_supp_color}"> {{ title_supp }}</span>
        </h1>
      </el-col>
    </el-row>

    <!-- 作者名单 -->
    <el-row justify="center" class="author-row">
      <span class="author-item" v-for="author in authors" :key="author.name">
        <component
          :is="author.homepage ? 'a' : 'span'"
          :href="author.homepage || null"
          :target="author.homepage ? '_blank' : null"
          :rel="author.homepage ? 'noopener noreferrer' : null"
        >
          <span class="author">
            {{ author.name }}<sup v-if="author.address_flag" class="name_sup">{{ author.address_flag }}</sup>
          </span>
        </component>
      </span>
    </el-row>

    <!-- 地址名单 -->
    <el-row justify="center" class="address-row">
      <div class="address-item" v-for="address in addresses" :key="address.address_flag">
        <component
          :is="address.homepage ? 'a' : 'span'"
          :href="address.homepage || null"
          :target="address.homepage ? '_blank' : null"
          :rel="address.homepage ? 'noopener noreferrer' : null"
        >
          <span class="address">
            <sup v-if="address.address_flag" class="address_sup">{{ address.address_flag }}</sup>{{ address.name }}
          </span>
        </component>
      </div>
    </el-row>

    <!-- 共一和通讯提示内容 -->
    <el-row justify="center" class="con-cor">
        {{ con_and_corresponding_author }}
    </el-row>

    <!-- 强调内容 -->
    <el-row justify="center" class="emphasis" v-for="emphasis in emphases">
        {{ emphasis }}
    </el-row>

    <!-- 提供引导按钮 -->
    <el-row justify="center" style="margin-bottom: 20px;">
      <el-col :span="20">
        <el-row justify="center">
          <a
            v-for="button in buttons"
            :key="button.name"
            :href="button.link || null"
            :target="button.link ? '_blank' : null"
            :rel="button.link ? 'noopener noreferrer' : null"
          >
            <el-button class="guidance-button" size="default" :color="btn_color" :disabled="button.disabled" round>
              <el-icon :size="18">
                <component :is="button.component" />
              </el-icon>
              <span class="btn-text">{{ button.name }}</span>
            </el-button>
          </a>
        </el-row>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

/* 文章标题字体、字间距、居中排布、字号 */
.paper-title {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 0;
  font-size: 40px;
  line-height: 1.18;
  margin: 28px 0 24px;
  text-align: center;
}

/* 姓名和地址按钮 */
.title-button {
  margin: 10px 3px;
}

/* 姓名和地址按钮光标悬浮 */
.title-button:hover {
  margin: 10px 8px;
}

/* 引导材料按钮 */
.guidance-button {
  margin: 8px 5px;
  box-shadow: #d8d8d8 1px 1px 1px 1px;
}

/* 姓名属性 */
.author {
  font-size: 22px;
  margin-left: 0;
  white-space: nowrap;
}

/* 作者名单容器 */
.author-row {
  line-height: 1.35;
  margin: 2px auto 8px;
  max-width: 1120px;
  padding: 0 16px;
}

/* 单个作者 */
.author-item {
  display: inline-flex;
  align-items: baseline;
  margin: 3px 14px;
}

/* 姓名上标属性 */
.name_sup {
  color: #000000; 
  font-size: 0.65em;
  margin-left: 1px;
  vertical-align: super;
}

/* 地址属性 */
.address {
  font-size: 22px;
}

/* 地址名单容器 */
.address-row {
  flex-direction: column;
  line-height: 1.3;
  margin: 4px auto 0;
  max-width: 1180px;
  padding: 0 16px;
}

/* 单个地址 */
.address-item {
  max-width: 100%;
  text-align: center;
}

/* 地址上标属性 */
.address_sup {
  color: #000000; 
  font-size: 0.65em;
  margin-right: 1px;
  vertical-align: super;
}

/* 头像属性 */
.el-avatar {
  margin-right: 6px;
  box-shadow: #b7b7b7 0px 0px 3px 1px;
}

/* 共一和通讯文字属性 */
.con-cor {
  font-family: Arial;
  font-size: 14px;
  margin: 18px 0px;
  text-align: center;
}

/* 强调信息属性 */
.emphasis {
  color: chocolate;
  font-weight: bold;
  margin: 8px;
  font-size: 22px;
  text-align: center;
}

/* 引导材料按钮文字属性 */
.btn-text {
  font-size: 18px;
  color: #ffffff;
}

@media (max-width: 768px) {
  .paper-title {
    font-size: 28px;
    line-height: 1.22;
  }

  .author {
    font-size: 18px;
  }

  .author-item {
    margin: 2px 8px;
  }

  .address {
    font-size: 16px;
  }
}

.el-alert {
  margin: 10px 0 0;
}

.el-alert:first-child {
  margin: 0;
}

.logo {
  width: 150px; 
  height: 150px;
  border-radius: 50%;
  box-shadow: #ced3dc 0px 0px 3px 2px;
  margin-top: 40px;
}

/* 手机端链接样式处理 */
a:-webkit-any-link {
  text-decoration: none;
}

/* 取消鼠标焦点悬浮在链接上的颜色装饰 */
a:hover {
  color: inherit;
  border-bottom: none;
}

/* 链接装饰，取消下划线和链接颜色 */
a {
	text-decoration: None;
	color: inherit;
}

</style>
