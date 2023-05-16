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
                            0, caso contrário}
v¯(A∧B) = H∧(v(A),v(B))     = {1, se v(A)= 1 E v(B) = 1
                            0, caso contrário}
v¯(A∨B) = H∨(v(A),v(B))     = {1, se v(A)= 1 OU v(B) = 1,se v(A)= 1 OU v(B) = 0,se v(A)= 0 OU v(B) = 1
                            0, caso contrário}
v¯(A->B) = H->(v(A),v(B))   = {1, se v(A)= 0 OU v(B) = 1  ps:01,00,11???
                            0, caso contrário}
v¯(A<->B) = H<->(v(A),v(B)) = {1, se v(A)= v(B)
                            0, caso contrário}
                            
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
### Teorema de Dedução


12 exerc especificação
