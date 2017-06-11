# CumulusLinux 勉強用Repositocy
https://github.com/kfukafuka/learning-bgp で作ってた内容をCumulusを分けたくなってきたので分離。<br/>
BGPに関するまとめは https://gist.github.com/kfukafuka/3c6979d49c81e27664a7b1875b56e8c5 に記載。

# CumulusVX
## Requirements
* Cumulus VX requires Vagrant 1.7 - 1.9.1
* 2017/03/08時点の最新は1.9.2
* Understand these VirtualBox considerations

## Install Vagrant
* https://releases.hashicorp.com/vagrant/1.8.7/ から [vagrant_1.8.7.dmg] (https://releases.hashicorp.com/vagrant/1.8.7/vagrant_1.8.7.dmg)をダウンロード
* 1.9.x だとうまくいかなかったりしたので、過去に使用していたバージョンを使用
```bash
$ vagrant --version
Vagrant 1.8.7
```

## Download VX
VAGRANTBOXを選択 (Downloadにはアカウント登録が必要)
![Cumulus VX 3.2.1](https://github.com/kfukai/Images/blob/master/SCREENSHOT-2017-0309-0236.png)
2017/06/10 時点で最新は ３．３．１

### Add box
```bash                                    
$ vagrant box add cumulus-linux-3.2.1 ~/Downloads/cumulus-linux-3.2.1-vx-amd64-1486153138.ac46c24zd00d13e.box
==> box: Box file was not detected as metadata. Adding it directly...
==> box: Adding box 'cumulus-linux-3.2.1' (v0) for provider:
    box: Unpacking necessary files from: file:///Users/kfukai/Downloads/cumulus-linux-3.2.1-vx-amd64-1486153138.ac46c24zd00d13e.box
==> box: Successfully added box 'cumulus-linux-3.2.1' (v0) for 'virtualbox'!
$ vagrant box list
cumulus-linux-3.2.1 (virtualbox, 0)
```
:exclamation:うまくいかないときに
```bash
$ sudo mv /opt/vagrant/embedded/bin/curl /opt/vagrant/embedded/bin/curl.bk
```

# Vagrant Command
## VM 起動
```bash
$ vagrant up
```

## VM 終了
```bash
$ vagrant halt 
```
## VM Provision
* 構成の変更したときなどに実行
```bash
$ vagrant provision  
```

# 参考URL
* https://docs.cumulusnetworks.com/display/VX/Using+Cumulus+VX+with+Vagrant
* https://github.com/CumulusNetworks/cumulus-vx-vagrant/tree/master/vagrant/demos/clos-bgp
* https://support.cumulusnetworks.com/hc/en-us/articles/205384457-Cumulus-Linux-Command-Reference-Guide

