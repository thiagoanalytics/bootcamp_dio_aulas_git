
# DIO | Resumo Git e Github

Repositório para armazenar resumos sobre o git e github do curso Versionamento de Coódigo com Git e Github.


## 📚 Documentação

- [Documentação do Git](https://git-scm.com/doc)
- [Link Github](https://github.com/)
- [Principais comandos](https://blog.somostera.com/desenvolvimento-web/comandos-git)
- [Editor de Markdown](https://readme.so/)
- [Documentação do Markdown](https://gist.github.com/AlexandreQuintela/168e6fa0b6fc5c740c8658c9a5086914)

## 💻 Resumo das Aulas

### Principais comandos

- **Configuração inicial**

Git config - Configurações do Git, como nome de usuário e e-mail.

```
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"

```
- **Criação e Inicialização de Repositórios**

Git init - Inicializa um novo repositório Git em um diretório existente.

```
git init

```
Git clone - Clona um repositório existente a partir de uma URL.

```
git clone https://github.com/usuario/repositorio.git
```

- **Controle de Mudanças**

Git add - Adiciona mudanças no diretório de trabalho ao índice (staging area).

```
git add arquivo.txt
git add .
```
Git commit - Salva as mudanças no repositório com uma mensagem descritiva.
```
git commit -m "Descrição das mudanças"
```
Git status - Mostra o estado atual do repositório, incluindo mudanças não adicionadas ou não comitadas.
```
git status
```
Git diff - Mostra as diferenças entre o diretório de trabalho e o índice ou entre commits.
```
git diff
git diff HEAD
```
- **Branching e Merging**

Git branch - Lista, cria ou deleta branches.
```
git branch                # Lista todas as branches
git branch nova-branch    # Cria uma nova branch
git branch -d antiga-branch # Deleta uma branch
```
Git checkout - Muda para outra branch ou restaura arquivos do repositório.
```
git checkout nome-da-branch
```
Git Merge - Mescla uma branch específica na branch atual.
```
git merge nome-da-branch
```
- **Atualização e Sincronização**

Git pull - Atualiza o repositório local com as últimas mudanças do repositório remoto e mescla automaticamente.
```
git pull origin main
```
Git fetch - Baixa as últimas mudanças do repositório remoto sem mesclar.
```
git fetch origin
```
Git push - Envia as commits locais para o repositório remoto.
```
git push origin main
```
- **Histórico e Navegação**

Git log - Mostra o histórico de commits do repositório
```
git log
```
Git show - Exibe detalhes de um commit específico.
```
git show commit_hash
```
Git reflog - Mostra o histórico de referências, útil para recuperar commits perdidos.
```
git reflog
```
- **Reescrita de Histórico**

Git reset - Move o ponteiro do HEAD para um commit específico, podendo alterar o índice e o diretório de trabalho.
```
git reset --hard commit_hash
```
Git revert - Cria um novo commit que desfaz as mudanças de um commit anterior.
```
git revert commit_hash
```
Git restore - Reverte as alterações feitas em um arquivo específico ou em todos os arquivos no diretório de trabalho para o estado do último commit.
```
git restore arquivo.txt
git restore . #restaura todos os arquivos modificados
```
- **Trabalho com Tags**

Git tag - Cria, lista ou deleta tags, que são referências para pontos específicos no histórico.
```
git tag v1.0
git push origin v1.0
```
- **Stashing**

Git stash - Salva temporariamente mudanças não comitadas para limpar o diretório de trabalho.
```
git stash
git stash apply
```
- **Ajuda**

Git help ou git --help - Exibe ajuda sobre comandos Git.
```
git help commit
git commit --help
```
### Exemplos na prática
Criar um novo repositório e fazer o primeiro commit:
```
mkdir meu-projeto
cd meu-projeto
git init
echo "# Meu Projeto" > README.md
git add README.md
git commit -m "Primeiro commit"
```
Clonar um repositório existente:
```
git clone https://github.com/usuario/repositorio.git
```
Criar e mudar para uma nova branch:
```
git branch nova-feature
git checkout nova-feature
# ou usando um comando único:
git checkout -b nova-feature
```
Mesclar uma branch de volta para a main:
```
git checkout main
git merge nova-feature
```
Enviar mudanças para o repositório remoto:
```
git push origin main
```

## 📤 Envio de atualização para o Github

Para enviar uma atualização ou um novo arquivo ao GitHub, a sequência de comandos Git geralmente segue esta ordem:

- **1 - Verificar o Status Atual do Repositório**

Comando:
```
git status
```
Mostra quais arquivos foram modificados, adicionados ou removidos, e o status da área de staging.
- **2 - Adicionar Arquivos ao Índice (Staging Area)**

Comando:
``` 
git add <arquivo> #Para adicionar um arquivo específico
```
ou 
```
git add . #Para adicionar todos os arquivos modificados
```
Adiciona os arquivos especificados ao índice para serem incluídos no próximo commit.

- **3 - Criar um Commit com uma Mensagem Descritiva**
Comando:
``` 
git commit -m "Descrição do que foi feito"
```
Salva as alterações no histórico de commits localmente com uma mensagem que descreve o que foi feito.

- **4 - Enviar as Alterações ao Repositório Remoto (GitHub)**
```
git push origin <branch>
```
Envia os commits da branch local para a branch correspondente no repositório remoto.


### Ordem Completa dos Comandos:
```
git status                           # Verifica o status atual do repositório
git add .                            # Adiciona todos os arquivos modificados ao staging
git commit -m "Descrição do commit"  # Cria um commit com uma mensagem descritiva
git push origin main                 # Envia as alterações para o GitHub na branch 'main'
```

## ⚙ Trabalhando com Branches

![branches](https://miro.medium.com/v2/resize:fit:1400/1*F_bDsbCj3pRyLefvg2Y6mA.png)

Trabalhar com branches no Git é essencial para gerenciar diferentes versões do seu código, permitindo que você desenvolva funcionalidades, corrija bugs ou experimente novas ideias sem afetar o código principal. Aqui está um guia básico para trabalhar com branches:

**1 - Criar uma nova branch**

Para criar uma nova branch, use o comando:
```
git checkout -b nome-da-branch
```
Isso cria e muda para a nova branch ao mesmo tempo.
```
#Exemplo
git checkout -b feature-nova-funcionalidade
```
**2 - Listar branches**

Para ver todas as branches existentes no seu repositório, use:
```
git branch
```
A branch atual será marcada com um asterisco (*).

**3 - Mudar para uma branch existente**

Para mudar para uma branch que já existe, use:
```
git checkout nome-da-branch
```
```
#Exemplo
git checkout main
```
**4 - Mesclar uma branch em outra**

Depois de terminar o trabalho em uma branch, você pode mesclar as mudanças na branch principal (ou em outra branch):
```
git checkout nome-da-branch-alvo
git merge nome-da-branch-que-será-mesclada
```
```
#Exemplo
git checkout main
git merge feature-nova-funcionalidade
```
**5 - Excluir uma branch**

Após mesclar as mudanças ou se uma branch não for mais necessária, você pode excluí-la:
```
git branch -d nome-da-branch
```
```
#Exemplo
git branch -d feature-nova-funcionalidade
```
Se a branch ainda não tiver sido mesclada e você deseja forçar a exclusão:
```
git branch -D nome-da-branch
```
**6 - Sincronizar branches com o repositório remoto
Para enviar uma nova branch ao repositório remoto:**
```
git push -u origin nome-da-branch
```
Para baixar (fetch) e criar uma branch que existe no repositório remoto:
```
git checkout nome-da-branch
```
**7 - Resolver conflitos durante o merge**

Se houver conflitos entre as branches durante o merge, o Git indicará os arquivos conflitantes, e você precisará resolver manualmente os conflitos:

- Edite os arquivos para resolver os conflitos.
- Após resolver, adicione os arquivos:
```
git add nome-do-arquivo
```
- Finalize o merge:
```
git commit
```