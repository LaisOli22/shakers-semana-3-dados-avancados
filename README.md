# shakers-semana-3-dados-avancados

## Desafio - Semana 3

A proposta consiste em criar uma Section de Slider onde um produto possua um Metafield contendo uma lista de Metaobjetos.  Cada Metaobjeto associa um produto a um banner (imagem).

O foco do desafio é:

- Metafields
- Metaobjetos
- Consumo via Liquid
- Slider dinâmico
- Estrutura organizada de assets

---

# Conceitos Utilizados

##  Metafields

Metafields permitem adicionar dados personalizados a recursos da Shopify (como produtos, coleções, páginas etc).

Neste projeto, foi criado um Metafield de Produto que referencia uma lista de Metaobjetos.

---

##  Metaobjetos

Metaobjetos são estruturas reutilizáveis de dados personalizadas.

Foi criado um Metaobjeto chamado:

product_with_banner

Com os seguintes campos obrigatórios:

- Campo do tipo **Product**
- Campo do tipo **File (imagem)**

Esse modelo permite vincular dinamicamente produtos a banners.

---

# O que foi implementado

## 1. Metaobjeto

Criado via:

Admin → Content → Metaobjects

Nome: product_with_banner

Campos:

- product (tipo Product)
- file (tipo File)

Foram cadastradas pelo menos 2 entradas desse Metaobjeto.

---

## 2. Metafield de Produto

Criado em:

Settings → Custom Data → Products

Nome: related_products_with_banner

Configuração:

- Tipo: Metaobject
- Lista de entradas
- Referência ao Metaobjeto `product_with_banner`

Esse Metafield foi associado manualmente a um produto específico no Admin.

## 3. Section do Slider

Arquivo:

sections/metaobject-slider.liquid

### Assets separados corretamente:

- Arquivo dedicado em `assets/metaobject-slider.css`

- Arquivo dedicado em `assets/metaobject-slider.js`
- O JavaScript é carregado separadamente e inicializa o slider apenas após carregamento do DOM.
---

## Como rodar localmente

### Instalar Shopify CLI

```bash
npm install -g @shopify/cli @shopify/theme
```

### Login na loja

```bash
shopify login
```

### Rodar ambiente de desenvolvimento

```bash
shopify theme dev
```

---

## Como configurar no Admin

Criar Metaobjeto product_with_banner

Criar entradas (mínimo 2)

Criar Metafield related_products_with_banner

Associar entradas ao produto

Selecionar produto na Section via Editor de Tema

### Link do Pull request
https://github.com/LaisOli22/shakers-semana-3-dados-avancados/pull/1

### Link do Vídeo

https://drive.google.com/file/d/1S3ZAaSi2VOR-TwW_18GqYf86nM4DfeRP/view?usp=sharing
