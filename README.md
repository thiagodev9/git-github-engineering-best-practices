# Git & GitHub Engineering Best Practices

## Overview / Visão geral

**English**
This repository contains a practical guide to Git and GitHub used in real engineering environments.
The goal is to help developers, data engineers, and analysts understand not just commands, but professional workflows used in production teams.

**Português**
Este repositório contém um guia prático de Git e GitHub usado em ambientes de engenharia reais.
O objetivo é ajudar desenvolvedores, engenheiros de dados e analistas a entender não apenas comandos, mas fluxos de trabalho profissionais usados em equipes de produção.

## Topics covered / Tópicos abordados

- Git fundamentals / Fundamentos do Git
- Branching strategies / Estratégias de branching
- Pull Requests / Pull Requests
- Code Review / Revisão de código
- Gitflow vs Trunk Based
- Versioning Data Pipelines / Versionamento de pipelines de dados
- dbt project versioning / Versionamento de projetos dbt
- Conflict resolution / Resolução de conflitos
- Engineering best practices / Boas práticas de engenharia

## Who is this for? / Para quem é?

- Data Engineers / Engenheiros de Dados
- Software Engineers / Engenheiros de Software
- Analytics Engineers / Engenheiros de Analytics
- Students preparing for tech interviews / Estudantes se preparando para entrevistas técnicas

## Why this repository exists / Por que este repositório existe

Many tutorials teach Git commands.
Few teach how engineering teams actually use Git in production.
This repo focuses on practical usage.

Muitos tutoriais ensinam comandos do Git.
Poucos ensinam como equipes de engenharia realmente usam Git em produção.
Este repositório foca no uso prático.

## Author / Autor

Thiago Camargo  
Senior Data Engineer | AI Engineer | Data Platforms | AWS | Databricks | Spark

## Contributions / Contribuições

Feel free to open pull requests or suggestions.
Sinta-se à vontade para abrir pull requests ou sugestões.

---

## How to use this repository / Como usar este repositório

1. Start with the fundamentals in [01-git-fundamentals/README.md](git-github-engineering-best-practices/01-git-fundamentals/README.md).
2. After fundamentals, read [02-branching-strategies/README.md](02-branching-strategies/README.md).
3. Continue with [03-collaboration/README.md](03-collaboration/README.md).
4. Learn real-world workflows in [04-real-world-workflows/README.md](04-real-world-workflows/README.md).
5. Review engineering best practices in [05-best-practices/README.md](05-best-practices/README.md).
6. Use [cheatsheet/README.md](cheatsheet/README.md) as a quick reference.
7. Use [APOSTILA.md](APOSTILA.md) if you want additional study material.

1. Comece pelos fundamentos em [01-git-fundamentals/README.md](git-github-engineering-best-practices/01-git-fundamentals/README.md).
2. Depois dos fundamentos, leia [02-branching-strategies/README.md](02-branching-strategies/README.md).
3. Continue com [03-collaboration/README.md](03-collaboration/README.md).
4. Aprenda fluxos de trabalho do mundo real em [04-real-world-workflows/README.md](04-real-world-workflows/README.md).
5. Revise as melhores práticas de engenharia em [05-best-practices/README.md](05-best-practices/README.md).
6. Use [cheatsheet/README.md](cheatsheet/README.md) como referência rápida.
7. Use [APOSTILA.md](APOSTILA.md) se quiser material de estudo adicional.

## Como navegar pelos materiais / How to navigate the materials

- [Guia de engenharia Git/GitHub](git-github-engineering-best-practices/README.md) / [Git/GitHub engineering guide](git-github-engineering-best-practices/README.md)
- [Git Init](git-github-engineering-best-practices/01-git-fundamentals/git-init.md) / [Git Init](git-github-engineering-best-practices/01-git-fundamentals/git-init.md)
- [Git Clone](git-github-engineering-best-practices/01-git-fundamentals/git-clone.md) / [Git Clone](git-github-engineering-best-practices/01-git-fundamentals/git-clone.md)
- [Git Add e Commit](git-github-engineering-best-practices/01-git-fundamentals/git-add-commit.md) / [Git Add and Commit](git-github-engineering-best-practices/01-git-fundamentals/git-add-commit.md)
- [Guia Git Fundamentals](git-github-engineering-best-practices/01-git-fundamentals/README.md) / [Git Fundamentals Guide](git-github-engineering-best-practices/01-git-fundamentals/README.md)

## 1. O que é Git?

Git é um sistema de controle de versão. Ele permite que você:

- acompanhe alterações no código
- volte para versões antigas quando necessário
- trabalhe em equipe sem perder histórico

### Por que usar Git?

- segurança: histórico de mudanças disponível
- organização: cada alteração fica registrada
- colaboração: várias pessoas podem trabalhar no mesmo projeto

## 2. Passo a passo: criar o repositório local

### 2.1 Inicializar o repositório

No terminal, entre na pasta do projeto e execute:

```bash
git init
```

Isso cria uma pasta oculta `.git` que registra todas as mudanças.

Se você já tem um projeto com arquivos e ainda não usa Git, este é o momento de começar. O Git passa a monitorar o diretório e mostra os arquivos não rastreados.

Depois de inicializar, adicione os arquivos e faça o primeiro commit:

```bash
git add .
git commit -m "Primeiro commit"
```

### 2.2 Verificar o status

Depois de fazer mudanças, use:

```bash
git status
```

Esse comando mostra quais arquivos foram alterados e ainda não estão prontos para commit.

### 2.3 Adicionar arquivos ao stage

Para preparar todos os arquivos para o commit:

```bash
git add .
```

Para adicionar apenas um arquivo específico:

```bash
git add main.py
```

### 2.4 Fazer commit

O commit é o ato de salvar um conjunto de mudanças no histórico.

```bash
git commit -m "Primeiro commit"
```

A mensagem deve ser curta e descrever o que mudou.

## 3. Como usar o GitHub

GitHub é um serviço online onde você pode guardar seu repositório na nuvem.

### 3.1 Criar repositório no GitHub

1. Acesse `https://github.com`
2. Clique em `New repository`
3. Dê um nome ao repositório, por exemplo `JornadaDados`
4. Crie o repositório

### 3.2 Conectar o repositório local ao GitHub

Copie a URL do repositório e cole no comando abaixo:

```bash
git remote add origin https://github.com/SEU_USUARIO/NOME_REPO.git
```

Substitua `SEU_USUARIO` e `NOME_REPO` pelos seus dados.

### 3.3 Enviar para o GitHub

```bash
git push -u origin main
```

Se a branch principal for `master`, use:

```bash
git push -u origin master
```

## 4. Parte 2: Entendendo o GitHub

GitHub é um site que guarda seu repositório remoto e facilita a colaboração em projetos. Ele serve para:

- hospedar o código na nuvem como backup seguro
- compartilhar o projeto com colegas ou com o mundo
- colaborar com outras pessoas usando branches e pull requests
- acompanhar tarefas, erros e melhorias com issues
- mostrar seu trabalho como portfólio

### 4.1 Por que usar o GitHub?

- backup automático dos seus arquivos na internet
- trabalho em equipe mais organizado
- histórico de mudanças fácil de visualizar
- revisão de código com comentários e aprovações
- possibilidade de contribuir em projetos de outras pessoas

### 4.2 Como criar um repositório no GitHub

1. Acesse `https://github.com` e faça login.
2. Clique em `New repository`.
3. Digite o nome do repositório, por exemplo `JornadaDados`.
4. Escolha se será público ou privado.
5. Marque a opção `Add a README file` se quiser uma página inicial automática.
6. Clique em `Create repository`.

Depois, use os comandos do Git local para conectar e enviar o projeto.

### 4.3 O que o GitHub oferece?

- Repositórios: cópias do projeto hospedadas online.
- Clone: baixar o projeto para o computador.
- Fork: copiar um projeto de outra pessoa para o seu GitHub.
- Pull request: pedir para juntar mudanças de uma branch ou fork.
- Issues: registrar erros, pedidos e tarefas.
- Actions: automatizar testes e deploys.

### 4.4 Fluxo básico no GitHub

1. Crie uma branch local para trabalhar em algo novo.
2. Faça commits claros e regulares.
3. Envie sua branch para o GitHub com:

```bash
git push origin nome-da-branch
```

4. Abra um pull request no GitHub para revisão.
5. Após aprovação, faça merge na branch principal.
6. Atualize sua cópia local:

```bash
git pull origin main
```

### 4.5 Exemplo rápido de uso

- `git add .`
- `git commit -m "Adicionar nova funcionalidade"`
- `git push origin minha-branch`
- abrir um pull request
- revisar e fazer merge
- `git pull origin main`

### 4.6 Dica para iniciantes

Pense no GitHub como uma vitrine do seu trabalho. Um repositório bem organizado, com `README.md`, descrições claras e boas mensagens de commit, ajuda outras pessoas a entenderem seu projeto.

### 4.7 Protocolos de comunicação

Quando você envia ou recebe código do GitHub, o computador usa protocolos para conversar pela internet. Um protocolo é um conjunto de regras que define como os dados são enviados e recebidos.

- HTTP: protocolo usado para acessar páginas web. Ele é simples, mas não é seguro para enviar senhas ou dados confidenciais.
- HTTPS: é a versão segura do HTTP. Ele criptografa os dados, deixando a conexão protegida. Use sempre HTTPS sempre que possível.
- SSH: protocolo seguro usado para acessar servidores e enviar dados com chaves de criptografia. No GitHub, a URL SSH parece `git@github.com:usuario/repositorio.git`.
- FTP: protocolo antigo para transferir arquivos. Ele não é usado pelo GitHub para comandos de Git, mas ainda existe para enviar e baixar arquivos em outros servidores.

No GitHub, os métodos mais comuns são HTTPS e SSH. Se você escolher HTTPS, o Git pedirá seu login ou token. Se escolher SSH, você usa uma chave pública/privada para acessar o repositório sem precisar digitar a senha toda vez.

#### Como funciona a chave SSH

Uma chave SSH é um par de arquivos: uma chave privada e uma chave pública.

- A chave privada fica segura no seu computador.
- A chave pública vai para o GitHub.

Quando você se conecta ao GitHub pelo SSH, o servidor verifica se a chave pública cadastrada combina com a sua chave privada. Se bater, a conexão é liberada.

A chave pública costuma ficar em `~/.ssh/id_rsa.pub` e pode ser copiada para o GitHub em `Settings > SSH and GPG keys`.

Para gerar uma chave nova, use:

```bash
ssh-keygen -t rsa -b 4096 -C "seu-email@example.com"
```

Depois copie o conteúdo de `~/.ssh/id_rsa.pub` e cole no GitHub.

### 3.4 Trabalhando com branches

Uma branch é uma linha de desenvolvimento independente. Você pode criar uma branch para testar algo novo sem alterar a versão principal.

- Ver branches existentes:
  ```bash
git branch
  ```
- Criar uma nova branch:
  ```bash
git branch nome-da-branch
  ```
- Mudar para outra branch:
  ```bash
git checkout nome-da-branch
  ```
- Criar e mudar para uma branch ao mesmo tempo:
  ```bash
git checkout -b nome-da-branch
  ```

### 3.5 Misturar branches com merge

Quando uma branch de teste está pronta, você pode combinar suas mudanças com a branch principal.

Imagine duas estradas diferentes que se encontram em um cruzamento: o `merge` pega a estrada da sua branch e a junta com a estrada da branch principal.

- Mudar para a branch principal:
  ```bash
git checkout main
  ```
- Fazer merge da branch de trabalho:
  ```bash
git merge nome-da-branch
  ```

Se houver conflitos, o Git não consegue juntar automaticamente duas versões diferentes do mesmo arquivo.

Uma boa analogia é imaginar duas pessoas escrevendo a mesma frase em duas cópias diferentes de um documento. Se as duas mudarem a mesma palavra de forma diferente, o Git precisa que você escolha qual versão manter ou combine manualmente as duas ideias.

Para resolver um conflito de merge:

1. Abra o arquivo em conflito.
2. Escolha se vai manter a mudança de uma branch, da outra, ou unir as duas.
3. Salve o arquivo.
4. Marque o conflito como resolvido:
   ```bash
git add nome-do-arquivo
   ```
5. Finalize o merge com um commit:
   ```bash
git commit
   ```

#### Exemplo prático de conflito

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

Nesse momento, o Git pode mostrar um conflito. Abra `main.py` e você verá marcas como estas:

```text
<<<<<<< HEAD
Texto da branch atual
=======
Texto da branch editar-main
>>>>>>> editar-main
```

- `<<<<<<< HEAD` mostra a sua versão atual.
- `=======` separa as duas versões.
- `>>>>>>> editar-main` mostra a versão da branch que está sendo unida.

Para resolver o conflito:

1. Escolha se vai manter a mudança da branch atual, da branch `editar-main`, ou combinar as duas.
2. Apague as linhas de marcação `<<<<<<<`, `=======` e `>>>>>>>`.
3. Salve o arquivo.
4. Marque o conflito como resolvido:
   ```bash
git add main.py
   ```
5. Finalize o merge com um commit:
   ```bash
git commit
   ```

### 3.6 Ver o histórico de commits

- Mostrar o histórico completo de commits:
  ```bash
git log
  ```

- Ver o histórico em formato compacto e gráfico:
  ```bash
git log --oneline --graph --all
  ```

Esse comando mostra todos os commits de forma resumida, com linhas que indicam como as branches se conectam. É muito útil para ver rapidamente o histórico e entender onde cada branch se juntou.

### 3.7 Restaurar mudanças

Se você fizer alterações que não quer manter, use:

```bash
git restore nome-do-arquivo
```

Esse comando devolve o arquivo ao estado do último commit, desfazendo modificações não adicionadas ao stage.

### 3.8 Resetar o histórico e o stage

O comando `git reset` é usado para voltar no histórico ou tirar arquivos da área de stage.

- Para remover arquivos do stage, mas manter as alterações no seu código:
  ```bash
git reset HEAD nome-do-arquivo
  ```
- Para voltar o histórico localmente ao último commit, mantendo as mudanças no diretório de trabalho:
  ```bash
git reset --soft HEAD~1
  ```
- Para voltar as mudanças completamente e descartar tudo após o commit anterior:
  ```bash
git reset --hard HEAD~1
  ```

Use `git reset` com cuidado: `--hard` apaga mudanças não salvas.

### 3.9 Alterar o último commit

Se você cometeu algo mas quer corrigir a mensagem ou incluir mudanças que esqueceu, use:

```bash
git commit --amend
```

Esse comando altera o último commit em vez de criar um novo.

### 3.9 Atualizar o repositório local

Quando outras pessoas alterarem o projeto ou quando você quiser baixar mudanças do GitHub:

```bash
git pull origin main
```

## 4. Como testar `main.py`

Este projeto tem um arquivo `main.py` com um exemplo simples em Python. Para executar o teste:

1. Abra o terminal na pasta do projeto.
2. Verifique se o Python está instalado com:

```bash
python --version
```

3. Execute o arquivo:

```bash
python main.py
```

Se tudo estiver correto, você verá uma saída parecida com:

```
Iniciando estudo com Git e GitHub
Soma de 10 + 5 = 15
Este arquivo main.py é parte do projeto JornadaDados
```

### O que observar

- A primeira linha mostra que o programa iniciou corretamente.
- A segunda linha mostra o resultado da função `somar`.
- A terceira linha mostra uma mensagem do projeto.

## 5. Comandos principais resumidos

- `git init` : inicia um repositório Git
- `git status` : mostra o estado dos arquivos
- `git add .` : adiciona arquivos para o próximo commit
- `git add <arquivo>` : adiciona um arquivo específico
- `git commit -m "mensagem"` : cria um commit
- `git log` : mostra o histórico de commits
- `git log --oneline --graph --all` : mostra o histórico resumido e em forma de gráfico com todas as branches
- `git restore <arquivo>` : desfaz alterações não adicionadas ao stage
- `git reset` : remove arquivos do stage ou volta o histórico local
- `git commit --amend` : altera o último commit
- `git merge <branch>` : combina outra branch com a branch atual
- `git branch` : lista branches locais
- `git checkout <branch>` : muda para outra branch
- `git checkout -b <branch>` : cria e muda para uma nova branch
- `git remote add origin <URL>` : conecta ao repositório remoto
- `git push -u origin main` : envia para o GitHub
- `git pull origin main` : puxa mudanças do GitHub

## 6. Exercícios

1. Abra o terminal na pasta do projeto.
2. Execute `git status` e veja o que aparece.
3. Modifique `main.py` e execute `git diff` para ver a diferença.
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
7. Crie o repositório no GitHub e faça o primeiro push.

## 6. Dicas importantes

- Use mensagens de commit claras.
- Sempre verifique `git status` antes de commitar.
- Não envie arquivos pessoais ou grandes demais.
- Mantenha o `.gitignore` atualizado.

---

Boa sorte nos estudos! Se precisar, peça ajuda para revisar os comandos e o processo.
