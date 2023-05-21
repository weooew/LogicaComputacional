# Lógica Computacional (matemática)

Conj de regras p/ raciocínio e argumentação
Entidades linguísticas-> Sentenças declarativas (expressam um pensamento completo) -> Átomoa

## Testando o raciocínio
### Raciocínio Lógica Proposicional:
  (C e J) -> M
  ~M
  C
  Posso conculir: ~J ? SIM
  
-------------------------------------------------------------------------------  
  (A e B) -> C
  ~C
  A
  Posso concluir ~B ? SIM

-------------------------------------------------------------------------------  
  D -> C
  C 
  Posso concluir: ~D? NÃO
  Podemos concuir: D ? NÃO
  Pode ser tanto uma quanto outra (0->1:V e 1->1:V)

---------------------------------------------------
A -> B
~A
Podemos concluir ~B ? SIM (PQ????????????? SE 0->0:V e 0->1:V)
Podemos concluir B ? NÃO

----------------------------------------------------
A ou P
~A
Podemos concluir P ? SIM

------------------------------------------------
A ou B
A -> C
B -> C
Podemos concluir C ? SIM

--------------------------------------------------------
(A ou B)-> C
~A
~B
Podemos concluir C ? NÃO (pode ser c ou ~c)
Podemos concluir  ~C? NÃO (pode ser c ou ~c)

--------------------------------------------------
A -> B
~A->C
B
Podemos concluir  C? NÃO(já que A pode ser 0 ou 1) PS: essa questão está certa? questão aparece 2 vezes no colab
Podemos concluir  ~C? NÃO

------------------------------------------------------
### De 1° ordem (∀, ∃, ∃!):
Quem gosta de voo de parapente gosta de esporte radical. **∀(P->R)**
Maria gosta de voo de parapente.                         **Maria(P)**
Podemos concluir que Maria não gosta de esporte radical? NÃO
Podemos concluir que Maria gosta de esporte radical? SIM

------------------------------------------------------------
Quem não gosta de esporte radical não gosta de voo de parapente. **∀(~P->~R)**
Maria gosta de voo de parapente.                                 **Maria(P)**
Podemos concluir que Maria gosta de esporte radical? SIM (?????????????????)
--------------------------------------------------
Quem gosta de esporte radical gosta de voo de parapente.
Alguém gosta de voo de parapente
Podemos concluir que Alguém gosta de esporte radical? SIM

-----------------------------------------------
Quem gosta de voo de parapente gosta de esporte radical. 
Alguém gosta de esporte radical. 
Podemos concluir que Alguém gosta de voo de parapente? NÃO

---------------------------------------------------------------
Todos que frequentam as aulas e fazem os exercícios são aprovados.
Todos frequentam as aulas.
Todos fazem os exercícios
Podemos concluir que Todos são aprovados? SIM

-----------------
Todos que frequentam as aulas e fazem os exercícios são aprovados.
Alguém frequenta as aulas e faz os exercícios.
Podemos concluir que Alguém é aprovado? SIM

---------------------------
Todos que frequentam as aulas e fazem os exercícios são aprovados.
Alguém frequenta as aulas.
Alguém faz os exercícios
Podemos concluir que Alguém é aprovado? NÃO

---------------------------
Todos que frequentam as aulas e fazem os exercícios são aprovados.
Alguém foi aprovado.
Podemos concluir que Existe alguém que frequenta as aulas e fez os exercícios? SIM

--------------------------------
Todos que frequentam as aulas e fazem os exercícios são aprovados.
Alguém não é aprovado.
Podemos concluir que Existe alguém que não frequenta as aulas ou não faz os exercícios? SIM
Podemos concluir que Existe alguém que não frequenta as aulas? NÃO
Podemos concluir que Existe alguém que não frequenta as aulas e não faz os exercícios? NÃO 

## Lógica proposicional
Alfabeto: Símbolos de pontuação(P0, P1... "chamados de átomos") e Conectivos proposicionais: ¬,∧,∨,→,↔ (ordem de precedência)

### Abreviações

Computador lê da direita p/ esquerda
P->(Q->(P∧Q)) == P->Q->P∧Q
P∧(Q∧R) == P∧Q∧R 
P→(Q→R) == P→Q→R 

### Semântica da Lógica Proposicional (dar significado)
Consiste na atribuição de valores verdades para fórmulas(0 ou 1, dependendo soa valores atribuidos aos átomos).
v: função valoração p/ átomos
v¯: função valoração p/ fórmulas

Sejam v(P) = 1 e v(Q) = 1
  v¯(P∧Q) = 1
  v¯(P∨Q) = 1

------------------------------------------
se v(C) = 1 e v(N)= 0 então 
  v¯((C∧(¬N)))=1, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯(C)=1 e v¯((¬N))=1 ⟹ v¯((C∧(¬N)))=1
  v¯((¬(C∨N)))=0, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯((C∨N))=1 ⟹ v¯((¬(C∨N)))=0  
  v¯(((¬C)→N))=1, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯((¬C))=0 e v¯(N)=0 ⟹ v¯((¬C)→N)=1
  v¯((¬(C→N)))=1, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯((C→N))=0 ⟹ v¯((¬(C→N)))=1
  v¯((C↔N))=0, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯((C↔N))=0
  v¯(((N∧C)→N))=1, pois v¯(C)=1 e v¯(N)=0 ⟹ v¯((N∧C))=0 e v¯(N)=0 ⟹ v¯(((N∧C)→N))=1
  v¯(((¬C)→(¬(N∧C))))=1, pois v(C)=1 e v(N)=0 ⟹ v¯((¬C))=0 e v¯((N∧C))=0 ⟹ v¯((¬C))=0 e v¯((¬(N∧C)))=1 ⟹ v¯(((¬C)→(¬(N∧C))))=1
  
----------------------------------------------
### Teorema da Definição Recursiva em Fórmulas
v¯(¬A) = H¬(v(A))           = {1, se v¯(A)= 0
                            0, caso contrário: v¯(A)= 1}
v¯(A∧B) = H∧(v(A),v(B))     = {1, se v(A)= 1 E v(B) = 1
                            0, caso contrário: v(A)= 0 OU v(B) = 0}
v¯(A∨B) = H∨(v(A),v(B))     = {1, se v(A)= 1 OU v(B) = 1
                            0, caso contrário: v(A)= 0 E v(B) = 0}
v¯(A->B) = H->(v(A),v(B))   = {1, se v(A)= 0 OU v(B) = 1  ps:01,00,11???
                            0, caso contrário: v(A)= 1 E v(B) = 0}
v¯(A<->B) = H<->(v(A),v(B)) = {1, se v(A)= v(B)
                            0, caso contrário: v(A) != v(B)}
                            
### Satisfatibilidade e Validade
De todas as possíveis valorações... 
  **Satisfatível** ao menos uma v¯(φ)=1
  **Insatisfatível** todas v¯(φ)=0
  **Válida**(tautologica) todas v¯(φ)=1
  **Falsificável** ao menos uma v¯(φ)=0

EXEMPLOS:
Fórmula P∧¬P é insatisfatível, demostração (por contradição):
v¯(P∧¬P)=1 ⟺ v¯(P)=1 OU v¯(¬P)=1
               v¯(P)=1 OU v¯(P)=0
               
-------------------------------------
Fórmula P∨¬P é válida, demonstração (por contradição):
v¯(P∨¬P) = 0 ⟺ v(P)=1 E v(¬P) = 0 impossível

-------------------------------------
Fórmula (¬P∧¬Q)<->¬(P∨Q) é válida, demonstração:
v¯(¬P∧¬Q) = v¯(¬(P∨Q))
1. v¯(¬P∧¬Q) = 1 ⟺ v(¬P)= 1 E v(¬Q)= 1
                    v(P)= 0  E  v(Q)= 0
                    v¯(P∨Q) = 0
                    v¯(¬(P∨Q)) = 1
2. v¯(¬P∧¬Q) = 0 ⟺ v(¬P)= 0 OU v(¬Q)= 0
                     v(P)= 1 OU v(Q)= 1
                     v¯(P∨Q) = 1
                     v¯(¬(P∨Q)) = 0

-------------------------------------
(D∧B)↔¬B(D∧B)↔¬B
D∧(¬D∧¬C)
B↔(¬E↔A)B↔(¬E↔A)
¬C∨(¬B∨C)
D↔(E∨¬B)
(¬A∧¬A)→E
¬B∨(¬D∨¬A)
(¬D∨¬D)↔E
¬E∨(¬C∨A)
(¬C∨¬C)↔D(¬C∨¬C)↔D
D∨(¬B∧¬B)
¬A↔(D→E)
(E∧B)∨¬E
¬C∨(¬A∨¬E)
A∧(¬A∧D)A∧(¬A∧D)
C∨(¬A∧D)

### Consequência Lógica
Γ(conj de fórmulas) ⊨ φ
φ consequência lógica de Γ se: teorias verd então formula SEMPRE verd
OBS: logicamente equivalentes, se φ⊨ψ e ψ⊨φ ("φ≡ψ")

Teorema: φ→ψ,¬ψ⊨¬φ
v¯(¬ψ) = 1 ⟺ v¯(ψ) = 0
v¯(φ→ψ)= 1  ⟺ v(φ)= 0 OU v(ψ) = 1
v¯(φ) = 0 ⟺ v¯(¬φ) = 1
PQ????????????????????? A->B = A ou B
 
**Para demonstrar que Γ⊭φ, devemos apresentar um contraexemplo**
A∨B⊭A
demonstração: seja v(A)=0 e v(B)=1. Assim, temos que
        v¯(A∨B)=1, pois v¯(B)=v(B)=1.
        v¯(A)=0, pois v(A)=0.

---------------------------------------------
A∧B→C,A⊭C
demonstração: seja v(A)=1, v(B)=0 e v(C)=0. Assim, temos que 
v¯(A∧B→C)=1, pois v¯(A∧B)=0 ⟸ v¯(B) = v(B) = 0 ⟸ v¯(A)=1, pois v(A)=1 ⟸ v¯(C)=0, pois v(C)=0

-----------------------------------------------
**CAREFULL**
A fórmula ¬(P∧Q)↔(¬P∨¬Q) é válida

Demonstração: v¯(¬(P∧Q)) = v¯(¬(P∨Q))
1. v¯(¬(P∧Q))=1 ⟺ v¯(P∧Q)=0
                ⟺ v¯(P)=0 OU v¯(Q)=0
                ⟺ v¯(¬P)=1 OU v¯(¬Q)=1
                ⟺ v¯(¬P∨¬Q)=1
2. v¯(¬(P∧Q))=0 ⟺ v¯(P∧Q)=1
                ⟺ v¯(P)=1 E v¯(Q)=1
                ⟺ v¯(¬P)=0 E v¯(¬Q)=0
                ⟺ v¯(¬P∨¬Q)=0
                
------------------------------------------                
(P→Q)↔(¬Q→¬P)
Demonstração: v¯(P→Q) = v¯(¬Q→¬P) 
1. v¯(P→Q) = 1 ⟺ 
               ⟺ 
               ⟺ 
               ⟺ 
2. v¯(P→Q) = 0 ⟺ 
               ⟺ 
               ⟺ 
               ⟺ 

-----------------------------------------
A→C,B→C,A∨B⊨C
Se v¯(A→C) = v¯(B→C) = v¯(A∨B) = 1 ENTÃO C
1. v¯(A→C) = 1 ⟺ v¯(A) = 0 OU v¯(C) = 1
2. v¯(B→C) = 1 ⟺ v¯(B) = 0 OU v¯(C) = 1
3. v¯(A∨B) = 1 ⟺ v¯(A) = 1 OU v¯(B) = 1

2 possibilidades:
* v¯(A) = 1 DAÍ 1 é verdadeira
* v¯(B) = 1 DAÍ 2 é verdadeira
Ambas concluem v(C) = 1

--------------------------------------------
### Teorema de Dedução (Γ,φ ⊨ ψ ⟺ Γ ⊨ φ→ψ)

Demostração de: Γ,φ ⊨ ψ 
1. (v(Γ) = 1, v(φ) = 1) ENTÃO v(ψ) = 1  (DEFINIÇÃO)
Suponha a contradição Γ ⊭ φ→ψ:
2. v1(Γ) = 1 
3. v1(φ→ψ) = 0: v1(φ) = 1 E v1(ψ) = 0
Porém, colocando os valores da equação 1 na expressão v1(φ→ψ)=1 

Demonstração de Γ ⊨ φ→ψ
1. se v¯(Γ)=1 ENTÃO v¯(φ→ψ)=1  (DEFINIÇÃO)
Suponha a contradição Γ,φ ⊭ ψ:
2. v¯1(Γ)= 1
3. v¯1(φ) = 1
4. v¯1(ψ) = 0
Com a equação 1 em equação (então v¯1(φ→ψ)=1), porém 3 e 4 daria v¯1(φ→ψ)=0  

EXEMPLO:
Γ={A→B,B→C}, φ=A e ψ=C
A->B, B->C, A ⊨ C   <==>   A->B, B->C ⊨ A->C 

EXERCÍCIOS:
⊨(A→B)↔(¬A∨B)
1.v1(A→B) = 0 ↔ v1(A)=1 E V(B)=0
                 v1(¬A)=0 OU v1(B)=0 
                 v1(¬A∨B) = 0
2. v2(A→B) = 1 ↔ v2(A)= 0 OU v2(B)=1
                  v2(¬A)=1 OU v2(B)=1
                  v2(¬A∨B) = 1 
--------------------------------------
¬A∨B ⊨ A→¬B
1. v(¬A∨B) = 1 ↔ v(¬A)=0 OU v(B)=1    11, 01, 00
                 v(A)=1 OU v(B)=1    
                 v(A)=1 OU v(¬B)=0   (possibilidades 10, 11, 00)   
                 PODE DAR v(A->¬B)=0
???????????????????????????????????????????????????????????????????????????????
⊨(A∨B)↔(¬A→B)
1. v(A∨B) = 0 <-> v(A) = 0 E v(B) = 0
                  v(¬A) = 1 E v(B) = 0
                  v(¬A→B) = 0 
2. v(A∨B) = 1 <-> v(A) = 1 OU v(B) = 1
                  v(¬A) = 0 OU v(B) = 1
                  v(¬A→B) = 1 
                  
--------------------------------------------------
¬A→B ⊨B→A
1. ¬A→B 
--------------------------------------------------
⊨A→(B→A)
--------------------------------------------------
⊨(A∨(B∧C))↔((A∨B)∧(A∨C))
--------------------------------------------------
⊨(A∧(B∨C))↔((A∧B)∨(A∧C))
--------------------------------------------------
{A∨D,A→C,B→C}⊨C
--------------------------------------------------
{A∨B,¬B}⊨A
--------------------------------------------------
{A∨B,¬B,¬A→C}⊨C
--------------------------------------------------
{A∨B,¬B}⊨A⟺{A∨B}⊨(¬B→A)
--------------------------------------------------
Prove, utilizando teorema de dedução:
{A∨B,¬B}⊨A⟺⊨(A∨B)→(¬B→A)
--------------------------------------------------
{A∨B}⊨¬B→A⟺⊨¬B→((A∨B)→A)
--------------------------------------------------
{A∨B}⊨A→B⟺⊨A→((A∨B)→B)
--------------------------------------------------
{A∨B,A→C,B→C}⊨C⟺B→C⊨(A∨B)→((A→C)→C)
--------------------------------------------------
Γ,φ⊨¬ψ, então Γ,ψ⊨¬(ψ→φ)
--------------------------------------------------
Γ,ψ⊨¬(ψ→φ), então Γ,φ⊨¬ψ Γ⊨¬φ∨ψ, então Γ,¬ψ⊨φ
--------------------------------------------------
 Γ⊨¬φ∨ψ, então Γ,¬ψ⊨φ
--------------------------------------------------
Γ,¬ψ⊨φ, então Γ⊨¬φ∨ψ
--------------------------------------------------
## Dedução Natural do estilo de Filtch
Regras de dedução natural:
premisas depois...
  *conjução: ∧i m,n {m. A
                     n. B
                     l. A∧B ∧i m,n}
             ∧e m   {m. A∧B 
                     n. A ∧e m}
  *condicional: ->i m,n {m. A
                         n. B
                         l. A->B ->i m,n}
OBS: Para concluir A → B, a “caixa” deve iniciar com a hipótese A e terminar com a
dedução B;
                ->e m,n {m. A->B 
                         n. A
                         l. B ->e m,n}
  *disjunção: ∨i m {m. A        |m.B  
                    n. A∨B ∨i m |n.A∨B ∨i m}
              ∨e m,(m+1)-n, (n+1)-p  {m. A∨B  
                                       {m+1. A hip
                                       n.C}
                                       {n+1. B hip
                                        p.C}
                                     p+1. C ∨e m,(m+1)-n, (n+1)-p}
  *negação: ¬i m-n {  {m.A hip   "Hipotese dá absurdo, logo provo sua contradição"
                      n.⊥}
                    p.¬A ¬i m-n}
            ¬e m,n{m.A           "Dar o absurdo(contradição: ⊥)"
                   n.¬A
                   p.⊥ ¬e m,n}
  *contradição: ⊥e m {m. ⊥    "Quando chego a uma contradição posso dizer uma fórmula qualquer"
                      n. A ⊥e m} 
  ⊨ A -> (~A->B)
1. {A hip
2.    {~A hip
3.      ⊥ ¬e 1,2
4.      B ⊥e}
5.  ~A->B ->i 2-4}
6. A -> (~A->B) ->i 1-5                     
                
  *copie: {m.A
           n. A copie m}
  *redução ao absurdo: raa m-n {   {m. ¬A hip  "Coloque ~(fórmula) para provar absurdo disso+verd da fórmula"
                                   n. ⊥}
                                n+1. A raa m-n}


QUESTÃO1---------------------------------------------
#|- (A|(A&B))->A
1.{ A|(A&B) hip
2.  {A hip}
3.  {A&B hip
4.   A &e 3}
5. A |e 1, 2-2, 3-4}
6. A|(A&B) -> A ->i 1-5
QUESTÃO2---------------------------------------------
#|- A&(A|B)->A
1. {A&(A|B) hip
2. A &e 1}
3. A&(A|B)-> A ->i 1-2
QUESTÃO3---------------------------------------------
#|- (A->(B->C)) -> (B->(A->C))
1.   {A->(B->C) hip
2.      {B hip
3.         {A hip
4.          B->C ->e 1,3
5.          C ->e 4,2}
6.       A->C ->i 3-5}
7.    B->(A->C) ->i 2-6}
8. (A->(B->C)) -> (B->(A->C)) ->i 1-7
QUESTÃO4---------------------------------------------
#|- (A->(A->B)) -> (A->B)
1. {(A->(A->B)) hip
2.      {A hip
3.       A->B ->e 2,1
4.       B  ->e 3,2}
5.  A->B ->i 2-4}     
6. (A->(A->B)) -> (A->B) ->i 1-5
QUESTÃO5---------------------------------------------
#|- (~A->B)->((~A->~B)->A)
1. {(~A->B) hip
2. {A hip}
6.  } 
7. }
QUESTÃO6------------------------------------------
⊨ A∨¬A
1.  {¬(A∨¬A) hip
2.    {¬A hip
3.     A∨¬A ∨i 2
4.     ⊥ ¬e 3,1}
5.  A raa 2-4
6.  A∨¬A ∨i 5
7.  ⊥ ¬e 6,1}
8. A∨¬A raa 1-7
QUESTÃO7--------------------------------------
|- (A->B)|(B->A)
PROVE UM LADO OU O OUTRO
1.{~(A->B) hip
2.     {A hip
3.      B ->e 1,2}
4. A->B ->i 2-3
5. @ e 1,4}
6. (A->B) ~i 1-5
7. (A->B)|(B->A) |i 6
-??????????????????????????????????????????
---------------------

QUESTÃO10---------------------------------
A&B->C |- B->(A->C)
1. A&B->C pre
2.  {B hip 
3.   {A hip 
4.    A&B &i 2,3
5.    C ->e 1,4}
6.   A->C ->i 3-5}
7. B->(A->C) ->i 2-6

QUESTÃO13---------------------------------------------
#|- (A->(B->A))

QUESTÃO15----------------------------
A->C, A|B, B->C |- C 
1. A->C pre 
2. A|B pre 
3. B->C pre
4. {A hip
5.  C ->e 1,4}
6. {B hip
7. C ->e 3,6}
8. C |e 2,4-5, 6-7

QUESTÃO20------------------------
 # A->B |- ~B->~A 
1. A->B 		pre
2. {	~B		hip
3.	 { 	A	hip
4.	  	B	->e 1,3
5.		  @	~e 2,4}
6.	~A 		~i 3-5}
7. ~B->~A		->i 2-6		
???????????????????????????????????????????????????????????????????????????????????????????????????????????????

QUESTÃO24-----------------------------~
~A|~B |- ~(A&B)
1. ~A|~B pre
2. {A & B hip
3.    {~A hip
4.    A &e 2
5.    @ ~e 3,4}
6.    {~B hip
7.    B &e 2
8.    @ ~e 6,7}
9. @ |e 1, 3-5,6-8}
10. ~(A&B) ~i 2-9

QUESTÃO26---------------------------------------------
(A|B)&(A|C) |- A|(B&C)



QUESTÃO30-----------------------
A|B |-A->B
1. A|B 
2.{A hip
3.   {~A hip
4.    @
5.    B}
6.  {B
7.B}
8. A->B

QUESTÃO33-------------------------
# ~(A->~B) |- A&B
1.~(A->~B) pre
2.{~(A&B) hip
3.   {A hip
4.      {B hip
5.      A&B &i 3,4
6.      @ ~e 2,5} 
7.   ~B ~i 4-6}
8.  A->~B ->i 3-7
9.  @ ~e 1,8}
10.  A&B raa 2-9

QUESTÃO41------------------------------------------
~A|B |- A->B
1.~A|B pre
2.{ A hip
3.  { ~A hip
4.    @ ~e 2,3
5.    B @e 4}
6.  {B hip}
7. B |e 1,3-5,6-6}
8. A->B ->i 2-7

----------------------------------------------------
B |- A->B
1. B pre
2.{ A hip
3.  B copie 1}
4.  A->B ->i 2-3
