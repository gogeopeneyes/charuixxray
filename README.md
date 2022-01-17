xray项目

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/likeflowercome/charuixxray.git) 

★代理协议【类型】：vless 或 vmess
★端口：443
★vmess额外id：0
★加密：none
★传输协议：ws
★伪装类型：none
★VLESS路径：/UUID-vless
★VMESS路径：/UUID-vmess
★底层传输安全：tls
★跳过证书验证：false


☆参考CDN加速脚本一：
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
const SingleDay = '替换成自己的heroku域名地址'
const DoubleDay = '替换成自己的heroku域名地址'
addEventListener(
    "fetch",event => {
    
        let nd = new Date();
        if (nd.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }
        
        let url=new URL(event.request.url);
        url.hostname=host;
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX


☆参考CDN加速脚本二：
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
addEventListener(
  "fetch", event => {
    let url = new URL(event.request.url);
    url.host = "替换成自己的heroku域名地址";
    let request = new Request(url, event.request);
    event.respondWith(
      fetch(request)
    )
  }
)
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX


