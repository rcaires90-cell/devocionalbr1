# ✝ Painel Sagrado — @devocionalbr1

Sistema completo de gestão de conteúdo TikTok Dark Devocional com IA integrada.

---

## 🚀 COMO COLOCAR NO AR (Passo a Passo)

### OPÇÃO 1: VERCEL (Recomendado — Grátis)

#### Passo 1 — Criar conta no GitHub
1. Acesse **github.com** e crie uma conta (se não tiver)
2. Clique em **"New repository"** (botão verde)
3. Nome: `devocionalbr1`
4. Deixe **Public** e clique **"Create repository"**

#### Passo 2 — Subir os arquivos para o GitHub
Opção A — Pelo site (mais fácil):
1. No repositório criado, clique **"uploading an existing file"**
2. Arraste TODOS os arquivos e pastas deste projeto
3. Clique **"Commit changes"**

Opção B — Pelo terminal (se souber usar):
```bash
cd devocional-br1
git init
git add .
git commit -m "primeiro commit"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/devocionalbr1.git
git push -u origin main
```

#### Passo 3 — Pegar sua chave da API Anthropic
1. Acesse **console.anthropic.com**
2. Crie uma conta (se não tiver)
3. Vá em **Settings > API Keys**
4. Clique **"Create Key"**
5. Copie a chave (começa com `sk-ant-...`)
6. ⚠️ IMPORTANTE: Você precisa ter créditos na conta. O plano gratuito dá US$5.

#### Passo 4 — Deploy na Vercel
1. Acesse **vercel.com** e faça login com sua conta GitHub
2. Clique **"Add New" > "Project"**
3. Selecione o repositório `devocionalbr1`
4. Em **"Environment Variables"**, adicione:
   - Name: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-sua-chave-aqui`
5. Clique **"Deploy"**
6. Aguarde ~1 minuto
7. ✅ Pronto! Seu sistema vai estar em `devocionalbr1.vercel.app`

---

### OPÇÃO 2: NETLIFY (Alternativa — Grátis)

1. Acesse **netlify.com** e conecte com GitHub
2. Clique **"New site from Git"**
3. Selecione o repositório
4. Build command: `npm run build`
5. Publish directory: `dist`
6. Em **Site settings > Environment variables**, adicione `ANTHROPIC_API_KEY`
7. ⚠️ Nota: Netlify Functions têm formato diferente. Pode precisar adaptar o arquivo `api/claude.js`

---

### OPÇÃO 3: RODAR NO SEU COMPUTADOR (Local)

```bash
# 1. Instale Node.js em nodejs.org

# 2. Abra o terminal na pasta do projeto

# 3. Instale as dependências
npm install

# 4. Crie o arquivo .env com sua chave
cp .env.example .env
# Edite o .env e cole sua chave

# 5. Rode o projeto
npm run dev

# 6. Abra no navegador: http://localhost:5173
```

---

## 📱 COMO USAR NO CELULAR

Depois de fazer o deploy na Vercel:
1. Abra o link no navegador do celular
2. No iPhone: toque em **Compartilhar > Adicionar à Tela Inicial**
3. No Android: toque nos **3 pontos > Adicionar à tela inicial**
4. Agora funciona como um app!

---

## 💰 QUANTO CUSTA?

| Item | Custo |
|------|-------|
| Vercel (hosting) | **Grátis** |
| GitHub | **Grátis** |
| API Anthropic | ~US$5/mês (plano gratuito dá US$5) |

Cada geração de conteúdo custa ~US$0.003 (menos de 1 centavo).
Com US$5 você gera aproximadamente **1.500 roteiros**.

---

## 🔧 PERSONALIZAÇÃO

Para mudar o nome do canal, edite a variável `U` no topo do arquivo `src/App.jsx`:
```javascript
const U = "seu_usuario_aqui";
```

---

## 📂 ESTRUTURA DO PROJETO

```
devocional-br1/
├── api/
│   └── claude.js        ← Proxy seguro para API (sua chave fica no servidor)
├── src/
│   ├── App.jsx           ← App principal
│   └── main.jsx          ← Entrada React
├── index.html            ← HTML base
├── package.json          ← Dependências
├── vite.config.js        ← Config do Vite
├── vercel.json           ← Config Vercel
├── .env.example          ← Template de variáveis
└── .gitignore
```
