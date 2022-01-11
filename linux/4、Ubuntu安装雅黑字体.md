# 4、Ubuntu安装雅黑字体

## 1、 windows系统字体

> `C:\Windows\Fonts`找到`微软雅黑字体`，复制出来会有三个字体文件：`msyhbd.ttc`，`msyhl.ttc`，`msyh.ttc`

## 2、Ubuntu安装

```shell
> sudo mkdir /usr/share/fonts
> cd /usr/share/fonts
> sudo mkdir winfonts
```

上传三个ttc字体问题到文件夹`/usr/share/fonts/winfonts`

```shell
> cd /usr/share/fonts/winfonts
> sudo chmod 755 *
> sudo apt install xfonts-utils
> sudo apt install fontconfig
> sudo mkfontscale
> sudo mkfontdir
> sudo fc-cache -fv
```



> ps: `sudo chmod 755 *`是指root以外的用户也可读可执行
>
> 三个数字分别代表：FileOwner权限， Group权限，Others权限
>
> 7:  二进制`111`（可读/可写/可执行）
>
> 5: 二进制`101`（可读/不可写/可执行）