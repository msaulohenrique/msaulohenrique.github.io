---
layout: post
title: "Instalando e Configurando o CentOS Web Panel no CentOS 7"
description: "Aprenda a fazer uma instalação básica do CWP deixando pronta para seu uso."
date: 2019-01-26
tags: [centos,cwp]
comments: true
share: true
---

É muito comum dificuldades encontradas para instalação do CWP, no entanto, venho desmistificar de forma básica. Usaremos o CentOS 7 neste tutorial.

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
Vá no menu de navegações e busque por *PHP Settings > PHP-FPM Selector*, e selecione as versões mais recentes para cada PHP, conforme a imagem abaixo, e clique no botão *Start Compiler* e aguarde a conclusão.

![Imgur](https://i.imgur.com/aK4NbsN.png){: .center-image}

Você pode acompanhar em tempo real até a conclusão, através do comando no terminal:
```
tail -f /var/log/php-selector-rebuild.log
```
### Instalando o WebServers
Vá no menu de navegações e busque por *WebServers Settings > Select WebServers*, e selecione a opção em que desejar, no meu caso estarei configurando conforme a imagem abaixo, pois quero o servidor otimizado para WordPress, o qual consome bastante recursos.

![Imgur](https://i.imgur.com/zJoVVls.png){: .center-image}

Clique no botão *Save & Rebuild Configuration* e aguarde a conclusão.

### Configurando o ConfigServer Security & Firewall (csf)
Vá no menu de navegações e busque por *Security > CSF Firewall*, clique no botão *Firewall Configuration* procure pela linha:
```
TESTING = "0"
```
Por padrão o CWP está vindo com o valor 0, mas lembre-se que se estiver 1, quer dizer que o modo de teste está ativo, por isso, sempre o mantenha com o valor 0.
Por questão de recomendação do próprio firewall vamos altera a linha:
```
RESTRICT_SYSLOG = "0"
```
Para:
```
RESTRICT_SYSLOG = "3"
```
Clique em *Save changes*.

Vá em *Security > Firewall Manager* e clique na opção *Enable Firewall*.

### Configurando o CWP
Vá em *CWP Settings > Edit Settings* e defina um email nas opções *Admin Email* e *CSF/LFD Alerts* e clique no botão *Save Changes*.

Vá em *CWP Settings > Yum Manager* e veja se há alguma atualização para ser realizada, se sim, realize. Se seu CWP não for o PRO, você só consegue realizar a atualização por terminal, usando o comando:
```
yum update -y
```
Para configurar o SSL vá em *Security > SSL Generator*.

### Configurando o DNS
Neste tutorial a máquina em que estou usando tem dois IPs, os quais vou configura-los como NS1 e NS2.
Vá em *DNS Functions > Edit Nameservers IPs* e realize a modificação, e salve. 
Lembre-se que é preciso que o domínio esteja configurado.

## 3. Finalizando
Concluimos nossa instalação e configuração, agora você pode configurar os pacotes de cada plano (*Package > Add Package*) e criar as contas (*User Accounts > New Accounts*).

Vale ressaltar que aqui realizamos configurações básicas, podendo variar conforme seu uso.

Fiquem a vontade para realizar perguntar abaixo, ajudarei conforme puder.
