<template>
    <div>
        <div class="weui-panel weui-panel_access">
            <div class="weui-panel__hd" v-if="header"  v-html="header">
                <slot name="header"></slot>
            </div>
            <div class="weui-panel__bd">
                <div class="money">余额：￥{{money}}</div>
                <div style="margin: 15px;">
                    <flexbox>
                        <flexbox-item ><div class="purse-demo" @click="depositmoney" >充值</div></flexbox-item>
                        <flexbox-item ><div class="purse-demo" @click="cashout">提现</div></flexbox-item>
                    </flexbox>
                </div>
                <div>
                    <x-button type="primary" @click.native="bindaccount"  style="background-color:#FF9900; height:50px;line-height:50px;">绑定帐号</x-button>
                    <x-button type="warn"  @click.native="unbindaccount" style="background-color:#FF9900; height:50px;line-height:50px;">解除绑定</x-button>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { XButton, Flexbox, FlexboxItem, Divider } from 'vux'

const header = '我的钱包'
const money = 30000.98

export default {
  name: 'purse',
  components: {
    Flexbox,
    FlexboxItem,
    Divider,
    XButton
  },
  methods: {
    depositmoney () {
      console.log('depositmoney')
    },
    cashout () {
      console.log('Cashout')
    },
    bindaccount () {
      console.log('bindaccount')
    },
    unbindaccount () {
      console.log('unbindaccount')
    }
  },
  data () {
    return {
      header: header,
      money: money
    }
  }
}
</script>

<style lang="less">
@import '../styles/weui/widget/weui_cell/weui_cell_global';
@import '../styles/weui/widget/weui_cell/weui_access';
@import '../styles/weui/widget/weui_panel/weui_panel';
@import '../styles/weui/widget/weui_media_box/weui_media_box';
@import '~vux/src/styles/1px.less';

.purse-demo {
  text-align: center;
  color: #fff;
  background-color: #FF9900;
  border-radius: 4px;
  background-clip: padding-box;
  height: 50px;
  line-height: 50px;
  font-weight: bold;
  font-size: 18px;
}
.money{
    height: 100px;
    margin: 15px;
    line-height: 100px;
    text-align: center;
    font-weight: bold;
    font-size: 28px;
}
</style>
