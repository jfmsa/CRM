# Baviera Control

App mobile-first para gestão de registos de viaturas BMW, com base de dados Supabase.

## Pré-requisitos

1. Um projeto **Supabase** com a tabela `baviera_control` criada (SQL fornecido em separado)
2. Um utilizador criado em **Supabase → Authentication → Users**
3. Uma conta **GitHub**

---

## Deploy via GitHub Pages (passo a passo)

### 1. Criar repositório no GitHub

1. Vai a [github.com/new](https://github.com/new)
2. Nome: `baviera-control` (ou outro à escolha)
3. Visibilidade: **Private** (recomendado — o código contém lógica de negócio)
4. Clica **Create repository**

### 2. Fazer upload do ficheiro

1. No repositório vazio, clica **uploading an existing file**
2. Arrasta o ficheiro `index.html` para a página
3. Clica **Commit changes**

### 3. Ativar GitHub Pages

1. Vai a **Settings → Pages** (menu lateral esquerdo)
2. Em **Source**, seleciona **Deploy from a branch**
3. Em **Branch**, seleciona `main` e pasta `/ (root)`
4. Clica **Save**
5. Espera 1-2 minutos

### 4. Aceder à app

O URL será:
```
https://SEU-USERNAME.github.io/baviera-control/
```

Abre este URL no telemóvel.

### 5. Adicionar ao ecrã inicial (funciona como app)

**iPhone:**
1. Abre o URL no Safari
2. Toca no ícone de partilha (quadrado com seta)
3. Toca **Adicionar ao ecrã principal**

**Android:**
1. Abre o URL no Chrome
2. Toca nos 3 pontos (menu)
3. Toca **Adicionar ao ecrã principal**

---

## Primeiro uso da app

1. **Configuração** — introduz:
   - **URL do Projeto**: encontras em Supabase → Settings → API → Project URL
   - **Anon Key**: encontras em Supabase → Settings → API → `anon` `public`

2. **Login** — usa o email e password do utilizador criado em Supabase → Authentication

3. **Usar** — pesquisa, filtra por status, cria/edita/apaga registos

---

## Estrutura

```
baviera-control/
└── index.html    ← ficheiro único, contém tudo (HTML + CSS + JS)
```

Não precisa de build, não precisa de npm, não precisa de nada. É um ficheiro HTML que corre em qualquer browser.

---

## Segurança

- A **Anon Key** é pública por design (Supabase usa Row Level Security para proteger os dados)
- O **token de sessão** nunca é guardado em disco — expira quando fecha o browser
- A configuração (URL + Anon Key) é guardada em `localStorage` no browser do utilizador
- Se o repositório for **Private**, o GitHub Pages ainda funciona mas só para quem tem acesso

---

## Atualizar a app

Para fazer alterações:
1. Edita o `index.html` localmente ou diretamente no GitHub
2. Faz commit — o GitHub Pages atualiza automaticamente em ~1 minuto
