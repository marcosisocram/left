---
layout: post
title: Corrigindo o erro do libudev.so.0 com o Chrome no ubuntu 13.04
description: Com falta do libudev.so.0 no ubuntu 13.04 o Chrome falha na instalação e inicialização.
type: article
post: true
locale: pt_BR
---
Para corrigir o erro tem duas formas, Use uma das duas abaixo.


### Copiando o libudev.so.
Usando o locate achei o libudev.so.1.2.2 na pasta/lib/i386-linux-gnu/

> `locate libudev.so.`

depois de achar é só criar um link do libudev.so.1.2.2 para /lib/i386-linux-gnu/libudev.so.0

> `ln -s /lib/i386-linux-gnu/libudev.so.1.2.2 /lib/i386-linux-gnu/libudev.so.0`

agora o Chrome abre normalmente.

### Baixando o libudev.so.0

__32 bits__

> `wget https://launchpad.net/ubuntu/+source/udev/175-0ubuntu19/+build/4325790/+files/libudev0_175-0ubuntu19_i386.deb`

>`sudo dpkg -i libudev0_175*`

__64 bits__

>`wget https://launchpad.net/ubuntu/+source/udev/175-0ubuntu19/+build/4325788/+files/libudev0_175-0ubuntu19_amd64.deb`

>`sudo dpkg -i libudev0_175*`

e agora o Chrome também abre normalmente.
