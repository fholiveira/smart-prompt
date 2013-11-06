Smart prompt
============

Bash script que cria um prompt mais esperto. Ele informa:

* O usuario e máquina atuais
* Se está em um virtualenv do Python e qual o nome do mesmo
* O diretório atual, usando a sintaxe reduzida do vim
* Caso seja um repo do git
    * Mostra o nome da branch atual
    * Se tem arquivos no working directory e na stage area
    * O estado do repo em relação a origin
* Se o usuário tem permissões de root

### Para usar

1. Baixe o arquivo [smart_prompt](smart_prompt) e coloque-o na pasta "~/bin/".
2. Certifique-se que a pasta "~/bin/" está no seu PATH 
3. Dê permissão de execução ao arquivo 

    ```bash
    chmod +x ~/bin/smart_prompt
    ```
4. No arquivo "~/.bashrc" adicione as seguintes linhas:
    ```bash
    function set_ps1() {
        PS1="$(smart_prompt)"
    }

    PROMPT_COMMAND=set_ps1
    ```

### Editando o código fonte

Para editar o código fonte você vai precisar instalar o *[Bash Script Organizer](github.com/fholiveira/bso)*.



Pronto!
