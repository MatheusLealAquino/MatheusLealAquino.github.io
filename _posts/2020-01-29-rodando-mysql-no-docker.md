---
layout: post
title: Rodando um banco de dados MySQL no Docker
author: Matheus Leal
date: '2020-01-29 22:02:00 +0530'
category: Docker
summary: Aprenda a inicializar um container docker com a imagem do MySQL
thumbnail: docker.png
---

<p>Olá a todos, hoje vamos ver sobre o que é o Docker e como rodar um banco de dados MySQL em um container. <br> <i>Este post é indicado para quem não possui experiência com Docker e deseja dar o seu primeiro passo.</i></p>
<ul>
  <li>O que é Docker?</li>
  <li>O que é um container?</li>
  <li>Rodando o MySQL em um container Docker</li>
</ul>

<h2>O que é Docker?</h2>
<p>Docker é uma ferramenta para facilitar a criação, implantação e pode rodar em aplicações na nuvem ou localmente.</p>
<p>Com o Docker existe a capacidade de se utilizar containers que funcionam como máquinas virtuais. E com um container é possível ganhar maior flexibilidade para a migração de um ambiente para outro.</p>

<h2>O que é um container?</h2>
<p>Um container é uma unidade de software que engloba  código e todas as suas dependências então a aplicação roda rapidamente e a transferência de um computador para outro é feita de forma confiável.</p>
<p>Ficou díficil de entender? Bem, imagine o container como uma máquina virtual bem mais simplificada e que só possui o necessário para a execução da sua aplicação. Caso ainda não tenha entendido siga até o fim, que botar a mão na massa pode te ajudar, ok?</p>

<h2>Rodando o MySQL em um container Docker</h2>
<p>Agora vamos botar a mão na massa e ver que o básico do Docker não tem mistério.</p>
<h5>Requisitos:</h5>
<ul>
  <li>Acesso a internet</li>
  <li>Ter o Docker instalado em seu computador (<a href="https://www.docker.com/products/docker-desktop" target="_blank">Site com informações para download</a>)</li>
  <li>Vontade de aprender :)</li>
</ul>

<p>O primeiro passo é baixar a imagem que você quer utilizar em seu container, no nosso caso vamos baixar a imagem do MySQL (<a href="https://hub.docker.com/_/mysql" target="_blank">https://hub.docker.com/_/mysql</a>).</p>
<p>Para isso, após a instalação do Docker e sua inicialização, vamos abrir o terminal e digitar o seguinte comando: <br> <b>"docker pull mysql:latest"</b><br> Após executar este comando, sera iniciado o download da ultima versão da imagem disponibilizada pela equipe do MySQL.</p>

<p>Com a imagem salva podemos criar um container a partir desta imagem e começar a usar o MySQL sem que seja necessário realizar uma instalação de um cliente em sua máquina. Para criar o container executamos o seguinte comando: <br> 
<b>"docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_USER=root --name meu_container mysql:latest"</b><br> Vamos análisar o que este comando faz:</p>

<ul>
  <li>run: Responsável por inicializar o container.</li>
  <li>-d: Habilitar o modo independente, fazer o container rodar em backgroud.</li>
  <li>-p: Indicar as portas da aplicação (portaExposta):(portaInterna). Ao colocar 3306:3306 estamos expondo para acesso em nossa máquina     na porta 3306, sendo possível acessar nosso banco de dados de qualquer aplicativo de gerenciamento de banco de dados.</li>
  <li>MYSQL_ROOT_PASSWORD: Senha para acesso ao MySQL.</li>
  <li>MYSQL_USER: Usuário para acesso ao MySQL.</li>
  <li>--name: Váriavel para criar nome do container.</li>
  <li>mysql:latest : A imagem que será utilizada como base para a criação do container.</li>
</ul>

<p>Após este comando, podemos executar o comando <b>"docker ps"</b> e será possível ver que existe um container rodando na porta 3306 xD.</p>
<p>Após a sequência destes pequenos passos já temos o MySQL rodando em nossa máquina sem a necessidade de realizar instalações de executáveis ~Tirando o Docker (No Windows e MAC)~.</p>
<p>É isso pessoal, qualquer dúvida podem me mandar e-mail ou me mandar uma mensagem em alguma das minhas redes sociais. <br>
Até o próximo post!</p>