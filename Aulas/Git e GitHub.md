<span id="header"/>
<!-- ◀ -->
<a href="https://github.com/lucasdzuc/bootcamp-avanade-dio-projetos">Voltar</a>

<div align="center">

# Git & GitHub
> Foi aprendido os conceitos base do funcionamento da ferramenta Git e do repositório remoto GitHub  
> ⏳ Duração: 6h

</div>

<span id="summary">

# Sumário
> - **<a href="#topic1">Conceitos</a>**
> > - **<a href="#subtopic1">Git & GitHub</a>**
> > - **<a href="#subtopic2">GUI x CLI</a>**
> > - **<a href="#subtopic3">SHA1</a>** 
> > - **<a href="#subtopic4">Tipos de armazenamento do Git</a>**
> > - **<a href="#subtopic5">Chave SSH</a>**
> - **<a href="#topic2">Comandos GitBash</a>**
>
> - **<a href="#footer">Rodapé</a>**


<br>

<span id="topic1"/>

## Conceitos
> <a href="#summary">#retornar ao sumário</a>

> ### Git <span id="subtopic1"/>
> É um software criado por Linus Torvalds (mesmo criador e desenvolvedor do sistema operacional Linux) e sua equipe de desenvolvedores, que baseia-se em um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, podendo ser utilizado para registrar o histórico de edições de qualquer tipo de arquivo.
>
> ### GitHub
> É um repositório remoto onde você pode armazenar seus repositórios, funcionando também como uma grande Rede Social para divulgar seus projetos, servindo como um portifólio para recrutadores verem.
>
> #
>
> ### GUI x CLI <span id="subtopic2"/>
> - **Graphic User Interface** - São programas que disponibilizam de uma interface gráfica permitindo você interagir com o software.
> - **Command Line Interface** - São programas que disponibilizam apenas de linhas de comando para você interagir com o software (ex: Terminal do Windows, Linus, MacOS, etc.).
>
> O Git possui os dois tipos de interfaces, sendo mais comum utilizado o tipo de interface **CLI**.
>
> #
>
> ### SHA1 <span id="subtopic3"/>
> **Secure Hash Algorithm**, é um algoritimo de encripitação Hash, onde ele utilizará da encriptação hash para embaralhar de uma forma específica os dados presentes do objeto, com o intuito de proteger as informações contidas no arquivo criptografado.
> A encriptação irá gerar uma chave de 40 digítos única, que servirá como o identificador daquele arquivo.
> 
> ![image](https://user-images.githubusercontent.com/60985347/144118860-f4d8f448-a221-47c3-8664-1a8aa502a0ed.png)
>
> **GitBash** <br>
> `$ Openssl sha1 file.extension` - gerá uma chave criptografada do arquivo informado
>
> #
>
> ### Tipos de armazenamento do Git <span id="subtopic4"/>
> Existem 3 níveis de armazenamento no Git, sendo eles Blob, Tree e Commit
>
> - **Blob** -
> É uma função que contém metadados do Git, armazenando dentro dele o tipo do objeto, o tamanho dele, o conteúdo dele, etc., tento um **sha1** próprio como códificação. Ilustrando seria como a representação do conteúdo de um arquivo.
>
> - **Tree** -
> Armazena os metadados tanto de blobs como de outras trees, também possue seu **sha1** próprio que é alterado quando algum objeto dentro dela é mudado, seja um blob ou outra tree, ela armazena o sha1 dos blobs, de outras trees, incluindo o nome do arquivo/objeto referente à elas. Ilustrando seria como a representação das pastas e arquivos de um diretório.
>  
> - **Commit** -
> Ele é responsável por fazer a junção dos metadados, das trees, blobs, etc., contendo também a informação **parent** que remete ao último commit registrado, a informação **autor** remetendo á quem fez esse commit, possuí uma timestamp e também um próprio sha1 de identificador que é alterado caso qualquer tree ou blob dentro dele seja alterado.
> 
> ![image](https://user-images.githubusercontent.com/60985347/144123692-edf8b23a-6a3c-4c3d-b9c7-969d037dd40e.png)
>
> #
>
> ### Chave SSH (Secure Shell) <span id="subtopic5"/>
> É um protocolo que permite a conexão com servidores remotos, de forma criptografada e mais segura, usando um par de **chaves RSA**.
> > #
> > **Chave RSA (Rivest-Shamir-Adleman)** - É um dos primeiros sistemas de criptografia de chave pública e é amplamente utilizado para transmissão segura de dados. Neste sistema de criptografia, a chave de encriptação é pública e é diferente da chave de decriptação que é secreta (privada).
> > #
>
> Podemos criar uma chave SSH pelo GitBash pelo comando:
> `$ ssh-keygen -t ed25519 -C leonardo.delgadosp2014@gmail.com` - Gerará dois arquivos contendo uma chave pública e uma privada, dentro do diretório `.ssh`.
> > #
> > **Flags Usadas:**
> > - `-t <dsa | ecdsa | ecdsa-sk | ed25519 | ed25519-sk | rsa>` - tipo de códificação da chave ssh.
> > - `-C comment` - adiciona um comentário para identificação da chave, foi usado o meu email nesse exemplo.
> > #
>
> Após isso, podemos entrar dentro da nossa conta do GitHub em configurações na parte de SSH e registar uma chave lá, a chave que registramos é a chave pública (arquivo com a extensão ".pub")
> 
> Só precisamos inicializar um agente ssh, que funcionará como interpretador do código que recebermos, para isso no GitBash dentro da pasta .ssh: <br>
> `$ eval $(ssh-agent -s)` - cria um processo de um agente ssh.
> 
> Por fim só basta adicionar a nossa chave privada nesse agente: <br>
> `# ssh-add file`
> 
> Agora quando enviarmos qualquer arquivo para o GitHub atraves do push ou recebermos pelo pull, não será solicitado uma confirmação de senha para nossa conta, pois o ssh já está autenticando nossa máquina, além de termos uma proteção de dados maior.
> 
> #


<span id="topic2"/>

## Comandos GitBash
> <a href="#summary">#retornar ao sumário</a>
  
<table>
  <tr>
    <th align="left">Comando</th>
    <th align="left">Descrição</th>
  </tr>
  <tr>
    <td/>
    <td/>
  </tr>
  <!-- linha 1-->
  <tr>
    <th align="left">$ clear</th>
    <td>limpa o terminal</td>
  </tr>
  <tr>
  <!-- linha 2-->
    <th align="left">$ ls</th>
    <td>lista todos diretórios e arquivos do caminho atual</td>
  </tr>
  <!-- linha 3-->
    <th align="left">$ pwd</th>
    <td>mostra o caminho completo atual</td>
  </tr>
  <!-- linha 4-->
    <th align="left">$ cat [file] </th>
    <td>Mostra o conteúdo do arquivo informado</td>
  </tr>
  <!-- linha 5-->
    <th align="left">$ git config --global user.name [name]</th>
    <td>Seta em âmbito global o nome do autor dos commits realizados na máquina</td>
  </tr>
  <!-- linha 6-->
    <th align="left">$ git config --global user.email [email]</th>
    <td>Seta em âmbito global o email do autor dos commits realizados na máquina</td>
  </tr>
  <!-- linha 7-->
    <th align="left">$ git config --list</th>
    <td>Mostra todos os valores configurados do git</td>
  </tr>
  <!-- linha 8-->
    <th align="left">$ git init</th>
    <td>Inicializa o git no diretório atual</td>
  </tr>
  <!-- linha 9-->
    <th align="left">$ git status</th>
    <td>Mostra se há modificações, deleções ou adições de arquivos no repositório</td>
  </tr>
  <!-- linha 10-->
    <th align="left">$ git add [file]</th>
    <td>Adiciona arquivos na fila de espera para serem comitados</td>
  </tr>
  <!-- linha 11-->
    <th align="left">$ git commit -m "desc"</th>
    <td>Comita os arquivos na fila de espera do "git add", e informa uma mensagem</td>
  </tr>
  <!-- linha 12-->
    <th align="left">$ git branch -M main</th>
    <td>Altera o nome atual da branch principal para main (padrão é master)</td>
  </tr>
  <!-- linha 13-->
    <th align="left">$ git remote add origin [url]</th>
    <td>Adiciona uma origem de repositório remoto</td>
  </tr>
  <!-- linha 14-->
    <th align="left">$ git push -u origin main</th>
    <td>Empurra todas as comissões do seu repositório local para o remoto definido por "origin" na branch "main" ("-u" faz o upstream, só é necessário usar essa tag uma vez ao usar push)</td>
  </tr>
  <!-- linha 14-->
    <th align="left">$ git pull</th>
    <td>Puxa todas as comissões feitas pelo repositório remoto para o local</td>
  </tr>
  <!-- linha 13-->
    <th align="left">$ git clone [url]</th>
    <td>Clona um repositório do GitHub</td>
  </tr>
</table>

<br>
<br>
<br>
<br>

<span id="footer"/>
  
> <div align="center"><a href="#header">Voltar ao topo</a></div>
  