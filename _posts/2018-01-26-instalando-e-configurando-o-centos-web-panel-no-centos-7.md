---
layout: post
title: "Instalando e Configurando o CentOS Web Panel no CentOS 7"
description: "Aprenda a fazer o básico no CWP"
date: 2018-01-26
tags: [centos,cwp]
comments: true
share: true
---

É muito comum dificuldades encontradas para instalação do CWP, no entanto, venho desmistificar de forma básica. Usuaremos o CentoOS 7 neste tutorial.

---

## 1. Instalando
Para iniciar a instalação certifique que o seu sistema esteja atualizado, para isso rode o comando:
```
yum update -y
```
Pois bem, antes de prosseguir certifique-se que tenha configurado o hostname corretamente, logo após, rode os comandos:
```
cd /usr/local/src
wget http://centos-webpanel.com/cwp-el7-latest
sh cwp-el7-latest
```
Agora é só aguardar a conclusão, sendo que no final da instalação será exibido algumas informações, como: endereço de acesso e senha root do MySQL.

## 2. Configurando
Pois bem, instalação concluída, agora acesse o administrativo do CWP:
```
http://<ip ou hostname>:2030
SSL: https://<ip ou hostname>:2031
```
### Instalando o PHP e PHP-FPM
Vá no menu de navegações e busque por *PHP Settings > PHP-FPM Selector*, e selecione as versões mais recentes para cada PHP, conforme a imagem abaixo, e clique no botão *Star Compiler* e aguarde a conclusão.

![Imgur](https://i.imgur.com/aK4NbsN.png){: .center-image}

Você pode acompanhar em tempo real até a conclusão, através do comando no terminal:
```
tail -f /var/log/php-selector-rebuild.log
```

