<template>
    <div>
        <div class="weui-media-box weui-media-box_appmsg">
                <div class="weui-media-box__hd" v-if="infoModel.src">
                    <img class="weui-media-box__thumb" :src="infoModel.src" >
                </div>
                <div class="weui-media-box__bd">
                    <h4 class="weui-media-box__title">
                        <span>姓名：{{infoModel.name}}</span>
                        <br/>
                        <span>{{infoModel.location}}</span>
                    </h4>
                </div>
        </div>
        <div>
            <div class="selfcontent" v-html="infoModel.desc" ></div>
        </div>
         
    </div>
</template>

<script>
import { Rater, Group, Cell, Range } from 'vux'

const infoModel = {
  name: '测试',
  age: '20',
  location: '北京昌平区回龙观西大街86号',
  src: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg',
  desc: '<p>Skwend烫发师 出生美发世家，父亲韩国籍华人，是韩国最著名的发型设计师和美容化妆师之一，第一届韩国十大发型设计师之一，在他父亲生活的年代，也正是陶瓷烫新起流行的年代；从小Skywend就受到父亲以及父亲行业朋友的熏陶，从小对美发设计和烫发技术有着独特的灵感天赋，Skywend从小就有远大的梦想，希望长大后能把父亲的美发技术以及韩国的先进的烫发技术带出韩国，带入亚洲各个区域。</p><p>1998年毕业于韩国技术教育大学后。抱着梦想回国，在父亲的好朋友美域老板手下工作，美域老板看他是个很不错的年轻人，也吃惊于他对美发的独到见解和特殊设计创新理念，对他特别的关注和重视。任命为发型设计部门经理，主要为陶瓷烫发机生产设计提供建议和意见，为美域各区域客户进行烫发技术培训指导。</p><p>2001年10月美域在马来西亚开分公司，特派为美域马来西亚分公司担任销售和技术总监。期间受马来西亚美发行业的影响，任命为马来西亚美发行业发型设计总指导师。美博会场连续几届发型设计指导师等。</p><p>所获证书：《马来西亚最高级别发型师》《马来西亚发型设计及培训高级讲师》等最高级别证书。</p>'
}

export default {
  name: 'Selfinfoview',
  components: {
    Rater,
    Group,
    Cell,
    Range
  },
  data () {
    return {
      infoModel: infoModel
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
.selfcontent {
    margin: 0px;
    padding: 15px;
    line-height: 30px;
    color: #666666;
    text-indent: 2em;
}
 .selfcontent p {
        padding: 100px;
        background-color: red;
    }
p {
        padding: 100px;
        background-color: red;
    }
</style>

<style>
.selfcontent {
    margin: 0px;
    padding: 10px;
    line-height: 30px;
    color: #666666;
    text-indent: 2em;
   
}
 .selfcontent p {
        padding: 5px;
    }

</style>
