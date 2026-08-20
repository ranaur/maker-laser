# Desenhos de base

Nesse documento profundidade é entre a frente da árvore (o que as pessoas vêem) e o fundo.
Altura é do "chão" (mesa) até o topo da árvore
E largura é o outro eixo (direta e esquerda de quem olha para a árvore de frente)

                ___
     /\          |
    /  \         |
   /    \        |                \
  /      \       | Altura        /
 /        \      |              / Profundidade
/__________\     |             /
    /  \         |            \
   /____\       _|_

|- largura -|

De acordo com o Desenho Básico_v5 o tamanho dos nichos será de:

Altura: 172.109 - thichness mm
Profundidade: 80.000 (pensando num cilindro de 10cm de tamanho) mm
Largura (entre colunas) : a cada 125.655 mm

# Origem

A imagem da árvore foi feita no ChatGPT, quantizada para diminuir o número de cores, vetorizado no inkscape e trabalhado.



Em UniversalBox.svg é um SVG gerado no boxes.py alterado no código para permitir alguns encaixes.

# Colunas

Parede das placas verticais (altura x profundidade). Terão a altura x profundidade com clicks no topo e na base (lado que encosta nas lajes.

A PAP ente L0 e L1 (chamada PAP0) tem só 135 de altura

As paredes Altura x Profundidade (PAP) terão click on em cima e embaixo e furos para eventuais encaixes laterais.

Os encaixes laterais só vão servir para 4 PAPs, que terão duas paredes Altura x Largura para dar estrutura. Eles tem 60 mm de largura, fora o thickness.

Esses encaixes terão pelo menos dois clicks para encaixar nas PAPs e um nas Lajes.

# Lajes

As lajes são de uma largura X profundidade e possuem furos para encaixe das colunas.

Serão 7 Lajes nomeadas de L0 a L6) onde L0 é no topo, e L6 é na base da árvore.

Laje : Larguras da laje: Furos em (a partir do centro, simétrico *)

folga é um pequeno tamanho (3cm) a mais nas lajes para acomodar o furo do click

l = 125.655
v = 40

L0: l + folga     | l/2
L1: l + folga     : v/2 l/2
L2: l * 2         : v/2 l/2 l/2+vC:\Trove\my-git\maker-laser\@Projects\20260302 - Laser - Advent Calendar\Version 2\Caixas Base
L3: l * 3         : 0.0 l/2 l/2+v l l+v
L4: l * 4 + folga : 0.0 l/2 l l+v 3l/2 3l/2+v
L5: l * 5 + folga : 0.0 l/2 l 3l/2 3l/2+v 2l 2l+2
L6: l * 6 + folga : 0.0 l 2l 2l+2 + os da base: 55 55+l
 
* se marca em 3.0, há um furo em 3 e um em -3, sendo o 0 o centro.

O tronco é feito diferente. São duas colunas de 2 * altura com peças horizontais no centro e fundo. Ela encaixa em L6

