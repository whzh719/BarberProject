<template>
    <div>myinfo
        <div></div>
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

export default {
  name: 'myinfo',
  components: {
    Tabbar,
    TabbarItem,
    Group,
    Cell
  }
}
</script>

