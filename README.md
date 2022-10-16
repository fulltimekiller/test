仅适用于Github下部署，大家下载后上传到Github上进行部署，也可以用简单的克隆方案上传到Github。注意项目名称说明不要出现有V2ray、Xray等相关字样。

https://github.com/fulltimekiller/test

Github那边已出现大面积封杀heroku代理项目，大家在github做好隐藏工作哦。。

export default {
    async fetch(request, env) {
      let url = new URL(request.url);
      if (url.pathname.startsWith('/')) {
        url.hostname="example.com";
        let new_request=new Request(url,request);
        return fetch(new_request);
      }
      // Otherwise, serve the static assets.
      return env.ASSETS.fetch(request);
    }
  };
一、操作步骤：

1、在浏览器复制链接   https://dashboard.heroku.com/new?template= 加上上传至Github的项目地址链接，回车进入Heroku参数设置界面

2、之前没有登录记录的话，会先提示注册并或登录Heroku界面，大家自己注册或者登录下

3、Heroku app名称与国家随意

4、输入UUID是必输项，别的可以不用改。建议使用V2rayN等工具生成，点击Deploy app，几秒种后就完成安装。

