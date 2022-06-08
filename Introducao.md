# **Introdução ao Git e ao GitHub**

## \***\*O que é o Git\*\***

O Git é o sistema *opensource* de controle de versão mais popular da internet. Ele é usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo.

## **Porque preciso dos comandos Git**

É muito comum que empresas tenham mais de um dev trabalhando paralelamente no mesmo projeto. Então, em primeiro lugar, sistemas como o Git existem para o código não virar uma bagunça. Pode haver também a necessidade de voltar para uma **versão** anterior, por uma série de motivos, e ter esse **controle** dá muito mais **segurança** pra quem está trabalhando.

## **Principais comandos Git**

### **Git init**

Para começar um projeto que ainda não seja um repositório (ou repo), o Git Init costuma ser o primeiro comando que você vai usar, pois vai precisar de um subdiretório .git na raiz do seu projeto. Esse comando cria um repositório vazio ou transforma uma pasta que você já tem, e que não está com controle de versão, em um repositório.

### **Git clone**

O Git clone é um comando para baixar o código-fonte existente de um repositório remoto (como o Github, por exemplo).

```markdown
git clone https://url-do-repositorio
```

Quando você clonar um repositório, o código é copiado para a o seu computador e continua linkado ao original, como foi explicado lá na descrição do que é um sistema distribuído.

Se você quiser desvincular a sua cópia do original, rode o comando abaixo:

```markdown
git remote rm origin
```

### **Git branch**

Com branches (ou ramificações), vários desenvolvedores podem trabalhar paralelamente no mesmo projeto. Assim, cada um pode codar a sua parte sem se atrapalharem.

Criando uma nova branch:

```bash
git branch nome-da-branch
```

Para upar a nova branch para o repositório remoto, você precisa usar o seguinte comando:

```bash
git push -u remote nome-da-branch

```

Para ver as ramificações:

```bash
git branch
```

ou

```bash
git branch --list
```

Deletando uma branch:

```bash
git branch -d nome-da-branch
```

### **Git checkout**

Este é um dos comandos Git mais usados. Para trabalhar em uma branch, primeiro você precisa mudar para ela. Não ir para a branch que você acabou de criar e na qual quer trabalhar é um erro bastante comum no começo.

```
git checkout nome-da-ramificação
```

### **Git status**

O comando status do Git fornece algumas informações sobre a branch em que você estiver no momento, como seu nome, se ela está atualizada em relação à master e quais arquivos foram alterados.

```
git status
```

### **Git add**

Quando criamos, modificamos ou excluímos um arquivo, essas alterações ocorrerão em nosso ambiente local e não serão incluídas no próximo commit (a menos que alteremos as configurações).

Precisamos usar o comando git add para incluir as alterações de um arquivo em nosso próximo commit.

```
git add arquivo
```

Para adicionar, de uma vez, todos os arquivos modificados:

```
git add -A
```

### **Git commit**

Este comando é como definir um ponto de verificação no processo de desenvolvimento, para o qual você pode voltar mais tarde, se necessário.

```
git commit -m "mensagem explicando a mudança no código"
```

### **Git push**

Após confirmar as alterações, a próxima coisa que você deseja fazer é enviar as alterações para o servidor remoto.

```
git push remote nome-do-branch
```

### **Git pull**

O comando git pull é usado para obter atualizações do repositório remoto. O comando de pull depende do referencial de onde ele foi feito, ou seja, um git pull feito da sua máquina vai puxar informações do repositório original para ela.

```
git pull remote
```

### **Git revert**

Existem várias maneiras de desfazer nossas alterações local ou remotamente (dependendo da necessidade), mas devemos usar esses comandos com cuidado para evitar problemas.

Uma maneira segura de desfazer os commits é usando git revert.

```
git revert número do hash
```

O número do hash pode ser conseguido pelo comando:

```
git log -- oneline
```

### **Git merge**

Quando você conclui o desenvolvimento em sua branch e tudo funciona bem, sem conflitos, a etapa final é mesclar as branches, isso é feito com o comando git merge.

Como falamos no tópico sobre git pull, esse comando vai mesclar, no seu repositório local, todas as alterações feitas.

```
git merge nome-da-branch
```

**Fonte: Geek Hunter.**

### Navegação

- **git clone <url-do-repositório>:** Clona um repositório da nuvem para seu PC.
- **git status:** fornece informações sobre a branch que está na sua máquina, se está atualizada em relação a master, quais arquivos foram alterados, como é o nome.
- **git commit -m "Mensagem explicando mudanças":** Cria uma mensagem expecificando as alterações realizadas, fazendo assim um histórico das versões.
- **git push:** Envia e salva sua branch local na nuvem.
- **git pull:** Atualiza a branch local de acordo com o que está na nuvem.
- **git add:** inclui alterações de arquivos no seu próximo commit. Para adicionar todos arquivos alterados, você pode digitar git add -A ou git add.
- **git fetch:** Atualiza o repositório local com as branches que estão na nuvem.
- **git branch:** Lista todas as branches do seu repositório local.
- **git chekout -b <nome-da-branch>:** Cria uma nova branch a partir da branch atual e já muda para ela.
- **git checkout <nome-da-branch>:** Muda da branch atual para a branch com o nome especificado. Usado para alternar entre branches.

<br/>

---

## **Entendendo como o Git funciona**

### Topicos fundamentais para entender o funcionamento

**\*SHA1**:\*

A sigla SHA significa secure Hash algorithm, é um conjuto de funções hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos EUA).

<aside>
💡 *A encriptação gera conjunto de characteres identificador de 40 dígitos.*

</aside>

### Objetos internos:

**BLOBS :**

Os conteúdos ficam guardados dentro do objeto BLOB. Contém meta-dados do Git.

**TREES :**

TREES armazenam as BLOBS que por sua vez tem o seu SHA 1. Os diretórios das TREES podem apontar tanto para os BLOBS quanto para ela mesma. As TRESS também possuem SHA 1.

**COMMITS :**

COMMITS junta todos os objetos, BLOBS e TREES.
Os COMMITS também existem um carimbo de tempo, registrando a data e horário da criação.

Caso você altere um SHA 1 dentro de uma BLOBS, que estava ligada a uma TREES, o SHA 1 modifica a BLOBS e a TREES fornecendo um novo código criptografado.

E caso esta mesma rede estivesse interligada a uma COMMITS, o SHA 1 seria modificado no COMMITS, TREES e BLOBS.

**Comandos para o Windows:**

| Comando   | O que faz                                   |
| --------- | ------------------------------------------- |
| CD        | navegar/voltar entre pastas/arquivos        |
| DIR       | listar/mostrar pastas e arquivos            |
| MKDIR     | criar pasta                                 |
| RMDIR     | deletar repositorio/pasta e arquivos        |
| DEL       | deletar arquivo                             |
| CLS       | Limpa o terminal windows                    |
| Tecla TAB | Autocomplete                                |
| ECHO      | Replicação/Representação de setença/arquivo |

<br/>
<br/>

### Chaves SSH e Tokens

_SSH_

- ssh-keygen -t ed25519 -c (email.com)

<br/>

## Primeiros comandos com GIT

---

- git init → inicia um repositorio
- ls -a → flag -a: mostra pasta oculta
- git config —global [user.email](http://user.email) “seu email.com”
- git config —global [user.name](http://user.name) (Nome sem parentes)
- markdown → estrutura de marcação, .md
  - \** **Negrito**, \_\_*italico\*
  ##. tamanho do markdown
- git add
- git commit -m “mensagem inicial (commit inicial)”

## Ciclo de vida dos arquivos no Git

- git status
- mv → move alguma pasta ou arquivo
- git add \* → mostra quais arquivos sofreram modificações para dar commit. (adiciona arquivo para “STAGING AREA”)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f0149ffd-c683-43a3-8a71-c55fc474cfaf/Untitled.png)

## Introdução ao GitHub

- git remote add origin (aqui vai o link do repositorio criado pelo HitHub)
- origin?
- git remote -v
- git push origin master

## Resolvendo conflitos

- git push —help
- git pull origin master
  - CONFLIT (content): apresenta o erro aqui
-

_Links complementares:_

**[Como usar Git e Git Hub part 1:](https://www.youtube.com/watch?v=DqTITcMq68k)**

**[Como usar Git e Git Hub part 2:](https://www.youtube.com/watch?v=UBAX-13g8OM)**

[GIT - Primeiros passos.md](https://gist.github.com/adammacias/bb358a90a4f4cea50b41)
