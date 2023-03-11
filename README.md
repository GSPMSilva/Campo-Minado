# Campo-Minado
O jogo consiste em liberar o campo das minas terrestres podendo marcar aonde as possíveis minas estão. O jogo tem uma marcação com números dizendo quantas minas estão próximas daquela casa. Ao liberar todas as casas o jogo se encerará dizendo que o jogador venceu. Se o jogador clicar aonde se encontra a mina o jogo encerará dizendo que o jogador perdeu.
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Algoritmo "Campo Minado"
// Autor: GUSTAVO SEVERO SILVA e DIOGO SILVA DORTA.
Var
campo: vetor[1..8,1..8] de inteiro
campojogo: vetor[1..8,1..8] de literal
quantidadedeminas: inteiro
i, j: inteiro
jogou: logico
//------------------------------------------------------------------------------
procedimento processamentominas
var
count: inteiro
i, j: inteiro
x, y: inteiro
//------------------------------------------------------------------------------
Inicio
repita
   x <- randi (8) + 1
   y <- randi (8) + 1
   se campo [x,y] <> -1 entao
      campo [x,y] <- -1
      count <- count + 1
   fimse
ate count = quantidadedeminas
fimprocedimento
//------------------------------------------------------------------------------
procedimento processamento (1, c: inteiro)
var
i, j, count, 1um, cum: inteiro
inicio
count<- 0
1 <- 1 - 1
j <- o - 1
1um <- 1 + 1
cum <- o + 1
enquanto 1 <= 1um faca
enquanto j <= cum faca
         se ( 1 >= 1) e (1 <= 8) e (j >= 1) e (j <= 0) entao
         se (campo [i, j] = -1 entao
            count <- count + 1
            fimse
            fimse
            j <- j + 1
fimenquanto
j <- c - 1
i <- i + 1
fimenquanto
campo[1,c] <- count
fimprocedimento
//------------------------------------------------------------------------------
procedimento processamentonumero
var
i, j, cont: inteiro
inicio
cont <- 0
para i de 1 ate 8 faca
para j de 1 ate 8 faca
     campojogo [1,j] <- "X"
     se(campo[1,j] <> -1) entao
     processamentonumero(i,j)
     fimse
     fimpara
     fimpara
     fimprocedimento
//------------------------------------------------------------------------------
procedimento menu
var
op: inteiro
inicio
limpatela
escreval("
               |¯¯ |¯| |¯|¯| |¯¯| |¯|      |¯|¯| | ¦_¦¦ |¯| |¯¯\ |¯|
               |__ |¯| ||¯|| |¯¯  |_|  ¯¯  ||¯|| | ¦¦¯¦ |¯| |__/ |_|
escreval("
escreval("")
escreval("")
escreval("")
escreval("")
escreval("")
escreval("              E S C O L H A   U M A  O P Ç Ã O:")
escreval("")
escreval("")
escreval("                       1) Jogar")
escreval("                       2) Instruções")
escreval("                       3) Créditos")
escreval("                       4) Score")
repita
  leia(op)
ate (op >= 1) ou (op <= 4)
escolha op
caso 1
     jogou <- verdadeiro
     menudificuldade
caso 2
     instrucoes
caso 3
     creditos
caso 4
     score
fimascolha
fimprocedimento
//------------------------------------------------------------------------------
// vou fazer com nivel de dificuldade porque se eu não pratiacar estarei ferrado
// culpa da professora aline falo mesmo. Fazendo na força do café
procedimento menudificuldade
var
op: inteiro
inicio
limpatela
escreval("
               |¯¯ |¯| |¯|¯| |¯¯| |¯|      |¯|¯| | ¦_¦¦ |¯| |¯¯\ |¯|
               |__ |¯| ||¯|| |¯¯  |_|  ¯¯  ||¯|| | ¦¦¯¦ |¯| |__/ |_|
escreval("
escreval("")
escreval("")
escreval("")
escreval("")
escreval("")
escreval("              E S C O L H A   U M A  O P Ç Ã O:")
escreval("")
escreval("")
escreval("                       1) Fácil (4 minas)")
escreval("                       2) Médio (8 minas)")
escreval("                       3) Dificil (12 minas)")
repita
   leia (op)
ate (op >= 1) ou (op <= 3)
escolha op
caso 1
     quantidadedeminas <-4
caso 2
     quantidadedeminas <- 8
caso 3
     quantidadedeminas <-12
fimescolha
processamentominas
processamentonumeros
escrevercampo
fimprocedimento
//------------------------------------------------------------------------------
//To fazendo o VisualG e minha dupla estará fazendo o C#. Esta linha de código
//estará no Redme. Para avaliação do código.
procedimento instrucoes
var
op: inteiro
inicio
limpatela
escreval("
                   |¯¯ |¯| |¯|¯| |¯¯| |¯|      |¯|¯| | ¦_¦¦ |¯| |¯¯\ |¯|
                   |__ |¯| ||¯|| |¯¯  |_|  ¯¯  ||¯|| | ¦¦¯¦ |¯| |__/ |_|
escreval("
escreval("")
escreval("")
escreval("")
escreval("")
escreval("")
escreval("                           C O M O   J O G A R:")
escreval("")
escreval("")
escreval("            Se descobrir um quadrado vazio, o jogo continua,")
escreval("                     e o sistema informará quantas")
escreval("            minas estão escondidas nos oito quadrados que o cercam,")
escreval("              Se você descobrir uma mina, você  E X P L O D E.")
escreval("            (Cada local descoberto sem bomba você recebe 1 ponto)")
escreval("
escreval("                                1) Menu")
escreval("                                2) Jogar")
repita
  leia (op)
ate (op >= 1) ou (op <= 2)
escolha op
caso 1
     menu
caso 2
     menudificuldade
fimeescolha
fimprocedimento
//------------------------------------------------------------------------------
//Dicas retidas do professor Code.
procedimento creditos
var
k: literal
inicio
limpatela
escreval("
                   |¯¯ |¯| |¯|¯| |¯¯| |¯|      |¯|¯| | ¦_¦¦ |¯| |¯¯\ |¯|
                   |__ |¯| ||¯|| |¯¯  |_|  ¯¯  ||¯|| | ¦¦¯¦ |¯| |__/ |_|
escreval("
escreval("")
escreval("")
escreval("")
escreval("")
escreval("")
escreval("                          C O M O   J O G A R:")
escreval("")
escreval("")
escreval("             Mini - Jogo, desenvolvido por Gustavo e Diogo")
escreval("                     Feito para futuras melhorias")
escreval("                      Trabalho Escolar Bimestral")
escreval("
escreval("                   Pressione enter para voltar ao menu")
leia(k)
menu
fimprocedimento
//------------------------------------------------------------------------------
procedimento escrevercampo
var
i, j: inteiro
inicio
limpatela
para i de 1 ate 2 faca
     escreval
fimpara
escreva ("                  ")
para i de 1 ate 8 faca
     escreva("   ",  i)
fimpara
escreval
escreva("                   - - - - - - - - - - - - - - - -")
para i de 1 ate 8 faca
     escreva("             ")
     para j de 1 ate 8 faca
     escreva(" | ", campojogo[i,j])
fimpara
escreva(" | ", i)
escreval
escreva("                    - - - - - - - - - - - - - - - -")
fimpara
escreval
jogo
fimprocedimento
//------------------------------------------------------------------------------
procedimento jogo
var
c: inteiro
l: inteiro
inicio
repita
 escreva("Escolha uma coluna (1 - 0): ")
 leia (c)
ate (c >= 1) ou (c <= 8)
repita
 escreva ("Escolha uma linha (1 - 8): ")
 leia (l)
ate (l >= 1) ou (l <= 8)
se (campo[l,c] <> -1) entao
 campojogo[l,c] <- numpcarac(campo[l,c]
 escrevercampo
senao
 estourobomba
fimse

fimprocedimento
//------------------------------------------------------------------------------
procedimento estourobomba
var
i: literal
inicio
limpatela
//timer(500)
escreval
escreval("                         VOCÊ MORREU !!!")
escreval("")
escreval("")
escreval("")
escreval("            Pressione enter para ver sua pontuação")
leia(i)
score

fimprocedimento score
var
pontuacao: inteiro
k: literal
inicio
se jogou entao
pontuaao <- 64
para i de 1 ate 8 faca
para j de 1 ate 8 faca
se campojogo[i,j] = "X" entao
pontuacao <- pontuacao - 1
fimse
fimpara
fimpara
limpatela
escreval
escreval
escreval
escreval
escreval
escreval("                   Sua pontuação é: ", pontuacao)
escreval("                   Pontuação máxima: 64")
escreval
escreval
escreval
escreva("                    Pressione enter para voltar ao menu")
leia(k)
menu
senao
escreva("Você ainda não jogou! (Pressione enter para voltar ao menu)")
leia(K)
menu
fimse

fimprocedimento
//------------------------------------------------------------------------------
inicio
menu
 
Fimalgoritmo
