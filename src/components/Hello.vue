<style scoped>
  .layout{
    border: 1px solid #d7dde4;
    background: #f5f7f9;
  }
  .layout-logo{
    width: 100px;
    height: 30px;
    border-radius: 3px;
    float: left;
    position: relative;
    font-size: 30px;
    left: 20px;
    color: #FFF;
  }
  .layout-nav{
    min-width: 420px;
    margin: 0 auto;
    margin-left: 200px;
  }
  .layout-assistant{
    width: 300px;
    margin: 0 auto;
    height: inherit;
  }
  .layout-breadcrumb{
    padding: 10px 15px 0;
  }
  .layout-content{
    min-height: 200px;
    margin: 15px;
    overflow: hidden;
    background: #fff;
    border-radius: 4px;
  }
  .layout-content-main{
    padding: 10px;
    min-height: 500px;
  }
  .layout-copy{
    text-align: center;
    padding: 10px 0 20px;
    color: #9ea7b4;
  }
  .layout-bread-crumb{
    padding-top: 10px;
    padding-left: 10px;
    text-align: left;
  }
</style>
<template>
  <div class="layout">
    <Menu mode="horizontal" theme="dark" active-name="1">
      <div class="layout-logo">Juzoom</div>
      <div class="layout-nav">
        <Menu-item name="1">
          <Icon type="ios-navigate"></Icon>
          导航一
        </Menu-item>
        <Menu-item name="2">
          <Icon type="ios-keypad"></Icon>
          导航二
        </Menu-item>
        <Menu-item name="3">
          <Icon type="ios-analytics"></Icon>
          导航三
        </Menu-item>
        <Menu-item name="4">
          <Icon type="ios-paper"></Icon>
          导航四
        </Menu-item>
      </div>
    </Menu>
    
    <div class="layout-content">
      <Row>
        <i-col span="4">
          <Menu active-name="1-2" width="auto" :open-names="['1']">
            <Submenu name="1">
              <template slot="title">
                <Icon type="ios-navigate"></Icon>
                导航一
              </template>
              <Menu-item name="1-1">选项 1</Menu-item>
              <Menu-item name="1-2">选项 2</Menu-item>
              <Menu-item name="1-3">选项 3</Menu-item>
            </Submenu>
            <Submenu name="2">
              <template slot="title">
                <Icon type="ios-keypad"></Icon>
                导航二
              </template>
              <Menu-item name="2-1">选项 1</Menu-item>
              <Menu-item name="2-2">选项 2</Menu-item>
            </Submenu>
            <Submenu name="3">
              <template slot="title">
                <Icon type="ios-analytics"></Icon>
                导航三
              </template>
              <Menu-item name="3-1">选项 1</Menu-item>
              <Menu-item name="3-2">选项 2</Menu-item>
            </Submenu>
          </Menu>
        </i-col>
        <i-col span="19">
          <div class="layout-bread-crumb">
            <Breadcrumb>
              <Breadcrumb-item href="/">Home</Breadcrumb-item>
              <Breadcrumb-item href="/components/breadcrumb">Components</Breadcrumb-item>
              <Breadcrumb-item>Breadcrumb</Breadcrumb-item>
            </Breadcrumb>
          </div>
          <div class="layout-content-main">
            <div>
              <Row type="flex" justify="space-between">
                <Col span="8">
                  <label>名称</label>
                  <Input v-model="value" placeholder="请输入..." style="width: 220px"></Input>
                </Col>
                <Col span="8">
                  <label>编号</label>
                  <Input v-model="value" placeholder="请输入..." style="width: 220px"></Input>
                </Col>
                <Col span="8">
                  <label span="4">手机号</label>
                  <Input v-model="value" placeholder="请输入..." style="width: 220px"></Input>
                </Col>
              </Row>
              <br>
              <Row type="flex" justify="space-between">
                <Col span="4">
                  <Button type="primary" icon="ios-search">搜索</Button>
                  <Button type="info">清空</Button>
                </Col>
              </Row>
            </div>
            <div style="margin-top:20px">
              <Table border :columns="columns1" :data="data1"></Table>
            </div>
            <div style="margin-top:20px;float:right">
              <Page :total="100"></Page>
            </div>
          </div>
        </i-col>
      </Row>
    </div>
    <div class="layout-copy">
        2011-2016 &copy; TalkingData
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: '22222222222222222222',
      value: '',
      columns1: [
        {
          title: '姓名',
          key: 'name'
        },
        {
          title: '年龄',
          key: 'age'
        },
        {
          title: '地址',
          key: 'address'
        }
      ],
      data1: [
        {
          name: '王小明',
          age: 18,
          address: '北京市朝阳区芍药居'
        },
        {
          name: '张小刚',
          age: 25,
          address: '北京市海淀区西二旗'
        },
        {
          name: '李小红',
          age: 30,
          address: '上海市浦东新区世纪大道'
        },
        {
          name: '周小伟',
          age: 26,
          address: '深圳市南山区深南大道'
        }
      ]
    }
  }
}
</script>
