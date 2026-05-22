# Como atualizar um site no GitHub → Vercel

> Fluxo completo do zero até o site publicado.
> Repo: `https://github.com/convertamaisgf-bot/presencacerta`

---

## Parte 1 — Configuração inicial (só faz uma vez)

Esses passos já estão feitos nessa máquina. Se for em outro computador, repita aqui.

### 1. Abrir o terminal na pasta do projeto

No explorador de arquivos, navegue até:
```
C:\Users\gabri\OneDrive\Documentos\Claude\Projects\Criador de Sites
```
Clique com o botão direito em espaço vazio → **"Abrir no Terminal"** (ou abra o PowerShell e digite o caminho).

### 2. Inicializar o git na pasta

```bash
git init
```

### 3. Conectar ao repositório do GitHub

```bash
git remote add origin https://github.com/convertamaisgf-bot/presencacerta.git
```

### 4. Baixar o histórico do GitHub

```bash
git fetch origin
```

### 5. Criar a branch local apontando pro GitHub

```bash
git symbolic-ref HEAD refs/heads/main
git reset origin/main
```

Pronto — configuração feita. Daqui pra frente só usa a Parte 2.

---

## Parte 2 — Fluxo de atualização (usa sempre)

### 1. Editar o arquivo

Faça as alterações normalmente no `index.html` do site que quiser (ex: `elite-auto-detail/index.html`).

### 2. Marcar o arquivo para envio

```bash
git add elite-auto-detail/index.html
```

> Troque `elite-auto-detail` pelo nome da pasta do site que editou.

### 3. Criar o registro da mudança (commit)

```bash
git commit -m "descrição curta do que mudou"
```

Exemplos de mensagem:
- `"elite-auto-detail: ajusta contraste dos textos"`
- `"lumina-pilates: atualiza número de WhatsApp"`
- `"geloprime: adiciona seção de depoimentos"`

### 4. Enviar pro GitHub

```bash
git push origin main
```

O Vercel detecta o push automaticamente e publica em ~30 segundos.

---

## Resumo rápido (quando já está configurado)

```bash
git add nome-do-site/index.html
git commit -m "o que mudou"
git push origin main
```

---

## Problemas comuns

| Problema | Solução |
|---|---|
| `fatal: not a git repository` | Você não está na pasta certa. Confira o caminho e repita a Parte 1. |
| `error: failed to push` | Alguém fez push antes de você. Rode `git pull origin main` primeiro, depois `git push`. |
| Pediu login/senha | O Windows vai abrir uma janela pedindo as credenciais do GitHub da conta `convertamaisgf-bot`. |
