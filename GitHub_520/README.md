# [GitHub520](https://github.com/521xueweihan/GitHub520)

## 一、使用方法

​		文件：`https://raw.hellogithub.com/hosts`

​		JSON：`https://raw.hellogithub.com/hosts.json`

####  修改 hosts 文件

hosts 文件在每个系统的位置不一，详情如下：

- Windows 系统：`C:\Windows\System32\drivers\etc\hosts`
- Linux 系统：`/etc/hosts`
- Mac（苹果电脑）系统：`/etc/hosts`
- Android（安卓）系统：`/system/etc/hosts`
- iPhone（iOS）系统：`/etc/hosts`

修改方法，把第一步的内容复制到文本末尾：

1. Windows 使用记事本。
2. Linux、Mac 使用 Root 权限：`sudo vi /etc/hosts`。
3. iPhone、iPad 须越狱、Android 必须要 root。

#### 2.1.2 激活生效

大部分情况下是直接生效，如未生效可尝试下面的办法，刷新 DNS：

1. Windows：在 CMD 窗口输入：`ipconfig /flushdns`
2. Linux 命令：`sudo nscd restart`，如报错则须安装：`sudo apt install nscd`
3. Mac 命令：`sudo killall -HUP mDNSResponder`

**Tips：** 上述方法无效可以尝试重启机器。

### 2.2 自动方式

**Tip**：推荐 [SwitchHosts](https://github.com/oldj/SwitchHosts) 工具管理 hosts

以 SwitchHosts 为例，看一下怎么使用的，配置参考下面：

- Title: 随意
- Type: `Remote`
- URL: `https://raw.hellogithub.com/hosts`
- Auto Refresh: 最好选 `1 hour`

如图：

[![img](https://github.com/521xueweihan/GitHub520/raw/main/img/switch-hosts.png)](https://github.com/521xueweihan/GitHub520/blob/main/img/switch-hosts.png)

这样每次 hosts 有更新都能及时进行更新，免去手动更新。

### 2.3 AdGuard Home 用户（自动方式）

在 **过滤器>DNS 封锁清单>添加阻止列表>添加一个自定义列表**，配置如下：

- 名称: 随意
- URL: `https://raw.hellogithub.com/hosts`（和上面 SwitchHosts 使用的一样）

如图：

[![img](https://github.com/521xueweihan/GitHub520/raw/main/img/AdGuard-rules.png)](https://github.com/521xueweihan/GitHub520/blob/main/img/AdGuard-rules.png)

更新间隔在 **设置>常规设置>过滤器更新间隔（设置一小时一次即可）**，记得勾选上 **使用过滤器和 Hosts 文件以拦截指定域名**

[![img](https://github.com/521xueweihan/GitHub520/raw/main/img/AdGuard-rules2.png)](https://github.com/521xueweihan/GitHub520/blob/main/img/AdGuard-rules2.png)

**Tip**：不要添加在 **DNS 允许清单** 内，只能添加在 **DNS 封锁清单** 才管用。另外，AdGuard for Mac、AdGuard for Windows、AdGuard for Android、AdGuard for IOS 等等 **AdGuard 家族软件** 添加方法均类似。

### 2.4 Chrome 插件方式

[FasterHosts](https://github.com/gauseen/faster-hosts) 是个 Chrome 插件，主要原理是拦截浏览器的某些请求，将 `domain` 替换成访问速度较快的那个。hosts 资源来自 [GitHub520](https://github.com/521xueweihan/GitHub520)，每 1 小时更新一次。

> 1. 下载 [FasterHosts](https://github.com/gauseen/faster-hosts/archive/master.zip) 然后解压，找到 `extension` 子目录
> 2. 打开 Chrome，输入: `chrome://extensions/`
> 3. 打开「开发者模式」
> 4. 选择「加载已解压的扩展程序」，然后定位到刚才解压的文件夹里面的 `extension` 目录，确定
> 5. 这就安装好了，关闭「开发者模式」

## 三、效果对比

之前的样子：

[![img](https://github.com/521xueweihan/GitHub520/raw/main/img/old.png)](https://github.com/521xueweihan/GitHub520/blob/main/img/old.png)

修改完 hosts 的样子：

[![img](https://github.com/521xueweihan/GitHub520/raw/main/img/new.png)](https://github.com/521xueweihan/GitHub520/blob/main/img/new.png)

## TODO

-  定时自动更新 hosts 内容
-  hosts 内容无变动不会更新
-  寻到最优 IP 解析结果

## 声明

[![知识共享许可协议](https://camo.githubusercontent.com/f63f0d2ca772bfd09afac289fa85d95f01809143efaeca8f014c78ac3f85244d/68747470733a2f2f6c6963656e7365627574746f6e732e6e65742f6c2f62792d6e632d6e642f342e302f38387833312e706e67)](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh)
本作品采用 [署名-非商业性使用-禁止演绎 4.0 国际](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh) 进行许可
