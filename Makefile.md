Aula de Makefile: MAC211 - Gubi 

    Rules: 
        target: prerequisies ...
            recipe ...
    
    - Nosso programa
        "prog : p1.o p2.o
            gcc -o prog p1.o p2. o
         
         p1.o : p1.c
            gcc -o p1.o p1.c

         p2.o : p2.c  
            gcc -o p2.o p2.c"

    Variaveis:
        $@ - nome do alvo
        $< - primeira dependencia
        $^ - lista de dependecias, sem repeticao
        $+ - lista de dependencias
        $? 
    
    - Nosso programa:
        "prog: p1.o p2.o
            gcc -o $@ $^

         p1.o : p1.c
            gcc -o $@ $^ 
        
         p2.o: p2.c
            gcc -o $@ $^" 

     
    Regras implicitas:  
                Faz um arquivo .c em .o
                    %.o : %.c 
                           $(CC) -c $(CFLAGS) $<                 
    
    - Nosso programa fica assim:
       "CC = gcc
        
        prog.o : p1.o p2.o"
    
    Limpando:
        "clean:
            rm -f *.o prog"

    

    
