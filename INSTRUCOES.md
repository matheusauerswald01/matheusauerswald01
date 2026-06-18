# 🚀 Como publicar seu perfil no GitHub

Guia completo pra colocar seu README animado no ar. Leva ~5 minutos.

---

## 📦 O que tem nesta pasta

```
perfilGitHub/
├── README.md                    ← o conteúdo do seu perfil
├── INSTRUCOES.md                ← este guia
└── .github/
    └── workflows/
        └── snake.yml            ← gera a cobrinha 🐍 automaticamente
```

---

## 1️⃣ Criar o repositório especial

O GitHub só exibe o README no seu perfil se o repositório tiver **exatamente o mesmo nome do seu usuário**.

1. Vá em **https://github.com/new**
2. **Repository name:** `matheusauerswald01` (igualzinho ao seu usuário)
3. Marque como **Public** ✅ (obrigatório — não funciona em privado)
4. **NÃO** marque "Add a README file" (vamos enviar o nosso)
5. Clique em **Create repository**

> 💡 Se aparecer a mensagem *"matheusauerswald01/matheusauerswald01 is a ✨special✨ repository"*, é sinal de que você acertou o nome.

---

## 2️⃣ Enviar os arquivos

### Opção A — Pelo terminal (recomendado)

Na pasta `perfilGitHub`, rode:

```bash
cd ~/Desktop/perfilGitHub
git init
git add .
git commit -m "Perfil animado e interativo ✨"
git branch -M main
git remote add origin https://github.com/matheusauerswald01/matheusauerswald01.git
git push -u origin main
```

### Opção B — Pelo site (sem terminal)

1. Abra o repositório recém-criado
2. Clique em **uploading an existing file**
3. Arraste o `README.md` e a pasta `.github` inteira
4. Clique em **Commit changes**

---

## 3️⃣ Ativar a cobrinha 🐍 (GitHub Action)

A cobrinha não usa um site externo — quem gera o desenho é uma **Action** que roda no seu próprio repositório. Por isso ela só aparece **depois do primeiro run**.

1. No repositório, vá na aba **Actions**
2. Se aparecer um aviso pedindo, clique em **"I understand my workflows, enable them"**
3. Na lista à esquerda, clique em **🐍 Gerar animação da cobrinha**
4. Clique em **Run workflow** → **Run workflow** (botão verde)
5. Espere ~1 minuto. Quando terminar (✅ verde), a Action cria uma branch chamada **`output`** com os arquivos `github-snake*.svg`

> ⚠️ **Importante:** se você abrir o perfil **antes** desse primeiro run, a imagem da cobrinha vai aparecer quebrada (404). É normal — basta rodar a Action uma vez. Depois ela se atualiza sozinha todo dia.

Para conferir: acesse
`https://github.com/matheusauerswald01/matheusauerswald01/branches`
e veja se a branch `output` existe.

---

## ✅ Pronto!

Abra **https://github.com/matheusauerswald01** e veja seu perfil animado. 🎉

---

## 🔧 Dicas e solução de problemas

### "Os cards de estatísticas às vezes não carregam"
A instância pública do `github-readme-stats` é gratuita e compartilhada — em horários de pico ela atinge o limite da API do GitHub e o card fica em branco. É temporário; geralmente volta sozinho.

**Para deixar 100% confiável** (opcional): faça um *fork* do repositório
[anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats),
faça o deploy no seu Vercel com um token pessoal do GitHub (env `PAT_1`), e troque
no `README.md` o domínio `github-readme-stats.vercel.app` pelo seu domínio do Vercel.

### Sobre os troféus
O serviço **oficial** (`github-profile-trophy.vercel.app`) estava **fora do ar** na
montagem do perfil, então o README já vem usando um **espelho que funciona**:
`github-trophies.vercel.app` (mesmos parâmetros, só muda o domínio).

Se um dia o espelho cair e o oficial voltar, é só trocar o host de volta para
`github-profile-trophy.vercel.app` no `README.md`. Outro espelho alternativo:
`profile-trophy.vercel.app`.

### "A cobrinha continua quebrada mesmo depois de rodar a Action"
- Confirme que a branch `output` foi criada (passo 3).
- O GitHub faz cache das imagens (camo). Force atualização com `Ctrl/Cmd + Shift + R`.
- Verifique se o nome de usuário no `README.md` está correto.

### "Mudei algo e não atualiza"
O GitHub guarda cache das imagens por alguns minutos. Aguarde ou force refresh.

### Quero mostrar também repositórios/contribuições privadas nas estatísticas
Isso só funciona com a versão *self-hosted* do stats (com seu token pessoal),
como descrito acima. Na instância pública só aparecem dados públicos.

---

## 🎨 Personalizar

Quer mudar o visual? No `README.md`, procure e ajuste:

- **Cores:** os hex `22D3EE` (ciano), `7C3AED` (roxo) e `F72585` (magenta) se repetem em vários lugares — troque por outras cores (sempre **sem o `#`** nas URLs).
- **Tema dos cards:** troque `theme=tokyonight` por `radical`, `synthwave`, `dracula`, `gruvbox`, etc.
- **Frases do typing:** edite o parâmetro `lines=` (frases separadas por `;`, espaços viram `+`).
- **Frases/seções:** é Markdown normal, edite à vontade.

É só me chamar se quiser ajustar qualquer coisa! 💜
