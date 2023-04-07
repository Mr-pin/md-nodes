# 移动端禁用长按
```css
  //阻止移动端长按事件
  -webkit-touch-callout: none; //系统默认菜单被禁用
  -webkit-user-select: none; //webkit浏览器
  -moz-user-select: none; //火狐
  -ms-user-select: none; //IE10
  user-select: none;
  pointer-events: none;


# 禁用滚动条
```css
//禁用滚动条
* {
    &::-webkit-scrollbar {
        display: none;
        /* Chrome Safari */
    }

    overflow: -moz-scrollbars-none;
    /* fire fox */
    scrollbar-color: #fff !important;
    scrollbar-width: none;
    -ms-overflow-style: none;
    /* IE 10+ */
}
```
# 响应式宽度布局（头部响应式高度，底部固定，中间自适应）
```scss
.el-container {
  height: 96vh;
  display: flex;
  flex-direction: column;
  .el-main {
    flex: 1;
  }
}
@media screen and (min-width: 768px) {
  .chat-header {
    height: 7rem;
  }
}
/* sm屏幕 */
@media screen and (min-width: 640px) and (max-width: 768px) {
  .header-wrap {
    padding: 0 5px;
    height: 5.8rem;
    .header-left {
      .app-name {
        font-size: 18px !important;
        line-height: 27px !important;
      }
      .app-desc {
        font-size: 12px !important;
        line-height: 18px !important;
      }
    }
  }
}
/* xs屏幕 */
@media screen and (max-width: 640px) {
  .header-wrap {
    height: 4.6rem;
    padding: 0 5px;
  }
  .header-left {
    .avatar-wrap {
      width: 40px;
      height: 40px;
      img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
      }
    }
    .app-name {
      font-size: 18px !important;
      line-height: 27px !important;
    }
    .app-desc {
      font-size: 12px !important;
      line-height: 18px !important;
    }
  }
}
```
```html
 <el-footer style="height: 84px">
    <my-footer @handlScroll="handlScroll" />
  </el-footer>
```

# SCSS的一些

