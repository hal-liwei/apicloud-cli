# apicloud-cli 工具使用说明

## 简介

[APICloud](http://www.apicloud.com/) 提供的一款适用于终端/命令行的 *APICloud* 平台开发工具,基于 [apicloud-tools-core 核心开发库](https://www.npmjs.com/package/apicloud-tools-core) 开发,包含新建页面模板,新建应用模板,WiFi同步等核心功能等核心库已有功能.

* 操作系统: Mac/Windows/Linux
* nodejs环境: node 4+
* 开源协议: GPL-3.0

## 安装

### 在线安装

```shell
npm install -g apicloud-cli
```

### 手动安装

考虑到cli工具的特殊性,下面给出完整的安装方法,需要先下载免安装包: [apicloud-cli](http://7y2xqk.com1.z0.glb.clouddn.com/apicloud/6ced29bbac804c3910064c3a38e844fe.zip)

#### windows 手动安装

解压后,把 *windows\node_modules* 中的文件复制到
*C:\Users\用户名\AppData\Roaming\npm\node_modules* 目录;
把 *windows\apicloud* 和 *windows\apicloud.cmd* 复制到
C:\Users\用户名\AppData\Roaming\npm 目录,
重启 命令行,输入 **apicloud help**,会出现命令提示;


#### Mac 手动安装:

在终端中,执行以下命令:

```shell
# 建立软连接, path/to/apicloud-cli/cli.js 表示 解压后apicloud-cli/cli.js 的绝对路径
# /usr/local/bin/apicloud 不要改,就要这么写
ln -s path/to/apicloud-cli/cli.js /usr/local/bin/apicloud

# 赋予可执行权限
chmod a+x /usr/local/bin/apicloud
```

然后重启终端/命令行,输入 **apicloud help** 即可查看命令各种提示

## apicloud-cli 指令集

```
***************** APICloud 通用命令行开发工具 ***********************

  命令格式: apicloud 方法名 --参数名1 参数值2 --参数名2 参数值2

  注意:
  1.参数中的workspace,project和file,可以是相对路径或绝对路径;
  2.支持的应用模板有: default,bottom,home,slide ;
  3.支持的页面模板有: page001,page002,page003,page004,page005,page006,page007,page008,page009,page010,page011,page012,page013,page014,page015,page016,page017,page018,page019,page020,page021,page022,page023,page024,page025,page026 ;
  4.port 为wifi服务启动时的端口号;

  命令示例

  显示版本号:
  apicloud version 或 apicloud -v 或 apicloud --version

  显示帮助信息:
  apicloud help

  启动 wifi 服务:
  apicloud wifiStart --port 8686

  停止 wifi 服务:
  apicloud wifiStop --port 8686

  wifi 增量更新:
  apicloud wifiSync --project ./ --updateAll false --port 8686

  wifi 全量更新:
  apicloud wifiSync --project ./ --updateAll true --port 8686

  wifi 预览:
  apicloud wifiPreview --file ./index.html --port 8686

  获取 wifi 信息:
  apicloud wifiInfo --port 8686

  获取 wifi 调试日志:
  apicloud wifiLog --port 8686

  创建应用模板:
  apicloud init --name HelloAPICloud --template home --workspace ./

  创建页面模板:
  apicloud initPage --name first_page --template page001 --project ./
```

## 注意

*apicloud wifiStart* 或 *apicloud wifiLog* 会持续输出操作日志或调试日志,此时无法继续进行输入,请在另一个终端/命令行窗口中继续进行操作;在真实的场景中,终端使用者,是可以通过特定指定使此指令后台执行,或重定向标准输出流.