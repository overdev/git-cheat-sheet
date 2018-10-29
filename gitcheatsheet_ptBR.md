# FOLHA DE DICAS GIT

Git é o sistema de controle de versionamento distribuido gratuíto e código aberto que é responsável por tudo relacionado ao GitHub que acontece localmente no seu computador. Esta lista de dicas (ou cola) contém os mais importantes e usados comandos Git para fácil referência.

## INSTALAÇÃO & GUIs

Com instaladores Git específicos para cada plataforma, GitHub também disponibiliza a facilidade de estar sempre atualizado com as últimas versões da ferramenta de linha de comando enquanto provê uma interface gráfica para interação dia-a-dia, revisão, e sincronização de repositório.

[GitHub para Windows](https://windows.github.com)

[GitHub para Mac](https://mac.github.com)

[Git para Todas as Platformas](http://git-scm.com)

## CONFIGURAÇÃO

Configurando informação do usuário em todos os repositórios locais.

```
git config --global user.name "[firstname lastname]"
```
atribui um nome que é identificável como credencial durante a revisão do histórico.

```
git config --global user.email "[valid-email]"
```
atribui um endereço de email que será associado a cada marcador de histórico.

```
git config --global color.ui auto
```
configura a coloração do prompt de comando do Git para revisão facilitada.


## CONFIGURAÇÃO & INICIALIZAÇÃO

Configurando informação de usuário, inicialização e clonando repositórios.

```
git init
```
Inicializa um diretório existente como um reposório Git.

```
git clone [url]
```
Copia um repositório inteiro de um local hospedado via URL.


## PREPARAÇÃO (STAGE) & PRÉVIA (SNAPSHOT)

Trabalhando com prévias e com a área de preparação Git

```
git status
```
exibe arquivos modificados no diretório de trabalho, preparação para seu próximo commit.

```
git add [file]
```
adiciona um arquivo como está agora para seu próximo commit (preparação).

```
git reset [file]
```
desprepara um arquivo enquanto mantém as mudanças no diretório de trabalho.

```
git diff
```
diferenças do que foi modificado mas não está preparado.

```
git diff --staged
```
diferenças do que foi preparado mas não recebeu commit anda.

```
git commit -m "[descriptive message]"
```
aplica o conteúdo preparado como uma nova prévia commit.


## RAMIFICAÇÃO (BRANCH) & INTEGRAÇÃO (MERGE)

Isolando o trabalho em ramos, alterando contexto, e integrando mudanças.

```
git branch
```
lista seus ramos (branches). um * aparecerá próximo ao ramo atualmente ativo.

```
git branch [branch-name]
```
cria um novo ramo no commit atual

```
git checkout
```
troca para outro ramo (branch) e sai para o diretório de trabalho atual

```
git merge [branch]
```
merge o ramo histórico do especificado ao atual.

```
git log
```
exibe todos os commits no histórico do ramo atual.


## INSPEÇÃO & COMPARAÇÃO

Examinando logs, diferenças and informação de objetos.

```
git log
```
exibe todos os commits no histórico do ramo atual.

```
git log branchB..branchA
```
exibe os commits no branchA que não estão no branchB

```
git log --follow [file]
```
exibe os commits que alteraram file, mesmo entre renomeações.

```
git diff branchB...branchA
```
exibe as diferenças do que está em branchA mas não em branchB.

```
git show [SHA]
```
exibe qualquer objeto no Git em formato legível.


## RASTREANDO MUDANÇAS DE CAMINHO

Versionando remoções e movimentações de arquivo.

```
git rm [file]
```
deleta o arquivo do projeto e prepara a remoção para o commit.

```
git mv [existing-path] [new-path]
```
altera um caminho de arquivo existente e prepara (stage) a movimentação.

```
git log --stat -M
```
exibe todos os logs de commits com indicações de caminhos que foram movidos.


## IGNORANDO PADRÕES

Prevenindo preparação ou commit de arquivos não intencionais.

```
logs/
*.notes
pattern*/
```
salve um arquivo com os padrões desejados como .gitignore com entradas de combinação diretas ou indiretas.

```
git config --global core.excludesfile [file]
```
padrões a serem ignorados por todos os repositórios locais.


## COMPARTILHAMENTO E ATUALIZAÇÃO

Recuperando atualizações de outro repositório e atualizando repositórios locais.

```
git remote add [alias] [url]
```
adiciona um URL git como um alias (pseudônimo).

```
git fetch [alias]
```
busca todos os ramos (branches) do Git remoto.

```
git merge [alias]/[branch]
```
merge um ramo remoto ao ramo atual para atualizá-lo.

```
git push [alias] [branch]
```
transmite commits do ramo local para o ramo do repositório remoto.

```
git pull
```
busca e merge qualquer commit do ramo remoto rastreado.


## REESCREVENDO HISTÓRICO

Reescrevendo ramos, atualizando commits e limpando o histórico

```
git rebase [branch]
```
aplica quaisquer commits do ramo atual que esteja à frente do especificado.

```
git reset --hard [commit]
```
limpa a area de preparação, reescreve a árvore de trabalho a partir do commit especificado.


## COMMITS TEMPORÁRIOS

Armazenando temporariamente arquivos modificados, rastreados com o objetivo de alterar ramos (branches).

```
git stash
```
salva modificações e preparações.

```
git stash list
```
lista em ordem de pilha das mudanças acumuladas no stash.

```
git stash pop
```
escreve o trabalho a partir do topo da pilha stash.

```
git stash drop
```
discarta as mudanças a partir do top da pilha stash.
