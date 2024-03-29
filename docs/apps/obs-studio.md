---
title: OBS Studio
appstreamRepo: com.obsproject.Studio
appstreamFlatpak: com.obsproject.Studio
---

# OBS Studio

OBS Studio — Бесплатная программа с открытым исходным кодом для записи видео и потокового вещания.

## Установка из репозитория 

**OBS Studio** можно установить любым привычным и удобным способом:

<!--@include: ./parts/install/software-repo.md-->

**Установка через терминал**

::: code-group

```shell[apt-get]
su -
apt-get update
apt-get install obs-studio
```
```shell[epm]
epm -i obs-studio
```
:::

## Установка c помощью Flatpak

При наличии пакета [Flatpak](/flatpak), можно установить **OBS Studio** одной командой:

```shell
flatpak install flathub com.obsproject.Studio
```

<!--@include: ./parts/install/software-flatpak.md-->
