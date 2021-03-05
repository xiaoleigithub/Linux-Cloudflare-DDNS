# Linux-Cloudflare-DDNS
- 项目源代码在这里：<a target="_blank" href="https://gist.github.com/xiaoleigithub/8fcc0d6fa03f1a39e900445a559cdb35">点击前往</a>
## 操作准备

## 操作步骤
### 获取API密钥
- Cloudflare API密钥：	b*************************************b <br>
### 下载脚本
- 得到API后，在Linux系统中把脚本下载到/ usr / local / bin目录，命名为cf-ddns.sh，并修改脚本的权限： <br>

获取root权限
```
sudo -i
```
下载脚本、修改权限
```
curl https://gist.githubusercontent.com/xiaoleigithub/8fcc0d6fa03f1a39e900445a559cdb35/raw > /usr/local/bin/cf-ddns.sh && chmod +x /usr/local/bin/cf-ddns.sh
```

备用链接
```
curl https://gist.githubusercontent.com/benkulbertis/fff10759c2391b6618dd/raw > /usr/local/bin/cf-ddns.sh && chmod +x /usr/local/bin/cf-ddns.sh
```
国内节点：看情况选择是否需要
### 编辑脚本
```
vi  /usr/local/bin/cf-ddns.sh
```
- 其中，在auth_email中填入CloudFlare账号的邮箱，在auth_key输入前面获取的API，zone_name填入域名zhaozhuji.net，record_name填入DDNS的域名ddns.zhaozhuji.net。
- 例如
```
auth_email="youxiang@qq.com"
auth_key="b************************b"
zone_name="ssp01.club"
record_name="aliyun-hk-01.ssp01.club"
```

### 执行脚本
```
bash /usr/local/bin/cf-ddns.sh
```
- 如果提示IP changed to: X.X.X.X，表明配置成功.

### 添加定时任务
- crontab定时运行；脚本配置成功后，需要让它定时运行。这里设置每5分钟运行一次cf-ddns.sh脚本。
```
crontab -e
*/5 * * * *  /usr/local/bin/cf-ddns.sh >/dev/null 2>&1
```

# 联系站长
- <a target="_blank" href="https://t.me/joinchat/JJVz3RGJmQHqSmoBJdNSNA">电报群组</a>
- <a target="_blank" href="http://xxlei.win/">小垒博客站点</a>
- <a target="_blank" href="https://cdn77.manage.hitun.io/auth/register?affid=2406">停机坪-海豚湾（最低￥9/月）</a>
- <a target="_blank" href="https://www.youtube.com/channel/UCXhWKWQ-n4ktWKp4zQAGdTw">Youtube频道</a>
- 你也可以直接提交问题单“Issues”
