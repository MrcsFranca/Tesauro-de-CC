# Tesauro de Ciência da Computação

Um repositório dedicado à construção e manutenção de um tesauro estruturado para a área de Ciência da Computação, com o objetivo de organizar, padronizar e relacionar os principais conceitos do campo.

## 📖 Índice

  [Sobre o Projeto](#-sobre-o-projeto)

  [Principais Recursos](#-principais-recursos)

  [Estrutura do Tesauro](#-estrutura-do-tesauro)

  [Como Usar](#-como-usar)

  [Tecnologias Utilizadas](#%EF%B8%8F-tecnologias-utilizadas)

  [Licença](#-licença)

---
## 💻 Sobre o Projeto

O Tesauro de Ciência da Computação foi criado para servir como uma fonte de referência terminológica para estudantes, pesquisadores, desenvolvedores e profissionais da área. Ele visa resolver a ambiguidade e a falta de padronização de termos, oferecendo uma estrutura hierárquica e relacional que facilita a busca, indexação e descoberta de informações.

Este projeto organiza conceitos desde os fundamentos teóricos até as tecnologias mais recentes, estabelecendo relações semânticas claras entre eles.

## ✨ Principais Recursos

Estrutura Hierárquica: Os termos são organizados em categorias e subcategorias, mostrando relações de "Termo Genérico" (TG) e "Termo Específico" (TE).

Relações Semânticas: Mapeamento de "Termos Relacionados" (TR) para conectar conceitos de diferentes ramos da computação.

Definições Claras: Cada conceito principal possui uma definição concisa e, sempre que possível, uma referência.

Formato Aberto: O tesauro é mantido em um formato legível por máquina (como SKOS/RDF, XML ou JSON), permitindo sua fácil integração com outras ferramentas e sistemas.

## 📂 Estrutura do Tesauro

O tesauro é construído sobre o padrão SKOS (Simple Knowledge Organization System), utilizando uma sintaxe RDF (como o XML/RDF). A estrutura principal se baseia em:

- Conceitos (skos:Concept): As unidades fundamentais do tesauro (ex: "Inteligência Artificial", "Algoritmo", "Rede Neural").

- Relações Hierárquicas:

	- skos:broader: Aponta para um conceito mais genérico (ex: "Algoritmo de Ordenação" -> skos:broader -> "Algoritmo").

	- skos:narrower: Aponta para um conceito mais específico.

- Relações Associativas:

	- skos:related: Conecta conceitos que são relacionados, mas não de forma hierárquica (ex: "Banco de Dados" -> skos:related -> "SQL").

## 🚀 Como Usar

Existem algumas maneiras de utilizar este tesauro:

Navegação Manual: Você pode clonar o repositório e explorar os arquivos de dados diretamente.

Software de Ontologias: Importe o arquivo principal (Tesauro de Ciência da Computação.rdf) em um editor de ontologias como o Protégé para visualizar e navegar na estrutura de forma gráfica.

Integração em Aplicações: Utilize bibliotecas de programação para manipular RDF (como rdflib para Python ou Apache Jena para Java) para carregar o tesauro e realizar consultas SPARQL em sua aplicação.

Para dar início a exploração do Tesauro de Ciência da computação, seguem algumas consultas que podem ajudar a nortear sua pesquisa

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX pav: <http://purl.org/pav/>

SELECT ?ontology ?version
WHERE {
  ?ontology rdf:type owl:Ontology .
  ?ontology pav:version ?version .
}
```
> A pesquisa acima mostrará em qual versão o Tesauro de Ciência da Computação se encontra

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX pav: <http://purl.org/pav/>

SELECT ?ontology (GROUP_CONCAT(?contributor; separator=", ") AS ?contributorList)
WHERE {
  ?ontology rdf:type owl:Ontology .
  ?ontology pav:contributedBy ?contributor .
}
GROUP BY ?ontology
```
> A pesquisa acima mostrará os contribuintes do Tesauro de Ciência da Computação

## 🛠️ Tecnologias Utilizadas

O desenvolvimento deste tesauro se baseia nas seguintes tecnologias e padrões:

- [SKOS](https://www.w3.org/2004/02/skos/)

- [RDF (Resource Description Framework)](https://www.w3.org/RDF/)

- [Protégé (para visualização e edição)](https://protege.stanford.edu/)


Você também pode abrir uma Issue para relatar um problema ou sugerir uma melhoria.

## 📜 Licença
Este projeto possui a licença do [MIT](https://choosealicense.com/licenses/mit/).

Última release do projeto: https://github.com/Load-Lased/Tesauro-de-CC/releases
