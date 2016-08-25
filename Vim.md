Aula de Vim:

    
    Abrindo o vim:
            - vim <file>
            - dentro do vim :e <file>. Obs: "e" = short for edit;

    Andando no Vim:
               k - para cima
               l - para a direita
               j - para baixo
               h - para a esquerda
    
    Inserindo:
        - i - Insere onde o esta o cursor
        - I - Insere no comeco da linha 
        - s - Deleta o caracter e entra no modo de insersao
        - S - Deleta a linha e entra no modo de insersao 
        - a - insere apos aonde o cursor esta
        - A - entra no modo de insersao no fim da linha
        - o - cria uma linha abaixo de onde esta e entra no modo de insersao
        - O - cria uma linha acima de onde esta e entra no modo de insersao 
        - c
        - C - deleta do cursor ate o fim da linha e entra no modo de insersao
         
    Moving:
        w - anda ate o comeco da proxima palavra 
        W - anda ate o comeco da proxima PALAVRA 
        b - anda ate o comeco da PALAVRA anterior 
        B - anda ate o comeco da PALAVRA anterior
        e - anda ate o fim da proxima palavra
        E - anda ate o fim da proxima PALAVRA
        [n]f<o> - Forward until (nth) (o) (Inclusive) 
        [n]F<o> - Forward until (nth) (o) (Inclusive) 
        [n]t<o> - Backward until (nth) (o) (Inclusive) 
        [n]T<o> - Backward until (nth) (o) (Inclusive) 

    Serching:
        / - Forward
        ? - Backward
        * - Word under cursor - forward (bounded = extamente igual)
        g* - Word under cursor - forward (unbounded = contida, ou com maiuscula)
        # - Word under cursor - backward (bounded = extamente igual)   
        g# - Word under cursor - backward (unbounded = contida, ou com maiuscula)
        n - next result
        N - previous result

    Common Edit commands:
        d - Delete: [range]d<motion>        
            dd - delete current line
            dj - delete current line and next line (j = down)
            2dj - delete current line and next 2 lines (j = down)
        c - Change (Same as d but put me in insert mode)
            cw - change word
            cc = S - Delete current line ans enter insert mode
        ~ - Toggle the case of character under cursor
        g~ - Toggle the case of motion]
            g~w - Toggle case of the cursor -> end of word
            g~iw - Toggle case of entire woed undr cursor        
        r{char} - replace the caracter under the cursor with char
        R - Enter Insert mode, replacing characters rather than inserting

    Registers:
       "<reg> - Registrador que guarda algo
            Exemple:
                "ayy - Yank current line into 'a' register
                "ap - Paste 'a' register " 
        <Ctrl-r><reg> - Paste contents of <reg> no modo de insersao
        :reg - Para listar os registradores   
        Special Registers: 
            " - Noname buffer - Last dcsxy"
            _ - Blackhole buffer
            % - Filename
            / - Last search
            : - Last command
            . - Last edit

    Advanced Motions:
        () - Sentences ("." delimited words)
        {} - Paragraphs (Next empty line) 
        <#>G - Go to line #
        gg - Go to the top of the file
        ]] - Next section (May move between functions)
        [[ - Previous section 
        0 - Front of line
        ^ - Front of line (first non-blank)
        % - Matching brace/bracket/paren/tag

    Text Objects:  {} [] () w <> t ' ' " "
        i vs a:
            i = Inside
                Example:
                 self.test[obj|ect] -> ci[ -> self.test[|]
                a = Around
                Example:
                 self.test[obj|ect] -> ca[ -> self.test|

    Misc. Commands:            
        zz - Center screen 
        zt - Scroll the screen so the cursor is at the top
        zb - Scroll the screen so the cursor is at the botton
        ZZ - Write and quit (= :wq)     
    
        
    Managing multiple files at once:
        :tabnew [file] - Open a new tab with given file (or empty file)
        gt or :tabn - Next tab
        gT or :tabp - Previous tab
        :tabm # - Move current tab to position # (zero-indexed), no argument = end
        :tabc - Close current tab
        :tabo - Close all other tabs except current

    Vimrc:

        Mapping:
            imap - map something in Insert mode
            nmap - map something in Normal mode
            vmap - map something in Visual mode        
        Macros:
            Q<reg> - to record some action to the register - Q - stop recording
            @<reg> - do the action saved in register
