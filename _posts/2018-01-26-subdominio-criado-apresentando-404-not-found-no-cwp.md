---
layout: post
title: "Subdomínio criado apresentando 404 not found no CWP"
description: "Corriga o erro 404 que é tido quando se cria/adiciona um novo subdomínio/domínio em uma conta no CentOS Web Panel."
date: 2018-01-26
tags: [404,cwp,centos,subdomínio,domínio]
comments: true
share: true
---

É um erro que vem sendo comum no CentOS Web Panel, pórem bastante simples de resolver, por algum motivo ao adicionar um novo domínio ou subdomínio o vhost do apache dá uma bugada bem esquisita e acaba retornando uma página de erro 404, outro casos nem é exibido a página e o navegador retorna com erro de DNS.

---
## Resolvendo o problema
Para resolver é bem simples, basta acessar o administrativo do CWP e ir em *Webserver Settings > Webserver Main Conf* e selecionar o checkbox *Rebuild all vhosts on save*, logo clique em *Save Changes*, agora aguarde a página retornar e tente acessar novamente o domínio ou subdomínio problemático.

É uma solucão bastante simples, pórem é um problema bastante chato e que atrapalhar bastante.
