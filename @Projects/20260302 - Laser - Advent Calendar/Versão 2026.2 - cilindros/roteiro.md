# Roteiro para cirar a árvore do advento

## A. Estrutura

1. Decidir o tamanho do cilindro, a espessura da placa e a folga
	diâmetro: 65 mm
	comprimento: 98 mm

	espessura: 3 mm
	folga: 5 mm
	
2. A partir desse dados decidir o tamanho dos furos (elípticos ou não)

	margem de folga: 5 mm
	ângulo da placa: 10 graus (a inclinação das placas da árvore)
		cos(10) = 0.98480775301
		tan(10) = 0.1763269807

	furos: é uma elipse de: 
		(diâmetro + folga) / cos(ângulo da placa) + espessura * tan(ângulo da placa)
		
		(note que se a placa ficasse na vertical o ângulo seria cos(0) = 1 e tan(0) = 0, gerando um círculo.)
		
		por:
		diâmetro + folga
	
	No exemplo: (65 + 5) / cos(10) + 3 * tan(10) = 71.6088437741 ~ 72 x 70 (nese caso eu deixaria um círculo mesmo de 72x72)

3. A partir dos furos, calcular a largura e altura do nicho.

	espaço entre o furo e o a lateral: 10mm
	proposção entre a altura a e alrgura: 1,618 (phi, razão áurea)
	
	largura = (diâmetro+folga) + espaço * 2 = 90
	altura = largura * phi = 90 * 1.618 = 145

	profundidade = Comprimento - espaço * 2 = 80 mm

	teremos nichos de 90 (largura) x 145 (altura) x 80 (prof) quando vistos de frente

4. Com os tamanhos, gerar no boxes.py uma caixa universal desse tamanho:

	Subtrai a espessura por que a caixa é gerada com duas laterais, mas quando fizermos o modelo ele vai ser só uma lateral.

	x = 90 - espessura = 87
	h = 145
	y = 80 - espessura = 77
	
	outside = marcado
	vertical_edges = Finger	holes
	espessura = 3
	
	As configurações podem ser refeitas nessa URL:
	
	https://boxes.hackerspace-bamberg.de/UniversalBox?FingerJoint_style=snap&FingerJoint_surroundingspaces=0&FingerJoint_bottom_lip=0&FingerJoint_edge_width=3&FingerJoint_extra_length=0.0&FingerJoint_finger=5&FingerJoint_play=0&FingerJoint_space=8&FingerJoint_width=1.0&Stackable_angle=60&Stackable_bottom_stabilizers=0.0&Stackable_height=2.0&Stackable_holedistance=1.0&Stackable_width=4.0&Hinge_grip_percentage=0&Hinge_outset=0&Hinge_outset=1&Hinge_pinwidth=0.5&Hinge_axle=2.0&Hinge_grip_length=0&Hinge_hingestrength=1&CabinetHinge_bore=3.2&CabinetHinge_eyes_per_hinge=5&CabinetHinge_hinges=2&CabinetHinge_style=inside&CabinetHinge_eye=1.5&CabinetHinge_play=0.05&CabinetHinge_spacing=2.0&SlideOnLid_hole_width=0&SlideOnLid_second_pin=0&SlideOnLid_second_pin=1&SlideOnLid_spring=both&SlideOnLid_style=rectangular&SlideOnLid_surroundingspaces=2.0&SlideOnLid_bottom_lip=0.0&SlideOnLid_edge_width=1.0&SlideOnLid_extra_length=0.0&SlideOnLid_finger=3.0&SlideOnLid_play=0.05&SlideOnLid_space=2.0&SlideOnLid_width=1.0&Click_angle=5.0&Click_bottom_radius=0.1&Click_depth=3.0&RoundedTriangleEdge_height=50.0&RoundedTriangleEdge_r_hole=2.0&RoundedTriangleEdge_radius=30.0&RoundedTriangleEdge_outset=1.0&Mounting_d_head=6.5&Mounting_d_shaft=3.0&Mounting_margin=0.125&Mounting_num=2&Mounting_side=back&Mounting_style=straight+edge%2C+within&HandleEdge_height=20.0&HandleEdge_hole_height=75.0&HandleEdge_hole_width=40%3A40&HandleEdge_on_sides=0&HandleEdge_on_sides=1&HandleEdge_radius=10.0&HandleEdge_outset=1.0&Flex_stretch=1.05&Flex_connection=1.0&Flex_distance=0.5&Flex_width=5.0&Lid_handle=none&Lid_style=none&Lid_handle_height=8.0&Lid_height=4.0&Lid_play=0.1&top_edge=e&bottom_edge=e&x=87&y=145&h=77&outside=0&outside=1&vertical_edges=finger+holes&thickness=3.0&burn=0.1&format=svg&labels=0&labels=1&reference=100.0&tabs=0.0&qr_code=0&inner_corners=loop&spacing=0.5&debug=0&language=pt_br&render=0

TODO: O valor para o tamanho das peças fica inpreciso. O programa subtrai dois thickness. Talvez fazer sem o outside, mas ocm uma espessura a menos? (outside=false, H 142 ao invés de 145?). Precisei ajustar no passo B3.
	Baixe o SVG e abra o INkscape

5. Crie um novo arquivo no Inkscape

	Gere um retângulo de Largura x Altura [90 x 145], oco, de hairline de espessura.
	Gere uma elipse/círculo e alinhe dentro do retângulo (lemfre que o inkscape trabalha com o raio e não o diâmetro)
	Agrupe.
	
	
	Faça 47 cópias (total 48 retângulos)
	Organize um grid, sem espaço de 8 (linhas) por 6 (colunas) zero espaçamento
	Deixe só uma na primeira linha, duas na segunda e assim por diante. Na sétima e outava, deixe só duas. Vai ficar parecido com isso.
	
```
	[]
	[][]
	[][][]
	[][][][]
	[][][][][]
	[][][][][][]
	[][]
	[][]
```

	Agrupe cada linha em grupos separados, e centralize tudo no centro. Deve ficar assim:
	
```
	     []
	    [][]
	   [][][]
	  [][][][]
	 [][][][][]
	[][][][][][]
	    [][]
	    [][]
```

	Desagrupe tudo algumas vezes até ficarem só círculos e retângulos. Agrupe todos os círculos e todos os retângulos em dois grupos separados.

	Pode criar um layer para eles, mas os furos precisarão sair depois.
	
	Salve como 1 - Estrutura.SVG
	
6. Importe as faces

	Importe de Árvore_1.svg (que é a Árvore.SVG com os caminhos unificados) numa camada nova
	Ajuste a árvore para que cada camada do furo fique alinhado em uma camada da árvore (e os dois últimos ficam no tronco).
	É meio chatinho, mas o segredo é deixar os furos quase encostando (mas ainda com uma boa folga) na base do andar da árvore.
	
	Salve como 2 - Estrutura com árvore.SVG

## B. As placas

	A estrutura da árvore tem os seguintes tipos de placas que precisarão ser encaixadas:
	
	* Frente 1 (topo) a Frente 7 (tronco) : são as placas em forma das camadas das árvores
	* Verticais (V), Verticais-um (V1): todas as placas que ficarão na vertical são de dois tipos: a vertical, o tipo básico para todas as camadas exceto a primeira camada (topo), que usa a Vertical 1
	* Horizontais 0 (topo do topo) até a Horizontal 6: são placas que fazem cada camada
	* Placas do tronco TV e TH que são totalmente diferentes das outras.
	
1. Ajuste o topo e a base
	O topo vai precisar se um pouco mais curto por conta da ponta cônica da árvore.
	A base da árvore vai precisar ser cortada no limite mínimo da estrutura.
	Arrume as camadas.
	
	Salve como 3 - ajustes

TODO: Os furos do tronco ficam mais próximos?

2. Crie um novo layer e importe a universal box

	A universal box importa 4 cortes. Os dois de cima são iguais aos dois de baixo.
	
	O da esquerda (back/front) vai ser extendidos para fazer as placas Horizontais. Os da direita (right/left) são praticamente os Vs prontos.

3. Ajuste os Vs

	O boxes.py gera os clips ao contrário. Para desmontar será muito melhor inverter.
	Ao inverter os snaps, precisa consertar a linha ou o laser vai cortar os snaps, o que dá certo trabalho.
	
	Garanta que os snaps encaixam na peça à esquerda.
	Depois de gerar o V, gere o V1
	Salve.
	
4. Gerar os Hs

	Na peça da direita verifique a largura (que deve estar errada) e a altura da peça. Corrija a peça V de acordo, deixando ela com duas thickness a menos. Faça o mesno na V1.
	
	No exemplo, as duas peças eram de 80, mas ficaram de 74.2 (80 - 2 * 3 (thickness) + burn*2)
	
	Pode apagar as duas de baixo
	
	Ajuste o tamanho dos furos e garanta o alinhamento com os encaixes da V.
	
	* Gerar H0
	
		Para gerar a H0 é fácil, mas você precisará espaçar ela de forma que os dois furos estejam a largura (90) de distância.
		
		Faça um retângulo de 90 - 2 espessuras (74) + brun*2 = 74.2 x 90 + 3 espessuras + 2 burns = 108.2
		
		Coloque uma borda arredondada (3mm)
		
		Coloque um par de furos de cada lado 3x6 entre 22,5 e 90-22,5 para encaixar o gancho da face
		
		Alinhe os furos à distância e pronto. H0 está feita.
		
	* Gerar H1
	
		Ela é o dobro à H0, porém com um furo no centro. Ajuste o teclado para um múltiplo da metade da sua largura. (90 => 45 ajustei pra 5mm) (Preferences / Behaviour / Steps)
		
		Duplique H0 para criar H1. Mude o tamanho do retângulo para + 90 (H0 era 108.20, H1 é 198.20)
		Duplique uma coluna de furos e ante 90 pro lado.
		
	* Gerar outros Hs
	
		Siga a mesma idéia até H5, olhando a estrutura como referência.
		
		Basta duplicar a camada anterior, aumentar 90 no retângulo de base (mantendo as pontas arredondada) e duplicar os 4 últimos furos.
		
		O H6 é igual ao H5, porém com menos marcações. E  com as marcaçÕes do tronco.

# C. Tronco

	O tronco é diferente. Ele é uma caixa diferente das outras. 

	A profundidade é 4 thickness maior que a profundidade da árvore (74) => 86, para ela poder encaixar na parte externa (na H6)
	A largura é 2cm (1 pra cada lado) maior que duas larguras (90) => 200
	E a altura duas alturas (145) => 290
	
	Como não se gerará a parte da frente automaticamente, temos:

https://boxes.hackerspace-bamberg.de/UniversalBox?FingerJoint_style=snap&FingerJoint_surroundingspaces=0&FingerJoint_bottom_lip=0&FingerJoint_edge_width=3&FingerJoint_extra_length=0.0&FingerJoint_finger=5&FingerJoint_play=0&FingerJoint_space=8&FingerJoint_width=1.0&Stackable_angle=60&Stackable_bottom_stabilizers=0.0&Stackable_height=2.0&Stackable_holedistance=1.0&Stackable_width=4.0&Hinge_grip_percentage=0&Hinge_outset=0&Hinge_outset=1&Hinge_pinwidth=0.5&Hinge_axle=2.0&Hinge_grip_length=0&Hinge_hingestrength=1&CabinetHinge_bore=3.2&CabinetHinge_eyes_per_hinge=5&CabinetHinge_hinges=2&CabinetHinge_style=inside&CabinetHinge_eye=1.5&CabinetHinge_play=0.05&CabinetHinge_spacing=2.0&SlideOnLid_hole_width=0&SlideOnLid_second_pin=0&SlideOnLid_second_pin=1&SlideOnLid_spring=both&SlideOnLid_style=rectangular&SlideOnLid_surroundingspaces=2.0&SlideOnLid_bottom_lip=0.0&SlideOnLid_edge_width=1.0&SlideOnLid_extra_length=0.0&SlideOnLid_finger=3.0&SlideOnLid_play=0.05&SlideOnLid_space=2.0&SlideOnLid_width=1.0&Click_angle=5.0&Click_bottom_radius=0.1&Click_depth=3.0&RoundedTriangleEdge_height=50.0&RoundedTriangleEdge_r_hole=2.0&RoundedTriangleEdge_radius=30.0&RoundedTriangleEdge_outset=1.0&Mounting_d_head=6.5&Mounting_d_shaft=3.0&Mounting_margin=0.125&Mounting_num=2&Mounting_side=back&Mounting_style=straight+edge%2C+within&HandleEdge_height=20.0&HandleEdge_hole_height=75.0&HandleEdge_hole_width=40%3A40&HandleEdge_on_sides=0&HandleEdge_on_sides=1&HandleEdge_radius=10.0&HandleEdge_outset=1.0&Flex_stretch=1.05&Flex_connection=1.0&Flex_distance=0.5&Flex_width=5.0&Lid_handle=none&Lid_style=none&Lid_handle_height=8.0&Lid_height=4.0&Lid_play=0.1&top_edge=e&bottom_edge=e&x=290&y=200&h=86&outside=0&outside=1&vertical_edges=finger+holes&thickness=3.0&burn=0.1&format=svg&labels=0&labels=1&reference=100.0&tabs=0.0&qr_code=0&inner_corners=loop&spacing=0.5&debug=0&language=pt_br&render=0

		
		
		
		
	