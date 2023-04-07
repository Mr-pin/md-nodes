# @功能
## 插件  [vue-tribute](https://vue-tribute.netlify.app/)
### 使用步骤

####安装
$ npm install tributejs vue-tribute@next --save
####导入
```js
import VueTribute from 'vue-tribute'
createApp(App).use(VueTribute).mount("#app")
<vue-tribute :options="atDialogData" class="editor-wrapper footer-middle">
      <div
        class="editor"
        ref="inputRef"
        id="testMultiple"
        contenteditable
        @input="valueChange"
      ></div>
</vue-tribute>
//配置项
 atDialogData: {
        trigger: "@",
        values: [
          { key: BAIDU, value: BAIDU, avatar: baiduavatar },
          { key: CHAT_GPT, value: CHAT_GPT, avatar: openaiavatar },
          { key: ALL, value: ALL, avatar: allavatar },
        ],
        positionMenu: true,
        noMatchTemplate: "<li>暂无数据</li>",
        selectTemplate: function (item) {
          return (
            '<span contenteditable="false"><a>' +
            "@" +
            item.original.value +
            "</a></span>"
          );
        },
        // 下拉菜单每一项的HTML内容
        // menuItemTemplate: function (item) {
        //   return '<img class="tribute-img" src="' + item.original.avatar + '">' + item.string;
        // },
      },
    //样式配置
    .tribute-container {
        position: absolute;
        top: 0;
        left: 0;
        ...
  }
```
#### 配置项参考 [tributejs](https://github.com/zurb/tribute)

#### 案例参考 

[demo地址(类似飞书输入框)](https://zhangxinxu.gitee.io/okr-at-mention/)
[项目地址](https://gitee.com/zhangxinxu/okr-at-mention)
[bug讲解/contentediable插入span标签的光标问题](https://www.zhangxinxu.com/wordpress/2022/08/gitee-feishu-okr-at-mention/)

[demo2](https://github.com/zuoxiaobai/fedemo/blob/master/src/vuecli-demo/src/views/at/index.vue)


#长按事件的处理
## 插件 [vue-touch](https://github.com/vuejs/vue-touch)

### 插件安装 
npm install vue-touch@next --save

###插件导入与使用

```js
var VueTouch = require('vue-touch')
Vue.use(VueTouch, {name: 'v-touch',maxDistance: 10, pressTime: 650})

<v-touch v-on:press="handlePress(chat)">
    <img v-if="chat.avatar != null" :src="chat.avatar" alt="" />
</v-touch>
 //myMain组件
 handlePress(item) {
      if(item.type==='my') {
        return;
      }
      let type, name, id;
      if (item.type === "baidu") {
          type = "WenXin";
        } else if (item.type === "openai") {
          type = "chatGPT";
        } else if (item.type === "together") {
          type = "所有人";
        }
        this.$emit("selectChatByAvatar", name);
  }
 //父组件
 selectChatByAvatar(name) {
      const content = `<span contenteditable="false"><a>
            @${name}
            </a></span>&nbsp;`;
      this.$refs.chatFooter.$refs.inputRef.innerHTML += content;
 },