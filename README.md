## INTRODUÇÃO AO GIT

**Git** é um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. (Fonte: wikipédia.)

**GitHub** é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. (Fonte: wikipédia)

### **Instalação**
1. Baixe a última versão do git
2. Abra o Git Bash no repositório do seu projeto local ou clone um projeto

Agora, já pode utilizar os comandos a seguir. Os comandos que estiverem entre [] é o dado que precisa ser inserido.


## Comandos básicos

- **Criar repositório local**
```
git init
```
A pasta oculta ".git" contém os gráficos de commits do projeto.


- **Configurar o usuário para usar o GitHub**
```
git config --global user.email "e-mail da conta do GitHub"
git config --global user.name "nome de usuário da conta do GitHub"
```

Verificando o usuário configurado
```
git config --global user.email 
git config --global user.name
```

- **Verificar qual o repositório remote que está linkado**
```
git remote -v
```

- **Clonar o repositório do GitHub na máquina local**
```
git clone [url do repositório do github]
```

- **Adicionar arquivos do repositório local na staged area (uma área intermediária antes de dar um commit)**
```
git add .                            // adiciona todos os arquivos locais
git add [nome_do_arquivo.extensão]  // adiciona um determinado arquivo
git add *.[extensão]               // adiciona todos os arquivos de uma determinada extensão 
```

- **Remover um arquivo da staged area (depois de ter dado o comando 'git add. ')**
```
git reset HEAD [nome_do_arquivo.extensão]
git restore --staged [nome_do_arquivo.extensão]
```

- **Marcar o atual estado do repositório local (comitar os arquivos)**
```
git commit -m "mensagem do commit"    
git commit -am "mensagem do commit"          // dá um add e um commit ao mesmo tempo
git commit --amend -m "mensagem do commit"  // edita o último commit feito
```

- **Remover um commit especifico**
```
git reset --hard [codigo_do_commit]  // apaga todas as modificações que esse commit fez
```

- **Enviar o estado atual da pasta local para o servidor do GitHub**
```
git push
```

- **Baixar atualizações do repositório do GitHub para o repositório local**
```
git pull
```

- **Mostrar as modificações feitas em cada arquivo**
```
git diff            // mostra as modificações feitas nos arquivos do repositório local
git diff --staged  // mostra as modificações feitas nos arquivos da staged area, ou seja, após já ter dado o 'git add.'
```

- **Mostrar todos os commits do projeto**
```
git log                                // mostra os commits de forma mais detalhada
git shortlog                          // mostra apenas as mensagens de cada commits
git log -p                           // junção do git log mais o git diff, apertar a letra “q” para voltar a linha de comando
git log -p -[quantidade de commits] // mostra uma determinada quantidade de commits
git log --pretty=oneline           // mostra o código completo de cada commit e a mensagem
git log --oneline                 // mostra os 7 primeiros dígitos do código de cada commit e a mensagem
git log --oneline --graph --all  // mostra o gráfico de commits simplificado
git log --graph --all           // mostra o gráfico de commits detalhado, apertar a letra “q” para voltar a linha de comando
```

- **Verificar a situação atual do repositório local**
```
git status     // mostra o que tem pra comitar, arquivos novos, deletados, etc
```

- **Criar um arquivo**
```
touch [nome_do_arquivo.extensão]
```

- **Criar uma  pasta**
```
mkdir [nome da pasta]
```

- **Descartar as mudanças realizadas em um arquivo**
```
git checkout -- [nome_do_arquivo.extensão]
```

- **Remover um arquivo**
```
git rm [ome_do_arquivo.extensão]
```

- **Voltar para uma determinada versão do projeto**
```
git checkout [código do commit]    // olha o código do commit usando o 'git log --oneline'
git checkout master                // volta novamente para a versão atual, a master
```

- **BRANCHES**

São ramificações dentro do controle de versão. O Branch permite que se trabalhe com várias ramificações e segmentações diferentes de um sistema, onde um commit de uma ramificação não altera a outra ramificação. Permite trabalhar com várias versões do sistema, assim pode-se fazer vários teste e mudançãs no código que não interferirá no projeto original.
  
**Cria um novo branch**
````
git branch [nome do branch]
````

**Escolhe o branch que será usado no momento**
````
git checkout  [nome do branch]
````

**cria um novo branch e já o escolhe para ser usado, substitui os dois comandos de cima**
````
git checkout -b [nome do branch]
````

**Lista todos os branches criados**
````
git branch
````

**Faz a junção/merge do branch informado ao branch ativo no momento**
````
git merge [nome do branch]
````
No momento da integração, haverá conflitos entre a versão teste e a versão master, o merge não será realizado até os conflitos terem sido resolvidos. Que conflitos são esses? Dados diferentes no arquivo da versão teste e da versão master. No arquivo do projeto serão criados linhas com o `<<<<<<<<< HEAD`, indicando onde está havendo o conflito. 

**Remove o branch do repositório local**
````
git push origin :[nome do branch]
````

**Remove o branch do repositório do GitHub**
````
git branch -d [nome do branch]
````

**Leva as modificações do master para um branch específico**
````
git rebase master 
````
Não necessariamente o master, pode ser outro branch criado.

- ****
```
```

