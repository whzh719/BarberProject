<template>
    <div class="weui-panel__bd" style="background-color:#ffffff">
      <div  class="weui-media-box weui-media-box_appmsg">
                <div class="weui-media-box__hd" v-if="infoModel.src">
                  <img class="weui-media-box__thumb" :src="infoModel.src" >
                </div>
                <div class="weui-media-box__bd">
                  <h4 class="weui-media-box__title">
                    <span>姓名：{{infoModel.title}}</span>
                  </h4>
                  <p class="weui-media-box__desc" v-html="infoModel.desc"></p>
                </div>
      </div>
      <div>
        <div v-for="item in assessList" class="weui-media-box weui-media-box_appmsg">
                <div class="weui-media-box__hd" v-if="item.phone">
                  <img class="weui-media-box__thumb" :src="item.phone" >
                </div>
                <div class="weui-media-box__bd">
                  <h4 class="weui-media-box__title">
                    <span>{{item.name}}</span>
                    <span style="float:right">{{item.datetime}}</span>
                  </h4>
                    <cell title="手艺">
                      <rater v-model="item.level"></rater>
                    </cell>
                    <cell title="服务">
                      <rater v-model="item.service" :max="5"></rater>
                    </cell>
                  <p class="weui-media-box__desc" v-html="item.remark"></p>
                </div>
        </div>
      </div>
    </div>
</template>

<script>
import { Rater, Group, Cell, Range } from 'vux'

const infoModel = {
  title: '测试',
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  desc: '由各种物质组成的巨型球状天体，叫做星球'
}
const assess = [{
  name: '匿名用户',
  phone: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  datetime: '2019年4月3日',
  level: 3,
  service: 4,
  remark: '评语'
},
{
  name: '匿名用户',
  phone: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  datetime: '2019年4月3日',
  level: 3,
  service: 4,
  remark: '评语'
},
{
  name: '匿名用户',
  phone: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  datetime: '2019年4月3日',
  level: 3,
  service: 4,
  remark: '评语'
},
{
  name: '匿名用户',
  phone: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  datetime: '2019年4月3日',
  level: 3,
  service: 4,
  remark: '评语'
}
]

export default {
  components: {
    Rater,
    Group,
    Cell,
    Range
  },
  data () {
    return {
      infoModel: infoModel,
      assessList: assess
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