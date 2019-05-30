<template>
     <div>
       <div style="overflow:hidde">
          <tab>
              <tab-item selected @on-item-click="onItemClick">理发师</tab-item>
              <tab-item @on-item-click="onItemClick">理发店</tab-item>
          </tab>
       </div>
       <template v-if="type === '1'">
        <div>
            <card >
              <div slot="content" class="card-demo-flex card-demo-content01">
                  <div class="vux-1px-r" >
                    评价
                  </div>
                  <div class="vux-1px-r">
                    订单数
                  </div>
                  <div >
                    价格
                  </div>
                  <div style="text-align: right; padding-right:15px;" v-on:click="onselectev">
                    筛选
                  </div>
              </div>
            </card>
        </div>
          <div class="weui-panel__bd">
              <div v-for="item in list" class="weui-media-box weui-media-box_appmsg">
                <div class="weui-media-box__hd" v-if="item.src">
                  <img class="weui-media-box__thumb" :src="item.src" >
                </div>
                <div class="weui-media-box__bd">
                  <h4 class="weui-media-box__title">
                    <span>姓名：{{item.name}}</span>
                    <span>年龄：{{item.age}}</span>
                    <span>{{item.price}}</span>
                  </h4>
                  <p class="weui-media-box__desc" v-html="item.desc"></p>
                  <p>
                      <flexbox>
                        <flexbox-item ><div v-on:click="viewassess(item.id)" class="flex-demo">查看评价</div></flexbox-item>
                        <flexbox-item ><div v-on:click="selfview(item.id)" class="flex-demo">自我介绍</div></flexbox-item>
                        <flexbox-item ><div v-on:click="apply(item.id)" class="flex-demo">预约</div></flexbox-item>
                      </flexbox>
                  </p>
                </div>
              </div>
          </div>
       </template>
       <template v-if="type === '2'">
        <div  class="weui-panel__bd">
            <card >
              <div slot="content" class="card-demo-flex card-demo-content01">
                  <div class="vux-1px-r" >
                    评价22
                  </div>
                  <div class="vux-1px-r">
                    订单数
                  </div>
                  <div style="text-align: right; padding-right:15px;" v-on:click="onselectev">
                    筛选
                  </div>
              </div>
            </card>
        </div>
          <div>
            <div v-for="item in shops" class="weui-media-box weui-media-box_appmsg">
                <div class="weui-media-box__hd" v-if="item.src">
                  <img class="weui-media-box__thumb" :src="item.src" >
                </div>
                <div class="weui-media-box__bd">
                  <h4 class="weui-media-box__title">
                    <span>{{item.name}}</span>
                  </h4>
                  <p class="weui-media-box__desc" v-html="item.desc"></p>
                  <p>
                      <flexbox>
                        <flexbox-item ><div v-on:click="viewassess(item.id)" class="flex-demo">查看评价</div></flexbox-item>
                        <flexbox-item ><div v-on:click="selfview(item.id)" class="flex-demo">店铺介绍</div></flexbox-item>
                        <flexbox-item ><div v-on:click="apply(item.id)" class="flex-demo">预约</div></flexbox-item>
                      </flexbox>
                  </p>
                </div>
              </div>
          </div>
       </template>
    </div>
</template>

<script>
import { Card, Panel, Tab, TabItem, Flexbox, FlexboxItem, Swiper, Cell, Group, Badge, Divider } from 'vux'
import { go, getUrl } from '../libs/router'

const type = '1'

const tab1DataList = [{
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '推荐1',
  id: '1',
  name: '测试1',
  age: '18',
  price: '30元',
  desc: '由各种物质组成的巨型球状天体，叫做星球。。',
  url: '/component/cell'
}, {
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '推荐2',
  id: '2',
  name: '测试2',
  age: '18',
  price: '30元',
  desc: '由各种物质组成的巨型球状天体，叫做星球。',
  url: '/component/radio'
}]
const shopList = [{
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '推荐1',
  id: '1',
  name: '店铺名称1',
  desc: '由各种物质组成的巨型球状天体，叫做星球。。',
  url: '/component/cell'
}, {
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  title: '推荐2',
  id: '2',
  name: '店铺名称2',
  desc: '由各种物质组成的巨型球状天体，叫做星球。',
  url: '/component/radio'
}]

export default {
  name: 'barberlist',
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
    Panel,
    Card
  },
  methods: {
    onselectev () {
      console.log('selected')
    },
    viewassess (val) {
      this.$router.push('/component/Assessview?id=' + val + '')
      console.log('viewassess' + val)
    },
    selfview (val) {
      console.log('selfview' + val)
      this.$router.push('/component/selfview?id=' + val + '')
    },
    apply (val) {
      console.log('apply' + val)
    },
    onSwiperItemIndexChange (index) {
      console.log('demo item change', index)
    },
    demo01_onIndexChange (index) {
      this.demo01_index = index
    },
    getUrl (url) {
      return getUrl(url, this.$router)
    },
    onItemClick (index) {
      if (index === 0) {
        this.type = '1'
        this.list = tab1DataList
      } else {
        this.type = '2'
      }
    }
  },
  data () {
    return {
      type: type,
      demo01_index: 0,
      list: tab1DataList,
      shops: shopList
    }
  }
}
</script>

<style scoped lang="less">
@import '~vux/src/styles/1px.less';
@import '~vux/src/styles/weui/widget/weui_cell/weui_cell_global';
@import '~vux/src/styles/weui/widget/weui_cell/weui_access';
@import '~vux/src/styles/weui/widget/weui_panel/weui_panel';
@import '~vux/src/styles/weui/widget/weui_media_box/weui_media_box';

.card-demo-flex {
  display: flex;
}
.card-demo-content01 {
  padding: 10px 0;
}
.card-padding {
  padding: 5px;
}
.card-demo-flex > div {
  flex: 1;
  text-align: center;
  font-size: 12px;
}
.card-demo-flex span {
  color: #f74c31;
}

.flex-demo {
  margin-top: 10px; 
  text-align: center;
  color: #fff;
  background-color: #FF9900;
  border-radius: 2px;
  background-clip: padding-box;
  font-size: 14px;
  padding: 3px;
}
</style>
