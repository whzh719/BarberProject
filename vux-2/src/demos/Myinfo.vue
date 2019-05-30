<template>
    <div >
        <div class="weui-media-box weui-media-box_appmsg" style=" text-align: center;">
          <div class="weui-media-box__hd" style="margin:0 auto; ">
            <img class="weui-media-box__thumb" :src="infoModel.phone" >
          </div>
        </div>
        <div>
            <group>
                <cell is-link title="人个信息" link="/component/tabbar-simple"></cell>
                <cell is-link title="我的关注" link="/component/tabbar-icon"></cell>
                <cell is-link title="我的评价" link="/component/tabbar-icon"></cell>
                <cell is-link title="我的钱包" link="/component/purse"></cell>
                <cell is-link title="联系我们" link="/component/tabbar-icon"></cell>
                <cell is-link title="我的关注" link="/component/tabbar-icon"></cell>
            </group>
        </div>
    </div>
</template>
<script>
import { Tabbar, TabbarItem, Group, Cell } from 'vux'
const infoModel = {
  id: '1',
  phone: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3985098578,2279412978&fm=27&gp=0.jpg'
}

export default {
  name: 'myinfo',
  components: {
    Tabbar,
    TabbarItem,
    Group,
    Cell
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
</style>