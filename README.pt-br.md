# ServiceNow Query Generator

[![Português](https://img.shields.io/badge/en-READ_IN_ENGLISH-brightgreen)](./README.pt-br.md)


O **ServiceNow Query Generator** é um widget HTML estático, leve e sem dependências, projetado para ser incorporado via Iframe (por exemplo, no SharePoint ou portais internos).

Ele permite que usuários insiram um termo de busca único (como uma Tag de Ativo ou Nome de IC) e gera um link de consulta complexo e multi-variável, realizando uma busca do tipo "dot-walk" (referência cruzada) em vários campos de variáveis dentro do ServiceNow.

### 🔐 Segurança e Privacidade no Design

Este projeto foi desenhado para ser hospedado publicamente no GitHub sem vazar informações corporativas sensíveis.

* **Código Agnóstico:** O arquivo HTML/JS não contém nenhum hostname, nome de instância ou IDs de variáveis internos "hardcoded" (fixos no código).
* **Configuração via URL:** Toda a configuração acontece através de parâmetros passados para a URL do Iframe no momento da execução.

## ✨ Principais Funcionalidades

* **🌐 Internacionalização (i18n):** Suporte nativo para Inglês (padrão) e Português (pt-BR), alternável via parâmetro de URL.
* **🚀 Zero Dependências:** Um único arquivo HTML que roda em qualquer lugar. Sem passos de build, sem Node.js.
* **🎨 UI Totalmente Personalizável:** Altere títulos, rótulos, textos de botões, dicas e placeholders via URL.
* **🖼️ Logos Embutidas:** Suporte para imagens codificadas em Base64 na URL, permitindo branding personalizado sem necessidade de hospedagem de imagens externa.
* **🔗 Ação Dupla:** Usuários podem abrir a consulta diretamente em nova aba ou copiar o link gerado para a área de transferência.

## 🛠️ Guia de Uso

### 1. Deploy
Hospede o arquivo `index.html` em qualquer servidor web estático (GitHub Pages, Netlify, servidor interno).

### 2. Configurar a URL
Construa a URL que será usada no atributo `src` do seu Iframe adicionando os parâmetros necessários.

#### Parâmetros Obrigatórios

| Parâmetro | Descrição | Exemplo |
| :--- | :--- | :--- |
| `host` | A URL base da sua instância ServiceNow. | `https://instancia.service-now.com` |
| `ids` | Lista separada por vírgulas dos `sys_ids` das variáveis a serem pesquisadas. | `e85466...cc,fc8850...cb` |

#### Parâmetros de Personalização (Opcionais)

| Parâmetro | Descrição | Padrão (EN) |
| :--- | :--- | :--- |
| `lang` | Seleção de idioma (`en` ou `pt-BR`). | `en` |
| `title` | Título principal do cabeçalho. | "Search Tool" |
| `subtitle`| Subtítulo do cabeçalho. | "Corporate Search" |
| `label` | Rótulo do campo de entrada. | "Search Query" |
| `hint` | Texto de ajuda abaixo do input. | "Enter the text to search" |
| `logo` | URL ou string Base64 para o ícone do cabeçalho. | (Ícone de Lupa Genérico) |
| `btnOpen` | Rótulo do botão de abrir. | "Search" |
| `btnCopy` | Rótulo do botão de copiar. | "Copy" |

---

### 💡 Exemplos de Configuração

#### Exemplo 1: Configuração Básica (Inglês)

```text
https://your-username.github.io/servicenow-query-generator/index.html?host=https://dev12345.service-now.com&ids=id1,id2,id3&lang=pt-BR&subtitle=Ferramenta%20SNOW
```

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
