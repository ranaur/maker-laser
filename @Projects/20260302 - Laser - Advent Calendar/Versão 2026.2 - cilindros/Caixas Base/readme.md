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

# Caixa base:
http://127.0.0.1:8000/UniversalBox?FingerJoint_style=snap&FingerJoint_surroundingspaces=0&FingerJoint_bottom_lip=0&FingerJoint_edge_width=2&FingerJoint_extra_length=0&FingerJoint_finger=3&FingerJoint_play=0.2&FingerJoint_space=8&FingerJoint_width=1&Stackable_angle=60&Stackable_bottom_stabilizers=0.0&Stackable_height=2.0&Stackable_holedistance=1.0&Stackable_width=4.0&Hinge_grip_percentage=0&Hinge_outset=0&Hinge_outset=1&Hinge_pinwidth=0.5&Hinge_axle=2.0&Hinge_grip_length=0&Hinge_hingestrength=1&CabinetHinge_bore=3.2&CabinetHinge_eyes_per_hinge=5&CabinetHinge_hinges=2&CabinetHinge_style=inside&CabinetHinge_eye=1.5&CabinetHinge_play=0.05&CabinetHinge_spacing=2.0&SlideOnLid_hole_width=0&SlideOnLid_second_pin=0&SlideOnLid_second_pin=1&SlideOnLid_spring=both&SlideOnLid_style=rectangular&SlideOnLid_surroundingspaces=2.0&SlideOnLid_bottom_lip=0.0&SlideOnLid_edge_width=1.0&SlideOnLid_extra_length=0.0&SlideOnLid_finger=3.0&SlideOnLid_play=0.05&SlideOnLid_space=2.0&SlideOnLid_width=1.0&Click_angle=5&Click_bottom_radius=0.1&Click_depth=3.0&RoundedTriangleEdge_height=50.0&RoundedTriangleEdge_r_hole=2.0&RoundedTriangleEdge_radius=30.0&RoundedTriangleEdge_outset=1.0&Mounting_d_head=6.5&Mounting_d_shaft=3.0&Mounting_margin=0.125&Mounting_num=2&Mounting_side=back&Mounting_style=straight+edge%2C+within&HandleEdge_height=20.0&HandleEdge_hole_height=75.0&HandleEdge_hole_width=40%3A40&HandleEdge_on_sides=0&HandleEdge_on_sides=1&HandleEdge_radius=10.0&HandleEdge_outset=1.0&Flex_stretch=1.05&Flex_connection=1.0&Flex_distance=0.5&Flex_width=5.0&Lid_handle=none&Lid_style=none&Lid_handle_height=8.0&Lid_height=4.0&Lid_play=0.1&bottom_edge=f&x=80&y=60&h=170&outside=0&outside=1&top_edge=f&vertical_edges=finger+holes&thickness=3.0&burn=0.1&format=svg&labels=0&labels=1&reference=100.0&tabs=0.0&qr_code=0&qr_code=1&inner_corners=loop&spacing=0.5&debug=0&language=en&render=0
