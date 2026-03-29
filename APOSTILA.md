# Apostila de Git e GitHub

## Introdução

Esta apostila é um material prático para alunos que estão começando com Git e GitHub. O objetivo é ensinar os conceitos básicos, os comandos mais usados e como trabalhar com um repositório local e remoto.

### Para quem é este material?

- estudantes iniciantes em programação
- pessoas que querem aprender controle de versão
- quem precisa enviar projetos para o GitHub

## Objetivos da apostila

Ao final deste material, você será capaz de:

- entender o que é Git
- criar e gerenciar um repositório local
- fazer commits para registrar mudanças
- conectar um repositório local ao GitHub
- enviar código para o GitHub
- atualizar seu projeto com mudanças remotas

## Estrutura do projeto

O repositório contém:

- `main.py`: arquivo de exemplo em Python
- `README.md`: documentação resumida e tutorial
- `APOSTILA.md`: este material didático
- `.gitignore`: lista de arquivos e pastas ignorados pelo Git

## 1. O que é Git?

Git é um sistema de controle de versão distribuído. Ele registra o histórico do seu projeto e permite voltar a versões anteriores sempre que necessário.

### Por que usar Git?

- controle de versões detalhado
- histórico de mudanças disponível
- fácil recuperação de erros
- colaboración em equipe

## 2. Componentes principais do Git

- `repositório` (repo): local onde o projeto e seu histórico são armazenados
- `branch`: linha de desenvolvimento independente
- `commit`: registro de alterações em um momento específico
- `branch principal` (`main` ou `master`): versão principal do projeto
- `remote`: cópia do repositório hospedada em um serviço como GitHub

## 2.1 O que é branch?

Uma branch é uma linha separada de trabalho dentro do mesmo repositório. Ela permite que você faça mudanças sem afetar a branch principal.

Use branches para:

- desenvolver uma nova função
- corrigir um bug
- experimentar uma ideia sem riscos

### Comandos básicos de branch

- Ver branches locais:
  ```bash
git branch
  ```
- Criar uma nova branch:
  ```bash
git branch nome-da-branch
  ```

## 2.2 Mudar de branch com checkout

O comando `checkout` muda o seu ambiente de trabalho para outra branch.

- Mudar para uma branch existente:
  ```bash
git checkout nome-da-branch
  ```
- Criar e mudar para uma nova branch em um passo:
  ```bash
git checkout -b nome-da-branch
  ```

Depois de usar `checkout`, qualquer commit será feito na branch ativa.

## 2.3 Misturar branches com merge

Quando uma branch de teste estiver pronta, você pode trazer suas mudanças para a branch principal.

Uma analogia útil: imagine que duas pessoas escreveram partes diferentes de uma tarefa em folhas separadas. O `merge` é o momento de juntar essas duas folhas em um único documento.

- Mudar para a branch principal:
  ```bash
git checkout main
  ```
- Trazer as mudanças da outra branch:
  ```bash
git merge nome-da-branch
  ```

Se houver conflitos, o Git não consegue decidir sozinho qual alteração é a correta.

Imagine que duas pessoas escreveram versões diferentes da mesma frase em duas folhas. O `merge` tenta juntar as folhas, mas quando a mesma frase mudou de maneiras diferentes, o Git pede sua ajuda para escolher a melhor combinação.

Como resolver um conflito de merge:

1. Abra o arquivo marcado como em conflito.
2. Veja as diferenças entre as versões.
3. Escolha qual trecho manter ou combine os dois.
4. Salve o arquivo.
5. Diga ao Git que o conflito foi resolvido:
   ```bash
git add nome-do-arquivo
   ```
6. Termine o merge com:
   ```bash
git commit
   ```

### Exemplo prático de conflito

1. Crie uma branch de teste:
   ```bash
git checkout -b editar-main
   ```
2. Altere a mesma linha em `main.py` e faça commit:
   ```bash
git add main.py
git commit -m "Alteração na branch editar-main"
   ```
3. Volte para a branch `main`:
   ```bash
git checkout main
   ```
4. Altere a mesma linha de `main.py` de forma diferente e faça commit:
   ```bash
git add main.py
git commit -m "Alteração na branch main"
   ```
5. Faça o merge da branch de teste:
   ```bash
git merge editar-main
   ```

O Git pode mostrar conflito. Abra `main.py` e você verá marcas como:

```text
Texto da branch atual
```

- `<<<<<<< HEAD`: versão atual da branch em que você está.
- `=======`: separa as duas versões.
- `>>>>>>> editar-main`: versão da branch que você está mesclando.

Para resolver, escolha a versão correta ou combine as duas, remova as marcas e salve.

Depois, marque o conflito como resolvido:

```bash
git add main.py
```

E finalize com:

```bash
git commit
```

## 3. Parte 2: Entendendo o GitHub

GitHub é um serviço online que guarda seu repositório remoto e facilita a colaboração.

### 3.1 Para que serve o GitHub?

- guardar seu projeto na nuvem como backup
- compartilhar o código com outras pessoas
- trabalhar em equipe usando branches e pull requests
- acompanhar tarefas e erros com issues
- mostrar seu trabalho como portfólio

### 3.2 Por que usar o GitHub?

- mantém seu código seguro na nuvem
- facilita o trabalho em equipe
- permite revisar mudanças antes de juntar ao projeto principal
- ajuda a organizar tarefas e problemas
- dá visibilidade ao seu trabalho para quem vê seu perfil

### 3.3 Como criar um repositório no GitHub

1. Acesse `https://github.com` e faça login.
2. Clique em `New repository`.
3. Digite o nome do repositório, por exemplo `JornadaDados`.
4. Escolha se o repositório será público ou privado.
5. Adicione um `README.md` inicial, se desejar.
6. Clique em `Create repository`.

### 3.4 O que o GitHub oferece?

- Repositórios: projetos hospedados na nuvem.
- Clone: baixar o projeto para seu computador.
- Fork: copiar um projeto de outra pessoa para o seu GitHub.
- Pull request: pedir para juntar mudanças de uma branch ou fork.
- Issues: registrar erros, dúvidas e tarefas.
- Actions: automatizar testes e publicação.

### 3.5 Fluxo de trabalho no GitHub

1. Crie uma branch local para uma nova tarefa.
2. Faça commits claros e regulares.
3. Envie sua branch para o GitHub:

```bash
git push origin nome-da-branch
```

4. No GitHub, abra um pull request para revisar a mudança.
5. Depois de aprovado, faça o merge no GitHub ou local.
6. Atualize sua cópia local com:

```bash
git pull origin main
```

### 3.6 GitHub para iniciantes

Pense no GitHub como um quadro de tarefas e um histórico do seu trabalho. Ele permite que outras pessoas vejam, comentem e colaborem com você no mesmo projeto.

### 3.7 Protocolos de comunicação

Para o Git e o GitHub funcionarem, o seu computador se comunica com servidores usando protocolos. Um protocolo é um conjunto de regras para troca de dados.

- HTTP: protocolo usado para navegar em sites. Ele envia dados sem criptografia.
- HTTPS: versão segura do HTTP. Ele protege a conexão usando criptografia.
- SSH: protocolo seguro que usa chaves para autenticar e transferir dados sem senha a cada vez.
- FTP: protocolo antigo para transferir arquivos. Não é usado pelo GitHub para comandos Git, mas aparece em outros tipos de servidor.

No GitHub, os dois protocolos mais usados são HTTPS e SSH.

- HTTPS: `https://github.com/usuario/repositorio.git`
- SSH: `git@github.com:usuario/repositorio.git`

Use HTTPS se quiser algo mais simples, ou SSH se preferir trabalhar com chaves e evitar digitar usuário/senha a cada push.

### 3.8 Chave SSH

A chave SSH é um par de arquivos usados para autenticar sem senha.

- A chave privada fica no seu computador e deve ficar em segredo.
- A chave pública fica no GitHub.

Para criar uma chave SSH:

```bash
ssh-keygen -t rsa -b 4096 -C "seu-email@example.com"
```

Depois, copie o conteúdo de `~/.ssh/id_rsa.pub` e cole em `Settings > SSH and GPG keys` no GitHub.

## 4. Configuração inicial

### 3.1 Iniciar o repositório local

No terminal, na pasta do projeto, execute:

```bash
git init
```

Este comando cria a pasta `.git` com todo o histórico do repositório.

Se o seu projeto já tem arquivos e ainda não usa Git, basta iniciar o repositório nessa pasta. O Git passa a ver todos os arquivos não rastreados.

Em seguida, adicione os arquivos e faça o primeiro commit:

```bash
git add .
git commit -m "Primeiro commit"
```

### 3.2 Verificar o status

Para ver os arquivos alterados e não adicionados ao controle de versão:

```bash
git status
```

### 3.3 Adicionar arquivos ao stage

Para adicionar todos os arquivos modificados:

```bash
git add .
```

Para adicionar apenas um arquivo específico:

```bash
git add main.py
```

### 3.4 Fazer commit

Salve as alterações no histórico com uma mensagem explicativa:

```bash
git commit -m "Primeiro commit"
```

### 3.5 Ver o histórico de commits

Para ver a lista de commits do projeto:

```bash
git log
```

Para ver o histórico em formato compacto e gráfico:

```bash
git log --oneline --graph --all
```

Esse comando mostra todos os commits de forma resumida e desenha um gráfico de branches, o que ajuda a ver como as alterações caminham e se juntam.

### 3.6 Restaurar mudanças

Se você fez alterações em um arquivo e quer voltar ao estado do último commit, use:

```bash
git restore nome-do-arquivo
```

Esse comando cancela as mudanças não salvas no stage.

### 3.7 Resetar o histórico e o stage

O comando `git reset` ajuda a voltar no histórico ou remover arquivos da área de stage.

- Para tirar um arquivo do stage e continuar com as alterações no código:
  ```bash
git reset HEAD nome-do-arquivo
  ```
- Para voltar um commit no histórico sem perder as alterações locais:
  ```bash
git reset --soft HEAD~1
  ```
- Para voltar para o commit anterior e descartar todas as mudanças não salvas:
  ```bash
git reset --hard HEAD~1
  ```

Cuidado: `--hard` apaga mudanças que não estão salvas em um commit.

### 3.8 Alterar o último commit

Se você cometeu e quer editar a mensagem do commit ou incluir mudanças esquecidas, use:

```bash
git commit --amend
```

Isso altera o último commit em vez de criar um novo.

## 4. Criar e usar o repositório no GitHub

### 4.1 Criar um repositório no GitHub

1. Acesse `https://github.com`
2. Clique em `New repository`
3. Defina um nome para o repositório
4. Deixe o repositório como público ou privado, conforme sua preferência
5. Clique em `Create repository`

### 4.2 Conectar o repositório local ao GitHub

No terminal, execute:

```bash
git remote add origin https://github.com/SEU_USUARIO/NOME_REPO.git
```

Substitua `SEU_USUARIO` e `NOME_REPO` pelos seus dados.

### 4.3 Enviar alterações para o GitHub

```bash
git push -u origin main
```

Se sua branch principal for `master`, use:

```bash
git push -u origin master
```

### 4.4 Atualizar o projeto local com mudanças remotas

Quando quiser trazer atualizações do GitHub para o seu computador:

```bash
git pull origin main
```

## 5. Testar o arquivo `main.py`

O arquivo `main.py` contém um exemplo simples em Python. Para testar:

1. Abra o terminal na pasta do projeto.
2. Verifique se o Python está instalado:

```bash
python --version
```

3. Execute o programa:

```bash
python main.py
```

Saída esperada:

```text
Iniciando estudo com Git e GitHub
Soma de 10 + 5 = 15
Este arquivo main.py é parte do projeto JornadaDados
```

## 6. Comandos principais

- `git init` : inicia o repositório local
- `git status` : verifica o estado dos arquivos
- `git add .` : adiciona todos os arquivos ao stage
- `git add <arquivo>` : adiciona um arquivo específico
- `git commit -m "mensagem"` : registra as alterações
- `git log` : mostra o histórico de commits
- `git log --oneline --graph --all` : mostra o histórico resumido em forma de gráfico com todas as branches
- `git restore <arquivo>` : desfaz alterações não adicionadas ao stage
- `git reset` : remove arquivos do stage ou volta o histórico local
- `git commit --amend` : altera o último commit
- `git merge <branch>` : combina outra branch com a branch atual
- `git branch` : lista branches locais
- `git checkout <branch>` : muda para outra branch
- `git checkout -b <branch>` : cria e muda para uma nova branch
- `git remote add origin <URL>` : adiciona o repositório remoto
- `git push -u origin main` : envia para o GitHub
- `git pull origin main` : baixa mudanças do GitHub

## 7. Exercícios práticos

1. Abra o terminal na pasta do projeto.
2. Execute `git status` e observe os arquivos listados.
3. Modifique `main.py` e veja as alterações com `git diff`.
4. Crie uma nova branch para testar outra versão:
   ```bash
git checkout -b estudo-branch
   ```
5. Faça uma alteração em `main.py`, adicione e commit:
   ```bash
git add main.py
git commit -m "Teste de branch estudo-branch"
   ```
6. Volte para a branch principal:
   ```bash
git checkout main
   ```
7. Envie para o GitHub com `git push origin main`.

## 8. Dicas finais

- Use mensagens de commit claras e objetivas.
- Faça commits pequenos e frequentes.
- Verifique sempre `git status` antes de commitar.
- Atualize o `.gitignore` para não enviar arquivos temporários.

---

Boa prática de estudos: execute os comandos no terminal e acompanhe a saída passo a passo.