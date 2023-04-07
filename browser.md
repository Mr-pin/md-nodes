# 判断PC端还是移动端

```js
    let ip = socket.handshake.address.replace(/::ffff:/, "");
    const headers = socket.handshake.headers;
    const realIP = headers['x-forwarded-for'];
    ip = realIP ? realIP : ip;
    const deviceType = this.getDeviceType(socket.handshake.headers["user-agent"].toLowerCase());
    console.log(deviceType);

//根据useragent判读设备类型
  getDeviceType(userAgent) {
    let bIsIpad = userAgent.match(/ipad/i) == "ipad";
    let bIsIphoneOs = userAgent.match(/iphone os/i) == "iphone os";
    let bIsMidp = userAgent.match(/midp/i) == "midp";
    let bIsUc7 = userAgent.match(/rv:1.2.3.4/i) == "rv:1.2.3.4";
    let bIsUc = userAgent.match(/ucweb/i) == "ucweb";
    let bIsAndroid = userAgent.match(/android/i) == "android";
    let bIsCE = userAgent.match(/windows ce/i) == "windows ce";
    let bIsWM = userAgent.match(/windows mobile/i) == "windows mobile";
    if (bIsIpad || bIsIphoneOs || bIsMidp || bIsUc7 || bIsUc || bIsAndroid || bIsCE || bIsWM) {
      return "phone";
    } else {
      return "pc";
    }
  },


  showList {
    '对话1': [],
    '2': [],
    '3': [],
  }

  