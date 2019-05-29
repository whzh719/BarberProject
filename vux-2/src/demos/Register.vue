<template>
  <div>
    <group  style="margin:15px;">
      <x-input placeholder="请输入手机号码" mask="999 9999 9999" :max="13" is-type="china-mobile"></x-input>
      <x-input placeholder="发送验证码" class="weui-vcode" ref="valiedCode" v-model="valiedCode" id="txtvaliedCode" >
        <x-button slot="right" type="primary" mini @click.native="getValidCode">发送验证码</x-button>
      </x-input>
     
      <x-button type="primary" link="/component/check-password">下一步</x-button>
      
    </group>
  </div>
</template>
<script>
import { Box, XInput, Group, XButton, Cell } from 'vux'

export default {
  name: 'register',
  components: {
    XInput,
    XButton,
    Group,
    Cell,
    Box
  },
  data () {
    return {
      valiedCode: '12'
    }
  },
  methods: {
    onClick (val) {
      console.log(val)
    },
    change (value) {
      console.log('change:', value)
    },
    getValidCode (val) {
      this.validCode = this.$refs.valiedCode.value
      console.log('dd:' + this.validCode)
    },
    onEnter (val) {
      console.log('click enter!', val)
    }
  }
}
</script>

