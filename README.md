## **【中文简介】**

![img](README/xmolo-zx.png)

这是一个将本地的HA控制网页反向代理到公网, 这样公网就可以轻松访问到HA控制台页面, 并控制家里已经连上HA的硬件. 基于安全方面的考虑, 该组件需要经过Google, GitHub或微信小程序的授权才能正常使用.

由于Home Assistant运行于局域网下, 想要通过外网远程访问HA, 首先HA部署环境所在网络下的路由器支持端口映射(port mapping), 映射后在公网通过ip:port直接访问，同时为了方便访问还需要一个ddns服务来把wan ip和动态域名绑定。但是由于网络供应商的网络环境复杂性, 以及用户自身内网环境复杂性, 很难系统性地总结一套通用有效的方法来实现. 上述技术实施起来比较繁琐, 对普通用户来说门槛较高, 本组件旨在简化用户进行远程访问本地HA控制网络.

**【一键安装】**

在终端直接执行下面命令一键安装molohub:

```shell
curl --silent --show-error --retry 5 https://raw.githubusercontent.com/smarthomefans/molohub/master/auto_install.py | sudo python
```

等待提示安装成功后手动重启Home Assistant即可。

若此方法安装失败，请用下面的方法手动安装。有`curl`组件的Windows用户也可以通过`cmd`执行一键安装（需要去掉命令中的`sudo`）。

**【安装软件】**

- [molohub组件](https://github.com/smarthomefans/molohub)

下载`molohub`文件夹，保存在`<homeassistant配置目录>/custom_components/`目录中，若`custom_components`目录不存在则自行创建。

- homeassistant配置目录在哪?

**Windows用户:** `%APPDATA%\.homeassistant`

**Linux-based用户:** 可以通过执行`locate .homeassistant/configuration.yaml`命令，查找到的`.homeassistant`文件夹就是配置目录。

**群晖Docker用户:** 进入Docker - 映像 - homeassistant - 高级设置 - 卷, `/config`对应的路径就是配置目录

![img](README/docker.png)

**【HA中配置实例】**

```yaml
molohub:
  dismissable: true  # 默认状态下忽略按钮不可用,添加此行来激活忽略按钮.
```

**【多开教程】**

如果你需要绑定多个molohub, 与家人一起控制HA, 可以通过以下步骤实现molohub多开:

> 1. 进入到homeassistant配置目录的`custom_components`文件夹
> 2. 复制粘贴`molohub`文件取名为`molohub0`
> 3. 修改homeassistant配置目录下的`configuration.yaml`, 添加如下一行代码
>
>```yaml
>molohub0:
>```
>
> 4. 手动重启Home Assistant, 完成. 同理可以添加任意多个molohub.

**【相关链接】**

平台入口网站：<https://smarthomefans.jtsh.top>

molohub组件：<https://github.com/smarthomefans/molohub>

**【效果展现】**

![img](README/molo_info.png)
****
![img](README/molo_login.png)
****
![img](README/molo_info2.png)
****
![img](README/molo_wechat_suc.png)

**【联系我们】**

如果安装和使用过程中遇到任何问题，可以通过以下方式联系我们，我们将在看到反馈后第一时间作出回应:

Email: octopus201806@gmail.com

QQ群: 598514359

****
****

## **【Description in English】**

![img](README/xmolo-zx.png)

This is a component forwards the local HA control web page to the public network, so that the public network can be easily accessed, and interact with the hardwares at home that has connected to the HA. For security reasons, this component needs to be authorized by Google, GitHub or Wechat Mini Program to work properly.

when Home Assistant runs under the LAN, if you want to access the HA remotely through the WAN, the router under the network where the HA deployed must supports port mapping , and will be directly accessible on the public network after mapping. also generally ddns is also needed to solve ip change problem. But due to the network provider's The complexity of the network environment, and the complexity of the user's own internet environment, it is difficult to systematically summarize a set of general and effective methods to achieve the target. The above technology is more complicated to implement, and the threshold for ordinary users is higher. This project aims to simplify users to remotely access the local HA control network.

**【One-key install】**

If you are Linux-based user, run the command below to install molohub automatically:

```shell
curl --silent --show-error --retry 5 https://raw.githubusercontent.com/smarthomefans/molohub/master/auto_install.py | sudo python
```

Wait untill installation success, and restart your Home Assistant.

If this not working, please install molohub manually according to the next section. For Windows user with `curl` component, remove `sudo` in command and run it in `cmd`.

**【Installation】**

- [molohub component](https://github.com/smarthomefans/molohub)

Download `molohub` folder and put it under `homeassistant configuration directory/custom_components/`. If `custom_components` doesn't exist, create one.

- Where is homeassistant configuration directory?

**Windows user:** `%APPDATA%\.homeassistant`

**Linux-based user:** Run command line `locate .homeassistant/configuration.yaml`. The `.homeassistant` folder in the returning result is the configuration directory.

**Synology NAS Docker user:** Go to Docker - Images - Homeassistant - Advanced settings - Volumes, the path corresponding to `/config` is the configuration directory.

![img](README/docker.png)

**【Configuration】**

```yaml
molohub:
  dismissable: true  # Dismiss button is disable by default, add this line to enable.
```

**【Mulit-client】**

If you need to bind multiple molohubs to control HA with your family, you can open more molohub by following the steps below:

> 1. goto homeassistant configuration directory's `custom_components` folder
> 2. copy paste `molohub` folder named `molohub0`
> 3. modify homeassistant configuration file `configuration.yaml`, add a line as below:
>
>```yaml
>molohub0:
>```
>
> 4. manully restart Home Assistant, done. You can add as more as you want by using this method

**【Reference link】**

Platform entrance link：<https://smarthomefans.jtsh.top>

molohub component：<https://github.com/smarthomefans/molohub>

**【Demonstration】**

![img](README/molo_info.png)
****
![img](README/molo_login.png)
****
![img](README/molo_info2.png)
****
![img](README/molo_wechat_suc.png)

**【Contact us】**

Please contact us if you have any questions about installation and using molohub. We will respond as soon as we see the feedback.

Email: octopus201806@gmail.com

QQGroup: 598514359