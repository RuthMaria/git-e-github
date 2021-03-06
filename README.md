<h2 align="center"> :information_source: Introdução ao GIT e GITHUB</h2><br>

## :books: Sobre


<p align="justify">
Pequeno resumo dos principais comandos do Git e GitHub. <br><br>
<strong>Git</strong> é um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. (Fonte: wikipédia.)</p>

<p align="justify"><strong>GitHub</strong> é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. (Fonte: wikipédia)</p>

<br>

### **Instalação**
* Baixe a última versão do [Git](https://git-scm.com/)
* Abra o Git Bash no diretório que deseja clonar o repositório remoto do GitHub e, em seguida, clone o repositório desejado

Agora, utilize os comandos a seguir. Os comandos que estiverem entre [] é o dado que precisa ser inserido.

<br>

## :memo: Comandos básicos

<br>

- **Criar repositório local**
```
git init
```
A pasta oculta ".git" contém os gráficos de commits do projeto.

<br>

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

<br>

- **Verificar qual o repositório remote que está linkado**
```
git remote -v
```

<br>

- **Clonar o repositório do GitHub na máquina local**
```
git clone [url do repositório do github]
```

<br>

- **Adicionar arquivos do repositório local na staged area (uma área intermediária antes de dar um commit)**
```
git add .                            // adiciona todos os arquivos locais
git add [nome_do_arquivo.extensão]  // adiciona um determinado arquivo
git add *.[extensão]               // adiciona todos os arquivos de uma determinada extensão 
```

<br>

- **Remover um arquivo da staged area (depois de ter dado o comando 'git add .')**
```
git reset HEAD [nome_do_arquivo.extensão]
git restore --staged [nome_do_arquivo.extensão]
```

<br>

- **Marcar o atual estado do repositório local (comitar os arquivos)**
```
git commit -m "mensagem do commit"    
git commit -am "mensagem do commit"          // dá um add e um commit ao mesmo tempo
git commit --amend -m "mensagem do commit"  // edita o último commit feito
```

<br>

- **Remover um commit específico**
```
git reset --hard [codigo_do_commit]  // apaga todas as modificações que esse commit fez
```

<br>

- **Enviar o estado atual da pasta local para o servidor do GitHub**
```
git push
```

<br>

- **Baixar atualizações do repositório do GitHub para o repositório local**
```
git pull
```

<br>

- **Mostrar as modificações feitas em cada arquivo**
```
git diff            // mostra as modificações feitas nos arquivos do repositório local
git diff --staged  // mostra as modificações feitas nos arquivos da staged area, ou seja, após já ter dado o 'git add .'
```

<br>

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

<br>

- **Verificar a situação atual do repositório local**
```
git status     // mostra o que tem pra comitar, arquivos novos, deletados, etc
```

<br>

- **Criar um arquivo**
```
touch [nome_do_arquivo.extensão]
```

<br>

- **Criar uma  pasta**
```
mkdir [nome da pasta]
```

<br>

- **Descartar as mudanças realizadas em um arquivo**
```
git checkout -- [nome_do_arquivo.extensão]
```

<br>

- **Remover um arquivo**
```
git rm [ome_do_arquivo.extensão]
```

<br>

- **Voltar para uma determinada versão do projeto**
```
git checkout [código do commit]    // olha o código do commit usando o 'git log --oneline'
git checkout master                // volta novamente para a versão atual, a master
```

<br>

- **BRANCHES**

São ramificações dentro do controle de versão. O Branch permite que se trabalhe com várias ramificações e segmentações diferentes de um sistema, onde um commit de uma ramificação não altera a outra ramificação. Permite trabalhar com várias versões do sistema, assim pode-se fazer vários testes e mudanças no código que não alterará o projeto original.
  
<br>

**Criar um branch**
````
git branch [nome do branch]
````

<br>

**Escolher o branch que será utilizado**
````
git checkout  [nome do branch]
````

<br>

**Criar um branch e o escolher para ser usado (substitui os dois comandos anteriores)**
````
git checkout -b [nome do branch]
````

<br>

**Listar todos os branches criados**
````
git branch
````

<br>

**Faz a junção/merge do branch informado ao branch ativo no momento**
````
git merge [nome do branch]
````
No momento da integração, haverá conflitos entre a versão teste e a versão master, o merge não será realizado até os conflitos terem sido resolvidos. Que conflitos são esses? Dados diferentes no arquivo da versão teste e da versão master. No arquivo do projeto serão criados linhas com o `<<<<<<<<< HEAD`, indicando onde está havendo o conflito. 

<br>

**Remover o branch do repositório local**
````
git push origin :[nome do branch]
````

<br>

**Remover o branch do repositório do GitHub**
````
git branch -d [nome do branch]
````

<br>

**Levar as modificações do master para um branch específico**
````
git rebase master 
````
Não necessariamente o master, pode ser outro branch criado.

<br>

- **TAGS**

É uma etiqueta, um ponto de atalho para um determinado status do sistema. Geralmente os desenvolvedores criam tags para fazer marcações nas versões diferentes de um sistema. Tipo: versão 1.0, versão 1.1, versão 1.2... Assim é possível baixar uma determinada versão de um projeto.

<br>

**Mostrar todas as tags do projeto**
```
git tag 
```

<br>

**Criar uma tag**
```
git tag -a [nome da tag] -m "mensagem da tag" 
```

<br>

**Criar uma tag de um commit já feito no repositório**
```
git tag -a [nome da tag] [código do commit] -m "mensagem da tag" 
```

<br>

**Mostrar os detalhes da tag informada**
```
git show [nome da tag]
```

<br>

**O repositório local volta para a versão da tag associada**
```
git checkout [nome da tag] 
```

<br>

**Remover uma tag já criada**
```
git tag -d [nome da tag] 
```

<br>

- **Fork e pull request**

O `fork` faz a clonagem de um repositório de terceiro diretamente para o seu GitHub. Assim, as alterações realizadas no projeto clonado não afetará o projeto original. Caso deseje alterar o projeto original é necessário dar um `pull request`, assim as alterações serão sinalizadas ao dono do projeto original, que avaliará se aceita ou não as mudanças sugeridas. O `pull request` é uma ótima forma de contribuir com os projetos da comunidade.


<br>

- **gitignore**

Para o git ignorar determinados arquivos da pasta do repositório, e estes arquivos não serem comitados, é preciso criar um arquivo txt sem nome e com a extensão .gitignore na raiz do projeto. E dentro do arquivo .gitignore colocar a lista de arquivos que não serão comitados, onde cada arquivo deve estar em uma linha.

Caso queira ignorar um arquivo que já foi comitado anteriormente, apenas colocá-lo no arquivo .gitignore não resolverá, é necessário limpar a staged area (o cache local), para isso use o comando:
```
git rm -r --cached [nome arquivo]
```
Em seguida, adicione os arquivos que entrará no versionamento `git add .` e comite as atualizações `git commit -m "mensagem do commit"`. 
