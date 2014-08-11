Smart prompt
============

Bash script que cria um prompt mais esperto. Ele informa:

* O usuario e máquina atuais
* Se está em um virtualenv do Python e qual o nome do mesmo
* O diretório atual, usando a sintaxe reduzida do vim
* Caso seja um repo do git exibe
    * o nome da branch atual
    * se está fazendo rebase
    * a quantidade de arquivos na staging area, modificados e untracked
    * a quantidade de arquivos em conflito
    * o estado do repo em relação a origin
    * utiliza cores para indicar o estado do repo
	* verde quando não há modificações
	* vermelho quando arquivos foram modificados
	* amarelo quando todos os arquivos modificados estão na staging area
	* azul quando há somente arquivos untracked
* Se o usuário tem permissões de root

### Para usar

1. Baixe o arquivo [smart-prompt](smart-prompt) e coloque-o na pasta "~/.bin/".
2. Certifique-se que a pasta "~/.bin/" está no seu PATH 

    * Se pasta estiver no path ela aparecerá destacada ao rodar o comando
        ```bash
        echo $PATH | grep -e "$HOME/.bin" -e "~/.bin"
        ```
    * Se ela não estiver no path você pode criá-la
        ```bash
        mkdir ~/.bin 
        ```
      E então adicionar a seguinte linha ao começo do arquivo "~/.bashrc"
        ```bash
        export PATH=$PATH:~/.bin    #User scripts
        ```

3. Dê permissão de execução ao arquivo 

    ```bash
    chmod +x ~/.bin/smart-prompt
    ```
4. No arquivo "~/.bashrc" adicione as seguintes linhas:

    ```bash
    export PROMPT_COMMAND='export PS1="$(smart-prompt)"'
    ```

### Editando o código fonte

Para editar o código fonte você vai precisar instalar o *[Bash Script Organizer](https://github.com/fholiveira/bso)*.
