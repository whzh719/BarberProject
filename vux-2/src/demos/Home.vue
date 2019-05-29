<template>
  <div>
    <div>
      <swiper :list="swiper_list" v-model="demo01_index" @on-index-change="demo01_onIndexChange"></swiper>
    </div>
    <div style=" margin-top: 10px;">
      <flexbox>
        <flexbox-item><div class="flex-demo">个人理发</div></flexbox-item>
        <flexbox-item><div class="flex-demo">团体理发</div></flexbox-item>
      </flexbox>
    </div>

    <div>
      <tab>
        <tab-item selected @on-item-click="onItemClick">推荐</tab-item>
        <tab-item @on-item-click="onItemClick">附近</tab-item>
      </tab>
      <div id="tab1" style="di">
       <panel :list="tabdatalist"></panel>
      </div>
     
    </div>

    <br>
    <p class="vue-version">current vue version: {{ vueVersion }}</p>
  </div>
</template>

<script>
import { Panel, Tab, TabItem, Flexbox, FlexboxItem, Swiper, Cell, Group, Badge, Divider } from 'vux'

import pkg from '../../package.json'
const version = pkg.version
const vueVersion = pkg.devDependencies.vue
const swiperList = [{
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vvsr72j20p00gogo2.jpg',
  title: '一朵fua'
}, {
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw1k2wj20p00goq7n.jpg',
  title: '一辆车'
}, {
  url: 'javascript:',
  img: 'http://pic1.win4000.com/wallpaper/2018-09-19/5ba1efdcb8e7c.jpg', // 404
  title: '一次旅行',
  fallbackImg: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw50iwj20ff0aaaci.jpg'
}]

const tab1DataList = [{
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
  title: '推荐1',
  desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
  url: '/component/cell'
}, {
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '推荐2',
  desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
  url: '/component/radio'
}]

const tab2DataList = [{
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
  title: '附近1',
  desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
  url: '/component/cell'
}, {
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '附近12',
  desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
  url: '/component/radio'
}]

export default {
  components: {
    Swiper,
    Cell,
    Group,
    Badge,
    Divider,
    Flexbox,
    FlexboxItem,
    Tab,
    TabItem,
    Panel
  },
  methods: {
    onSwiperItemIndexChange (index) {
      console.log('demo item change', index)
    },
    demo01_onIndexChange (index) {
      this.demo01_index = index
    },
    onItemClick (index) {
      if (index === 0) {
        this.tabdatalist = tab1DataList
      } else {
        this.tabdatalist = tab2DataList
      }
      // index === 1 ? console.log('附近:', index) : console.log('测试')
      // index === 1 ? this.tabdatalist=tab1DataList : this.tabdatalist=tab2DataList
      // this.tabdatalist = index === 1 ? tab1DataList : tab2DataList
      // console.log(index === 1 ? "附近" : "测试")
      // this.tabdatalist = index === 1 ? tab1DataList : tab2DataList
      // this.tabdatalist.push({
      //   src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
      //   fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
      //   title: '标题一',
      //   desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
      //   url: '/component/cell'
      // })
      // console.log('on item click:', index)
    }
  },
  data () {
    return {
      swiper_list: swiperList,
      demo01_index: 0,
      version,
      vueVersion,
      tabdatalist: tab1DataList
    }
  }
}

</script>

<style scoped>
.vue-version {
  text-align: center;
  font-size: 12px;
  color: #ccc;
}
.center {
  margin-top: 15px;
  text-align: center;
}
.vux-notice {
  color: #666;
  line-height: 40px;
}
.demo-icon {
  margin-right: 15px;
}
.vux-title {
  vertical-align: middle;
  text-align: center;
  color: #04BE02;
  display: inline-block;
  width: 75px;
  height: 75px;
  line-height: 75px;
  border-radius: 50%;
}
body {
  font-family: Helvetica, sans-serif;
  background-color: #fbf9fe;
}
.demo-tip {
  background-color: #fefcec;
  color: #f76a24;
  font-size: 12px;
  padding: 5px 10px;
  margin-top: 15px;
}
.flex-demo {
  text-align: center;
  color: #fff;
  height: 50px;
  background-color: #f76a24;;
  border-radius: 0px;
  background-clip: padding-box;
  font-weight: bold;
  font-size: 18px;
  line-height: 50px;
}
</style>
