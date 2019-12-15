---
layout: post
title: Iniciando com Git
author: Matheus Leal
date: '2019-12-15 14:35:23 +0530'
category: Git
summary: Aprenda o básico para começar a utilizar Git
thumbnail: git.png
---

<p>Olá a todos,</p>
<p>Para você que entrou de paraquedas nesse post e não tem ideia do que é Git.</p>
<p>Git é um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usando para registrar o histórico de edições de qualquer tipo de arquivo.</p>
<p>Irei dividir esse post em etapas, caso já saiba de alguma etapa pode ir passando para a próxima.</p>
<ol>
  <li>Instalação</li>
  <li>Configurações iniciais</li>
  <li>Iniciando um projeto</li>
  <li>Realizando primeiro commit</li>
</ol>

<h3>1 - Instalação</h3>
<p>O Git funciona em Mac OS X, Windows e Linux então não precisa se preocupar com a sua plataforma. Clique nesse link para baixar o Git para seu computador <a href="https://git-scm.com/downloads">https://git-scm.com/downloads</a> .</p>

<h3>2 - Configurações iniciais</h3>
<p>Se a instalação ocorreu como o esperado, se você abrir o seu terminal ou prompt de comando e digitar git irão aparecer algumas informações sobre os comandos do Git.</p>
<p>Próximo passo vai ser configurar seu nome e Email para reconhecimento dos commits (<del>ainda&nbsp;vamos&nbsp;falar&nbsp;o&nbsp;que&nbsp;são&nbsp;commits</del>) realizados posteriormente.</p>
<p>Primeiro vamos configurar seu nome, abre o terminal e digite esse comando a seguir:</p>
<p><em>git config --global user.name "seu nome"</em></p>
<p>Agora configurando seu email:</p>
<p><em>git config --global user.email "seuemail@email.com"</em></p>
<p>Esse comando "--global" indica que em qualquer projeto que utilize Git em seu computador ele ira utilizar esse dados para o commit, mas em caso de mudança desses valores para um único projeto é possível ir na pasta do projeto a partir do terminal e digitar esses comandos sem o "--global" e as configurações estão salvas somente para aquele projeto.</p>

<h3>3 - Iniciado um projeto</h3>
<p>Caso já tenha iniciado um projeto em seu computador, o primeiro passo é abrir o terminal, ir até o diretório do seu projeto e digitar <em>git&nbsp;init</em></p>
<p>Com isso o Git ira criar uma referencia do projeto no seu computador, após esse passo é necessário criar um repositório em alguma plataforma como o GitHub.</p>
<p>Após a criação do seu repositório online, ele ira receber um diretório e assim é possível sincronizar seu projeto local com o projeto online para isso é necessário usar o seguinte comando:</p>
<p> <em>git remote add origin https://github.com/user/repo.git</em> </p>
<p>Caso não exista um projeto ainda em seu computador, é possível iniciar o repositório no servidor (GitHub e etc) pegar link do repositório e abrir o terminal até o local onde deseja iniciar o projeto e digitar:</p>
<p><em>git&nbsp;clone</em> <em>https://github.com/user/repo.git</em></p>

<h3>4 - Realizando primeiro commit</h3>
<p>No contexto de ciência da computação e gerenciamento de dados, commit refere-se à ideia de fazer permanentes um conjunto de mudanças experimentais. Uma utilização popular está no fim de uma transação.  - Wikipedia</p>
<p>Após realizar suas alterações no código, abra seu terminal na pasta de seu projeto e digite:</p>
<p><em>git&nbsp;add&nbsp;.&nbsp;&nbsp;(Adiciona&nbsp;todos&nbsp;os&nbsp;arquivos&nbsp;na&nbsp;pasta)</em></p>
<p><em>git commit -m "Mensagem das alterações realizadas"</em></p>
<p><em>git push origin master</em></p>
<p>E pronto, seu primeiro commit foi realizado! </p>
<p>Se você for a página de seu repositório online poderá observar os arquivos que realizou upload :)</p>