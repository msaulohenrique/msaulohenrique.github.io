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
```yum update -y```
Pois bem, antes de prosseguir certifique-se que tenha configurado o hostname corretamente, logo após, rode os comandos:
```cd /usr/local/src
wget http://centos-webpanel.com/cwp-el7-latest
sh cwp-el7-latest
```
Agora é só aguardar a conclusão, sendo que no final da instalação será exibido algumas informações, como: endereço de acesso e senha root do MySQL.

## 2. Configurando
Pois bem, instalação concluída, agora acesse o administrativo do CWP:
```http://<ip ou hostname>:2030
SSL: https://<ip ou hostname>:2031
```
### Instalando o PHP e PHP-FPM
Vá no menu de navegações e busque por *PHP Settings > PHP-FPM Selector*, e selecione as versões mais recentes para cada PHP, conforme a imagem abaixo, e clique no botão *Star Compiler* e aguarde a conclusão.
[Imgur](https://i.imgur.com/aK4NbsN.png)
Você pode acompanhar em tempo real até a conclusão, através do comando no terminal:
```tail -f /var/log/php-selector-rebuild.log```

## 3. Images

![Large example image](http://placehold.it/800x400 "Large example image")
![Medium example image](http://placehold.it/400x200 "Medium example image")
![Small example image](http://placehold.it/200x200 "Small example image")

### 3-1. Image Alignment
![Center example image](http://placehold.it/200x200 "Center"){: .center-image}

## 4. Blockquotes

> Lorem ipsum dolor sit amet, test link adipiscing elit. Nullam dignissim convallis est. Quisque aliquam.

## 5. List Types

### Unordered List

* Lorem ipsum dolor sit amet, consectetur adipiscing elit.
* Nam ultrices nunc in nisi pellentesque ultricies. Cras scelerisque ipsum in ante laoreet viverra. Pellentesque eget quam et augue molestie tincidunt ac ut ex. Sed quis velit vulputate, rutrum nisl sit amet, molestie neque. Vivamus sed augue at turpis suscipit fringilla.
* Integer pretium nisl vitae justo aliquam, at varius nisi blandit.
  1. Nunc vehicula nulla ac odio gravida vestibulum sed nec mauris.
  2. Duis at diam eget arcu dapibus consequat.
* Etiam vel elit in purus iaculis pretium.

### Ordered List

1. Quisque ullamcorper leo non ex pretium, in fermentum libero imperdiet.
2. Donec eu nulla euismod, rhoncus ipsum nec, faucibus elit.
3. Nam blandit purus gravida, accumsan sem in, lacinia orci.
  * Duis congue dui nec nisi posuere, at luctus velit semper.
  * Suspendisse in lorem id lacus elementum pretium nec vel nibh.
4. Aliquam eget ipsum laoreet, maximus risus vitae, iaculis leo.

### Definition Lists

kramdown
: A Markdown-superset converter

Maruku
: Another Markdown-superset converter

## 6. Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3


## 7. Code Snippets

### Highlighted Code Blocks

```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

### Standard code block

    <div id="awesome">
      <p>This is great isn't it?</p>
    </div>
