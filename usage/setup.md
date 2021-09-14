---
description: How to initially setup the beta Debian repository
---

# Setup

## Warning

{% hint style="danger" %}
**Please, read** [**Before you start**](before-you-start.md) **and** [**Hardware requirements**](hardware.md#hardware-requirements) **to make sure you are ready to setup this cryptoanarchy tooling.** 
{% endhint %}

## How to setup the beta Debian repository

To install software from this repository, you need to add it to your system. You need to also setup Microsoft dotnet repository in order for some software \(BTCPayserver & co\) to work. 

First, download keys for verifying software directly to your `gpg` and add it to your apt keyring. Don't forget to [verify fingerprints](https://gist.github.com/Kixunil/fb7300edcb8a8afc95e6b7b727b31f0d). Enter commands one by one: 

```text
gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys 3D9E81D3CA76CDCBE768C4B4DC6B4F8E60B8CF4C
gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys BC528686B50D79E339D3721CEB3E94ADBE1229CF
gpg --export 3D9E81D3CA76CDCBE768C4B4DC6B4F8E60B8CF4C | sudo apt-key add -
gpg --export BC528686B50D79E339D3721CEB3E94ADBE1229CF | sudo apt-key add -
```

Now you can add links and information about repository to list of sources. If you're setting up a [dedicated hardware](https://github.com/debian-cryptoanarchy/cryptoanarchy-deb-repo-builder/blob/master/docs/dedicated-hardware.md) without desktop environment, you may want to leave out `desktop` component in line 2. 

```text
echo 'deb [arch=amd64,arm64,armhf] https://packages.microsoft.com/debian/10/prod buster main' | sudo tee /etc/apt/sources.list.d/microsoft.list > /dev/null
echo 'deb [signed-by=3D9E81D3CA76CDCBE768C4B4DC6B4F8E60B8CF4C] https://deb.ln-ask.me/beta buster common local desktop' | sudo tee /etc/apt/sources.list.d/cryptoanarchy.list > /dev/null
sudo apt update
```

You are ready to synchronize packages from added repositories using `sudo apt update` 

{% hint style="success" %}
You can now install the desired applications using `apt`. Check Installing applications in Supported software.
{% endhint %}

