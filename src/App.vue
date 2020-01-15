<template>
  <div id="app">
    <el-container>
      <el-header>
        <el-row :gutter="20">
          <el-col :span="16">
            <div class="grid-content bg-purple">
              <h3>
                <img src="@/assets/logo.png" alt="logo" class="logo" /> 勘探板块HSE体系审核监督管理系统
              </h3>
            </div>
          </el-col>
          <el-col :span="8">
            <div class="grid-content bg-purple">
              <ul class="settingBox clearfix">
                <li>
                  <el-badge is-dot class="item">
                    <i class="iconfont icon-xinfeng"></i>
                    <i>消息</i>
                  </el-badge>
                </li>
                <li>
                  <el-badge class="item">
                    <i class="iconfont icon-caidan1"></i>
                    <i>语言</i>
                  </el-badge>
                </li>
                <li>
                  <el-badge class="item">
                    <i class="iconfont icon-yonghu"></i>
                    <i>用户设置</i>
                  </el-badge>
                </li>
                <li>
                  <el-badge class="item">
                    <i class="iconfont icon-shezhi"></i>
                    <i>切换主题</i>
                  </el-badge>
                </li>
                <li>
                  <el-badge class="item">
                    <i class="iconfont icon-wenti-m"></i>
                    <i>操作手册</i>
                  </el-badge>
                </li>
              </ul>
            </div>
          </el-col>
        </el-row>
      </el-header>
      <el-container>
        <el-aside width="200px">
          <el-menu
            default-active="2"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
          >
            <template>
              <el-submenu index="1">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>审核专家</span>
                </template>
                <el-menu-item index="1-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="1-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="2">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>审核资料</span>
                </template>
                <el-menu-item index="2-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="2-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="3">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>方案计划</span>
                </template>
                <el-menu-item index="3-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="3-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="4">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>审核发现</span>
                </template>
                <el-menu-item index="4-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="4-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="5">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>统计分析</span>
                </template>
                <el-menu-item index="5-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="5-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="6">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>系统管理</span>
                </template>
                <el-menu-item index="6-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="6-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="7">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>主页设置</span>
                </template>
                <el-menu-item index="7-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="7-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="8">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>代办事宜</span>
                </template>
                <el-menu-item index="8-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="8-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="9">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>建设项目三同时</span>
                </template>
                <el-menu-item index="9-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="9-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
            <template>
              <el-submenu index="10">
                <template slot="title">
                  <i class="el-icon-s-tools"></i>
                  <span>设备设施检测</span>
                </template>
                <el-menu-item index="10-1" class="el-icon-document">环境竣工验收</el-menu-item>
                <el-menu-item index="10-2" class="el-icon-document">公示公告</el-menu-item>
              </el-submenu>
            </template>
          </el-menu>
        </el-aside>
        <el-main>
          <div class="mainBox">
            <div class="mainTop clearfix">
              <el-tag v-for="tag in tags" :key="tag.name" closable :type="tag.type">{{tag.name}}</el-tag>
              <el-select v-model="value" filterable placeholder="请选择" class="fr" size="mini">
                <el-option
                  v-for="item in options"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value"
                ></el-option>
              </el-select>
            </div>
            <div class="mainContainer">
              <div class="opBtn">
                <el-row>
                  <el-button type="success" size="mini">保存</el-button>
                  <el-button size="mini">返回</el-button>
                </el-row>
              </div>
              <ul class="inpBox clearfix">
                <li class="ibItem clearfix">
                  <h4>
                    基本信息
                    <i class="colLine"></i>
                  </h4>
                  <ul class="inpItem clearfix">
                    <li>
                      <span>项目名称</span>
                      <el-input placeholder="请输入项目名" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>表类型</span>
                      <el-select v-model="value" placeholder="请选择" class="inp300">
                        <el-option
                          v-for="item in options"
                          :key="item.value"
                          :label="item.label"
                          :value="item.value"
                        ></el-option>
                      </el-select>
                    </li>
                  </ul>
                </li>
                <li class="ibItem clearfix">
                  <h4>
                    建设单位情况
                    <i class="colLine"></i>
                  </h4>
                  <ul class="inpItem clearfix" >
                    <li class="searchName">
                      <span>单位名称</span>
                      <el-input placeholder="请输入单位名" clearable class="inp300"></el-input>
                       <el-button icon="el-icon-search" size="mini" class="searchBtn"></el-button>
                    </li>
                    <li>
                      <span>单位性质</span>
                      <el-input placeholder="请输入单位性质" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>隶属关系</span>
                      <el-input placeholder="请输入隶属关系" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>单位地址</span>
                      <el-input placeholder="请输入单位地址" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>邮政编码</span>
                      <el-input placeholder="请输入邮政编码" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>联系人</span>
                      <el-input placeholder="请输入联系人" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>电话</span>
                      <el-input placeholder="请输入电话" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>传真</span>
                      <el-input placeholder="请输入传真" clearable class="inp300"></el-input>
                    </li>
                     <li>
                      <span>E-mail</span>
                      <el-input placeholder="请输入邮箱" clearable class="inp300"></el-input>
                    </li>
                  </ul>
                </li>
                <li class="ibItem clearfix">
                  <h4>
                    运行单位情况
                    <i class="colLine"></i>
                  </h4>
                  <ul class="inpItem clearfix">
                    <li>
                      <span>单位名称</span>
                      <el-input placeholder="请输入单位名" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>单位性质</span>
                      <el-input placeholder="请输入单位性质" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>隶属关系</span>
                      <el-input placeholder="请输入" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>单位地址</span>
                      <el-input placeholder="请输入" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>邮政编码</span>
                      <el-input placeholder="请输入" clearable class="inp300"></el-input>
                    </li>
                    <li>
                      <span>联系人</span>
                      <el-input placeholder="请输入" clearable class="inp300"></el-input>
                    </li>
                  </ul>
                </li>
              </ul>
            </div>
          </div>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>
<script>
// @ is an alias to /src
export default {
  name: "XXX",
  data() {
    return {
      tags: [
        { name: "用户管理" },
        { name: "组织机构管理" },
        { name: "异常日志" },
        { name: "操作日志" },
        { name: "基础权限管理" },
        { name: "权限角色分配" },
        { name: "列表管理" },
        { name: "树形管理" },
        { name: "环境竣工验收", type: "warning" }
      ],
      options: [
        {
          value: "选项1",
          label: "黄金糕"
        },
        {
          value: "选项2",
          label: "双皮奶"
        },
        {
          value: "选项3",
          label: "蚵仔煎"
        },
        {
          value: "选项4",
          label: "龙须面"
        },
        {
          value: "选项5",
          label: "北京烤鸭"
        }
      ],
      value: ""
    };
  },
  components: {},
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>
<style lang="less" >
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
.clearfix::after {
  content: "";
  font-size: 0;
  height: 0;
  visibility: hidden;
  display: block;
  clear: both;
}
.clearfix {
  *zoom: 1;
}
.fl {
  float: left;
}
.fr {
  float: right;
}
.el-header {
  background-color: #5f5ca6;
  color: #fff;
  .logo {
    width: 36px;
    height: 36px;
    position: relative;
    top: 12px;
  }
  .settingBox {
    padding-left: 100px;
    li {
      float: left;
      line-height: 15px;
      text-align: center;
      .el-badge {
        display: flex;
        flex-direction: column;
      }
      .el-badge__content.is-dot {
        width: 6px;
        height: 6px;
      }
      i {
        font-style: normal;
        font-size: 12px;
      }
      .iconfont {
        font-size: 14px;
      }
      margin: 10px;
      // line-height: 40px;
    }
  }
}

.el-aside {
  background-color: #eee;
  color: #000;
  text-align: center;
  height: 629px;
  .el-menu {
    // height: 629px;
    background-color: #eee;
    .el-submenu__title {
      text-align: left;
    }
    .el-menu-item {
      text-align: left;
      color: #999;
    }
  }
}
.el-aside::-webkit-scrollbar {
  display: none;
}
.el-main {
  background-color: #fff;
  color: #333;
  .mainTop {
    height: 50px;
    background-color: #eee;
    line-height: 50px;
    padding: 0 10px;
    box-sizing: border-box;
  }
  .el-input--suffix .el-input__inner {
    padding-right: 0;
  }
  .mainContainer {
    position: relative;
    height: 571px;
    padding: 50px;
    overflow: auto;
    box-sizing: border-box;
    .inpBox {
      .ibItem {
        margin-bottom: 20px;
      }
    }
    h4 {
      border-bottom: 1px dashed #ccc;
      line-height: 25px;
      margin-bottom: 20px;
      position: relative;
      padding: 0 10px;
      .colLine {
        width: 3px;
        height: 20px;
        background-color: #409eff;
        position: absolute;
        top: 0;
        left: 0;
      }
    }
    .inpItem {
      // width: 300px;
      padding-left: 100px;
      li {
        float: left;
        font-size: 14px;
        margin-bottom: 10px;
        span {
          display: inline-block;
          width: 56px;
          text-align: right;
          font-weight: bold;
          margin-right: 10px;
        }
      }
      li:nth-child(2n + 1) {
        margin-right: 100px;
      }
    }
    .inp300 {
      width: 250px;
      .el-input__inner {
        height: 30px;
        line-height: 30px;
      }
      .el-input__icon {
        line-height: 30px;
      }
    }
    .searchName{
      position: relative;
      .searchBtn{
        position: absolute;
        top: 0;
        right: -50px;
      }
    }
  }
  .mainContainer::-webkit-scrollbar {
    display: none;
  }
  .opBtn {
    position: absolute;
    top: 20px;
    right: 30px;
    .el-button + .el-button {
      margin-left: 0;
    }
  }
}
#app {
  .el-main {
    padding: 0;
  }
}
body > .el-container {
  margin-bottom: 40px;
}
</style>
