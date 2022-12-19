<div align="center">
  <img width="125px" src="Assets/Havoc.png" />
  <h1>Havoc</h1>
  <br/>

  <p><i>Havoc is a modern and malleable post-exploitation command and control framework, created by <a href="https://twitter.com/C5pider">@C5pider</a>.</i></p>
  <br />

  <img src="Assets/Screenshots/SessionGraphSmbEkko.png" width="90%" /><br /><br />
  <img src="Assets/Screenshots/MultiUserAgentControl.png" width="90%" /><br />
  
</div>

> :warning: Havoc is in an early state of release. Breaking changes may be made to APIs/core structures as the framework matures.

# Go1.18
```
curl -LO https://go.dev/dl/go1.18.9.linux-amd64.tar.gz
tar -C /usr/local -xzf go1.18.9.linux-amd64.tar.gz
rm go1.18.9.linux-amd64.tar.gz
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
source ~/.bashrc
```
# 先决条件
```
sudo apt install -y git build-essential apt-utils cmake libfontconfig1 libglu1-mesa-dev libgtest-dev libspdlog-dev libboost-all-dev libncurses5-dev libgdbm-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev libbz2-dev mesa-common-dev qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools libqt5websockets5 libqt5websockets5-dev qtdeclarative5-dev qtbase5-dev libqt5websockets5-dev libspdlog-dev python3-dev libboost-all-dev mingw-w64 nasm
```
# 乌班图 20.04 / 22.04
```
sudo apt install build-essential
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.10 python3.10-dev
```
# 下载浩劫是一个现代且可塑的利用后命令和控制框架
```
git clone https://github.com/HavocFramework/Havoc.git
```
# 构建客户端
```
cd Havoc/Client
make 
```
# 构建团队服务器
```
cd Havoc/Teamserver
go mod download golang.org/x/sys  
go mod download github.com/ugorji/go
wget https://musl.cc/x86_64-w64-mingw32-cross.tgz -O /tmp/mingw-musl.tgz 
tar zxvf /tmp/mingw-musl.tgz -C data
make
```
# 运行团队服务器
```
sudo ./teamserver server --profile ./profiles/havoc.yaotl -v --debug
```
# 运行客户端
```
Havoc/Client/Havoc
```

### Quick Start

> Please see the [Wiki](https://github.com/HavocFramework/Havoc/wiki) for complete documentation.

Havoc works well on Debian 10/11, Ubuntu 20.04/22.04 and Kali Linux. It's recommended to use the latest versions possible to avoid issues. You'll need a modern version of Qt and Python 3.10.x to avoid build issues.

See the [Installation](https://github.com/HavocFramework/Havoc/wiki#installation) guide in the Wiki for instructions. If you run into issues, check the [Known Issues](https://github.com/HavocFramework/Havoc/wiki#known-issues) page as well as the open/closed [Issues](https://github.com/HavocFramework/Havoc/issues) list.

---

### Features

#### Client

> Cross-platform UI written in C++ and Qt

- Modern, dark theme based on [Dracula](https://draculatheme.com/)


#### Teamserver

> Written in Golang

- Multiplayer
- Payload generation (exe/shellcode/dll)
- HTTP/HTTPS listeners
- Customizable C2 profiles 
- External C2

#### Demon

> Havoc's flagship agent written in C and ASM

- Sleep Obfuscation via [Ekko](https://github.com/Cracked5pider/Ekko) or [FOLIAGE](https://github.com/SecIdiot/FOLIAGE)
- x64 return address spoofing
- Indirect Syscalls for Nt* APIs
- SMB support
- Token vault
- Variety of built-in post-exploitation commands

<div align="center">
  <img src="Assets/Screenshots/SessionConsoleHelp.png" width="90%" /><br />
</div>

#### Extensibility

- [External C2](https://github.com/HavocFramework/Havoc/wiki#external-c2)
- Custom Agent Support
  - [Talon](https://github.com/HavocFramework/Talon)
- [Python API](https://github.com/HavocFramework/havoc-py)
- [Modules](https://github.com/HavocFramework/Modules)

---

### Support

Consider supporting C5pider on [Patreon](https://www.patreon.com/5pider)/[Github Sponsors](https://github.com/sponsors/Cracked5pider). Additional features are planned for supporters in the future, such as custom agents/plugins/commands/etc.

### Community

You can join the official [Havoc Discord](https://discord.gg/z3PF3NRDE5) to chat with the community! 

### Contributing

To contribute to the Havoc Framework, please review the guidelines in [Contributing.md](https://github.com/HavocFramework/Havoc/blob/main/CONTRIBUTING.MD) and then open a pull-request! 
