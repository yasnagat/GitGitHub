# GitGitHub
Tutorial de como utilizar o git e conectar com o github, explicação de conceitos e componentes básicos para entender o que é e como fazer o versionamento de código.
# O que é e para o que serve?

**Git** é um sistema de versionamento de código distribuído, ou seja, uma ferramenta para registrar versões de um código. 

Suas principais funcionalidades são registrar alterações em arquivos e permitir a colaboração offline e online entre vários desenvolvedores, simultaneamente. 

A forma de uso mais comum é com o programa **GitHub**, uma plataforma de hospedagem de códigos e arquivos em nuvem compartilhável e colaborativo.

---

### 📁 Repositório `.git`

É uma pasta usada pelo Git para controlar as alterações feitas em arquivos. Contém todas as versões de cada arquivo salvo no repositório. 

- É feito um por projeto/pasta.
- Cada repositório é independente.
- Equipes normalmente usam um repositório central (por ex: no GitHub) para acompanhar e controlar alterações de um projeto.

---

### 🌿 Branch

Um *branch* (ramo) é uma ramificação do código, como um galho de uma árvore.

No Git, é comum utilizar branches para:
- Trabalhos simultâneos
- Diferentes fases de um projeto
- Experimentação de funcionalidades

O branch padrão é o `master` (ou `main`, veja abaixo como alterar). Cada commit feito é adicionado na "linha do tempo" desse branch.

---

### 🛠️ Manipulando Branches

1. **Criar um novo branch:**
git branch nomeDoNovoBranch

2. **Criar e trocar para o novo branch:**
git checkout -b nomeDoNovoBranch

3. **Verificar o branch atual:**
git log --oneline --decorate

4. **Alternar entre branches:**
git checkout nomeDoBranch

5. **Ver histórico gráfico de commits:**
git log --oneline --decorate --graph --all

6. **Remover um branch:**
git branch -d nomeDoBranch

7. **Mesclar branches:**
No branch que vai receber as alterações, execute:
git merge nomeDoOutroBranch

8. **Verificar status do branch:**
git status

9. **Listar todos os branches:**
git branch

---

### 🔒 Segurança contra modificações ocultas

O Git usa verificação por **checksum** (hash SHA-1) para garantir a integridade dos arquivos.

Exemplo de hash:

24b9da6552252987aa493b52f8696cd6d3b00373


Esses hashes identificam com precisão o conteúdo de cada snapshot do código.

---

# ⚙️ Como funciona?

1. Um repositório Git (`.git`) é criado na pasta do projeto.
2. Um arquivo é modificado no diretório local.
3. O arquivo modificado é **staged** (preparado para commit).

> O Git gera um hash (SHA-1), guarda o snapshot e adiciona à staging area.

4. O arquivo é **committed** (gravado no banco de dados local).

> O Git armazena metadados: autor, data, mensagem, ponteiros para commits anteriores etc.

---

### 📂 Diretório do Git

É onde ficam os metadados e objetos de banco de dados que representam a estrutura e histórico do projeto.

---

### 📌 Estados dos arquivos no Git:

| Estado     | Descrição |
|------------|-----------|
| Committed  | Alterações já salvas no banco de dados |
| Modified   | Arquivo alterado, mas ainda não preparado |
| Staged     | Arquivo pronto para o próximo commit |

---

# 🧪 Tutorial

## I. Instalação no Linux

1. Abra o terminal.
2. Execute:
sudo apt-get install git


---

## II. Configuração do Git

### Nome e e-mail:
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"

### Definir `main` como branch padrão:
git config --global init.defaultBranch main

### Se o repositório já foi criado com `master`, renomeie:
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a

---

## III. Criar um repositório Git

### a) Criar a partir de uma pasta local:
cd sua-pasta/
git init
git add --all
git commit -m "Primeiro commit"

> Use mensagens claras nos commits para facilitar o entendimento.

### b) Clonar um repositório existente:
git clone https://github.com/usuario/repositorio.git

---

## IV. Conectar repositório local com GitHub

1. Crie o repositório no GitHub.
2. Copie a URL HTTPS.
git remote add origin https://github.com/usuario/repositorio.git

---

💡 **Dica:** Você pode usar `git push -u origin main` para enviar e definir `main` como branch de rastreamento padrão.
