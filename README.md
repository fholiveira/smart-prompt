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

## Para usar

1. Baixe o arquivo [smart_script](smart_script) e coloque-o na pasta "~/bin/".
3. Certifique-se que a pasta "~/bin/" está no seu PATH 
2. Dê permissão de execução ao arquivo 
3. No arquivo "~/.bashrc" adicione as seguintes linhas:

    ```bash
    function set_ps1() {
        PS1="$(smart_prompt)"
    }

    PROMPT_COMMAND=set_ps1
    ```

Pronto!
