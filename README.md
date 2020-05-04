## INTRODUÇÃO AO GIT

**Git** é um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. (Fonte: wikipédia.)

**GitHub** é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. (Fonte: wikipédia)

### **Instalação**
1. Baixe a última versão do git
2. Abra o Git Bash no diretório que deseja clonar o repositório remoto do GitHub e, em seguida, clone o repositório do GitHub

Agora, utilize os comandos a seguir. Os comandos que estiverem entre [] é o dado que precisa ser inserido.


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

- **Remover um arquivo da staged area (depois de ter dado o comando 'git add .')**
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
git diff --staged  // mostra as modificações feitas nos arquivos da staged area, ou seja, após já ter dado o 'git add .'
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

São ramificações dentro do controle de versão. O Branch permite que se trabalhe com várias ramificações e segmentações diferentes de um sistema, onde um commit de uma ramificação não altera a outra ramificação. Permite trabalhar com várias versões do sistema, assim pode-se fazer vários testes e mudanças no código que não alterará o projeto original.
  
**Criar um branch**
````
git branch [nome do branch]
````

**Escolher o branch que será utilizado**
````
git checkout  [nome do branch]
````

**criar um branch e o escolher para ser usado (substitui os dois comandos anteriores)**
````
git checkout -b [nome do branch]
````

**Listar todos os branches criados**
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

- **TAGS**

É uma etiqueta, um ponto de atalho para um determinado status do sistema. Geralmente os desenvolvedores criam tags para fazer marcações nas versões diferentes de um sistema. Tipo: versão 1.0, versão 1.1, versão 1.2... Assim é possível baixar uma determinada versão de um projeto.

**Mostrar todas as tags do projeto**
```
git tag 
```

**Criar uma tag**
```
git tag -a [nome da tag] -m "mensagem da tag" 
```

**Criar uma tag de um commit já feito no repositório**
```
git tag -a [nome da tag] [código do commit] -m "mensagem da tag" 
```

**Mostrar os detalhes da tag informada**
```
git show [nome da tag]
```

**O repositório local volta para a versão da tag associada**
```
git checkout [nome da tag] 
```

**Remover uma tag já criada**
```
git tag -d [nome da tag] 
```

- **Fork e pull request**

O `fork` faz a clonagem de um repositório de terceiro diretamente para o seu GitHub. Assim, as alterações realizadas no projeto clonado não afetará o projeto original. Caso deseje alterar o projeto original é necessário dar um `pull request`, assim as alterações serão sinalizadas ao dono do projeto original, que avaliará se aceita ou não as mudanças sugeridas. O `pull request` é uma ótima forma de contribuir com os projetos da comunidade.


- **gitignore**

Para o git ignorar determinados arquivos da pasta do repositório, e estes arquivos não serem comitados, é preciso criar um arquivo txt sem nome e com a extensão .gitignore na raiz do projeto. E dentro do arquivo .gitignore colocar a lista de arquivos que não serão comitados, onde cada arquivo deve estar em uma linha.

Caso queira ignorar um arquivo que já foi comitado anteriormente, apenas colocá-lo no arquivo .gitignore não resolverá, é necessário limpar a staged area (o cache local), para isso use o comando:
```
git rm -r --cached [nome arquivo]
```
Em seguida, adicione os arquivos que entrará no versionamento `git add .` e comite as atualizações `git commit -m "mensagem do commit"`. 
