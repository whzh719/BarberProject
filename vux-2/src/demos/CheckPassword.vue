<template>
  <div>
    <group  style="margin:15px;">
      <x-input type="text" placeholder="请输入密码" v-model="password" ref="password"  @on-change="change"></x-input>
      <x-input placeholder="请确认密码" v-model="password2" type="text" :equal-with="password"></x-input>
     
      <x-button type="primary" @click.native ="onClickOk" >确定</x-button>
      
    </group>
  </div>
</template>

<script>
import { Box, XInput, Group, XButton, Cell } from 'vux'

export default {
  name: 'checkpassword',
  components: {
    XInput,
    XButton,
    Group,
    Cell,
    Box
  },
  data () {
    return {
      valiedCode: '',
      password: '',
      password2: ''
    }
  },
  methods: {
    onClick (val) {
      console.log(val)
    },
    onClickOk () {
      this.password = this.$refs.password.value
      if (this.password !== this.password2) {
        console.log('密码不一至')
      } else {
        console.log('ok' + this.password)
      }
    },
    change (value) {
      console.log('change:', value)
    },
    getValidCode (val) {
      // this.validCode = this.$refs.valiedCode.value
      // console.log('dd:' + this.validCode)
    },
    onEnter (val) {
      console.log('click enter!', val)
    }
  }
}
</script>

