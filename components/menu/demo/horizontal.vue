<template>
<div>
  <md>
  ## 顶部导航
  水平的顶部导航菜单。
  </md>
  <Menu
    v-model="current"
    mode="horizontal"
  >
    <MenuItem key="mail">
      <Icon type="mail" />Navigation One
    </MenuItem>
    <MenuItem key="app" disabled>
      <Icon type="appstore" />Navigation Two
    </MenuItem>
    <SubMenu>
      <span slot="title"><Icon type="setting" />Navigation Three - Submenu</span>
      <MenuItemGroup title="Item 1">
        <MenuItem key="setting:1">Option 1</MenuItem>
        <MenuItem key="setting:2">Option 2</MenuItem>
      </MenuItemGroup>
      <MenuItemGroup title="Item 2">
        <MenuItem key="setting:3">Option 3</MenuItem>
        <MenuItem key="setting:4">Option 4</MenuItem>
      </MenuItemGroup>
    </SubMenu>
    <MenuItem key="alipay">
      <a href="https://ant.design" target="_blank" rel="noopener noreferrer">Navigation Four - Link</a>
    </MenuItem>
  </Menu>
</div>
</template>
<script>
import { Menu, Icon } from 'antd'
const SubMenu = Menu.SubMenu
const MenuItemGroup = Menu.ItemGroup
const MenuItem = Menu.Item
export default {
  data () {
    return {
      current: ['mail'],
    }
  },
  components: {
    Menu,
    Icon,
    SubMenu,
    MenuItemGroup,
    MenuItem,
  },
}

</script>
