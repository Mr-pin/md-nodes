# 1.点击其它地方，弹窗收起
```js
    bindEvent() {
      let body = document.querySelector("body");
      body.addEventListener("click", (e) => {
        if (!e.target.parentNode.parentNode.className.includes("at-dialog")) {
          this.showDialog = false;
        }
      });
    },