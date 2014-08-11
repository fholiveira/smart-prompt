Smart prompt
============

Bash script que cria um prompt mais esperto. Ele informa:

* O usuario e máquina atuais
* Se está em um virtualenv do Python e qual o nome do mesmo
* O diretório atual, usando a sintaxe reduzida do vim
* Informações sobre o repositório git, caso o diretório seja um
* Se o usuário tem permissões de root

#### Informações do repositório git
* o nome da branch atual
* se está fazendo rebase
* a quantidade de arquivos na staging area, modificados e untracked
* a quantidade de arquivos em conflito
* o estado do repo em relação a origin

* utiliza cores para indicar o estado do repo
  - *verde* quando não há modificações
  - *vermelho* quando arquivos foram modificados
  - *amarelo* quando todos os arquivos modificados estão na staging area
  - *azul* quando há somente arquivos untracked

### Para usar

1. Verifique se que a pasta "~/.bin/" está no seu PATH com o comando

  ```bash
  echo $PATH | grep -e "$HOME/.bin" -e "~/.bin"
  ```
  * Se ela não estiver no PATH
    1. Crie-a com o comando

      ```bash
      mkdir -p ~/.bin
      ```
    2. Adicione a seguinte linha ao começo do arquivo "~/.bashrc"

      ```bash
      export PATH=$PATH:~/.bin    #User scripts
      ```
2. Baixe o arquivo [smart-prompt](smart-prompt) e coloque-o na pasta "~/.bin/"
3. Dê permissão de execução ao arquivo 

  ```bash
  chmod +x ~/.bin/smart-prompt
  ```
4. Ao final do arquivo "~/.bashrc" adicione a seguinte linha

  ```bash
  export PROMPT_COMMAND='export PS1="$(smart-prompt)"'
  ```

### Editando o código fonte

Para editar o código fonte você vai precisar instalar o *[Bash Script Organizer](https://github.com/fholiveira/bso)*.
