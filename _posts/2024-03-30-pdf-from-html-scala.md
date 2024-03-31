---
layout: post
title: Gerando PDF a partir de HTML com Scala
author: Matheus Leal
date: '2024-03-30 09:02:00 +3'
category: Scala
summary: Gerando PDF a partir de HTML com Scala
thumbnail: scala.png
---

Olá,

Escrevo esse artigo com o intuito de trazer um breve tutorial sobre como gerar um PDF com Scala a partir de arquivo HTML. Pretendo trazer no futuro mais posts sobre o uso de Scala.

Antes de iniciar o tutorial, gostaria de trazer um breve contexto sobre a linguagem Scala, uma vez que não é uma linguagem tão conhecida.

Texto retirado do site [Scala Lang](https://www.scala-lang.org/): Scala é uma linguagem de programação multiparadigma moderna projetada para expressar padrões de programação comuns de maneira concisa, elegante e com segurança de digitação. Ele integra perfeitamente recursos de linguagens funcionais e orientadas a objetos.

Configurações de ambiente:
- Scala v2.13
- JVM v17-tem
- sbt v1.9.4

Primeira etapa é adicionar as seguintes libs ao seu build.sbt:
* "com.openhtmltopdf" % "openhtmltopdf-pdfbox" % "1.0.10"
* "com.openhtmltopdf" % "openhtmltopdf-core" % "1.0.10"


Vamos iniciar a definição do nosso método de conversão de HTML para PDF:
```
private def convert(html: String, outputFile: String) = {
	val os = new FileOutputStream(new File(outputFile))

	try {
		val builder = new PdfRendererBuilder()
		builder
			.withHtmlContent(html, null)
			.toStream(os)
			.run()
		println(s"HTML converted to PDF. Output file: $outputFile")
	} finally {
		os.close()
	}
} 
```

Gerando o PDF:
```
override def run() = {
	val html = "<html><body><h1>Hello, world!</h1><p>This is a test HTML document.</p></body></html>"
	val outputFile = "output.pdf"
	convert(html, outputFile)
} 
```

Podemos também criar um método responsável por manipular os dados dentro desse HTML:
```
private def getUser(userId: String) = ???

private def addData(html: String, userId: String) = {
	val user = getUser(userId)

	html.replaceAll(“@name”, user.name)
}

override def run() = {
	val html = "<html><body><h1>Hello, @name!</h1><p>This is a test HTML document.</p></body></html>"
	val outputFile = "output.pdf"
	val userId = “123"
	val htmlUpdated = addData(html, userId)

	convert(htmlUpdated, outputFile)
} 
```

Você ainda pode criar outras adaptações para o seu código e gerar o que for necessário.

E com esses passos iniciais você já tem o seu gerador de PDF a partir de HTML com Scala.

Até o próximo post!

