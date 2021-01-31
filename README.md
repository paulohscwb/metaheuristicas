<link rel="stylesheet" href="imagens/style.css">
<script type="text/x-mathjax-config">
         MathJax.Hub.Config({
           tex2jax: {
             inlineMath: [ ['$','$'], ["\\(","\\)"] ],
             processEscapes: true
           }
         });
</script>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

<h2 id="inicio">Algoritmos, exemplos e aplicações</h2>

<p>Esta página contém os algoritmos e exemplos de algumas Metaheurísticas. Além disso, são mostradas as aplicações destas técnicas em várias áreas da Pesquisa Operacional.</p>
<p>A apostila está disponível no link: <a href="#" target="_blank">apostila de Metaheurísticas</a></p>

<h3>Redes Neurais Artificiais</h3>
<details>
  <summary id="parte1">Perceptron e Adaline</summary>
  <p>Material da página 1 até a página 19.</p>
   <img src="parte1/apostila_2020_1_19_0001.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0002.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0003.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0004.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0005.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0006.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0007.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0008.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0009.png"/>
   <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Neural Perceptron:
<pre><code>0. Inicializar os pesos, o bias e a taxa de aprendizado: <a alt="vetor de pesos">w = 0</a>, <a alt="bias">&theta; = 0</a>, <a alt="taxa de aprendizagem">&alpha; = 1</a> 
	1. Enquanto o <a alt="critérios de parada mais usados:&#10;número máximo de iterações, erro mínimo alcançado,&#10;ou número máximo de iterações sem modificações nos pesos">critério de parada</a> não for satisfeito, execute os passos 2-6:
		2. <a alt="cada par de treinamento deve ser apresentado à rede">Para cada par de dados de treinamento (x,d)</a>, execute os passos 3-5:
		3. <a alt="calculamos o valor da variável y* sem a função de ativação">Calcule y* = &theta; + &sum;<sub>i</sub>x<sub>i</sub>w<sub>i</sub></a> 
		4. <a alt="Neste passo, calculamos a função de ativação em y*">Se y* &gt; &delta;, então y = 1</a> 
		   Se -&delta; ≤ y* ≤ &delta;, então y = 0
		   Se y* &lt; -&delta;, então y = -1 
		5. <a alt="A atualização dos pesos só é feita quando a rede erra a classificação">Atualize os pesos e a tendência:</a>
		   Se y ≠ d, faça
		     w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> + &alpha;dx<sub>i</sub> e &theta;<sup>atual</sup> = &theta;<sup>anterior</sup> + &alpha;d 
		   Caso contrário
		     w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> e &theta;<sup>atual</sup> = &theta;<sup>anterior</sup>
6. <a alt="Neste passo, podemos calcular o erro quantitativo da rede">Teste a condição de parada.</a>

</code></pre></figcaption>
   </details></div>
   <img src="parte1/apostila_2020_1_19_0009a.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0010.png"/>
   <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução: 1&ordf; e 2&ordf; iterações</summary>
	<p>Vamos acompanhar os cálculos e as interpretações geométricas das 2 primeiras iterações deste exercício da Rede Neural Perceptron.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="001" name="sl" checked>
			   <label for="001"></label>
			   <img src="parte1/10_01_01.png"/>
			   <figcaption>Apresentação do primeiro padrão para a rede (x<sub>1</sub>, x<sub>2</sub>) = (1, 1). Como y = &theta; + x<sub>1</sub>w<sub>1</sub> + x<sub>2</sub>w<sub>2</sub> = 0 + 1.0 + 1.0 = 0 &ne; d = 1, então os pesos são atualizados (passo 5 do algoritmo).</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="002" name="sl">
			   <label for="002"></label>
			   <img src="parte1/10_01_01.png"/>
			   <figcaption>Os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; definem as equações das retas usadas para a classificação. O parâmetro &delta; cria uma região de indefinição para a classificação.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="003" name="sl">
			   <label for="003"></label>
			   <img src="parte1/10_01_03.png"/>
			   <figcaption>Apresentação do segundo padrão para a rede (1, 0). Como y = &theta; + x<sub>1</sub>w<sub>1</sub> + x<sub>2</sub>w<sub>2</sub> = 1 + 1.1 + 0.1 = 2 &ne; d = -1, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="004" name="sl">
			   <label for="004"></label>
			   <img src="parte1/10_01_03.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="005" name="sl">
			   <label for="005"></label>
			   <img src="parte1/10_01_05.png"/>
			   <figcaption>Apresentação do terceiro padrão para a rede (0, 1). Como y &ne; d, então os pesos são atualizados. Como os coeficientes das variáveis x<sub>1</sub> e x<sub>2</sub> ficaram nulos, não temos a interpretação geométrica nesta apresentação de padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="006" name="sl">
			   <label for="006"></label>
			   <img src="parte1/10_01_05.png"/>
			   <figcaption>Apresentação do último padrão para a rede (0, 0). Como y = d, então os pesos são mantidos. Usando esta combinação de pesos, podemos calcular o erro da primeira iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="006a" name="sl">
			   <label for="006a"></label>
			   <img src="parte1/10_01_06a.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 0, w<sub>2</sub> = 0, &theta; = -1) da última apresentação de padrões para calcular o erro. Apenas o primeiro padrão está classificado incorretamente: logo, o erro quantitativo nesta primeira iteração é de 25%.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="007" name="sl">
			   <label for="007"></label>
			   <img src="parte1/10_01_07.png"/>
			   <figcaption>Recomeçamos a apresentação de cada padrão para a rede na próxima iteração. O primeiro padrão (1, 1) é apresentado à rede, com a combinação de parâmetros (0, 0, 1). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="008" name="sl">
			   <label for="008"></label>
			   <img src="parte1/10_01_07.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="009" name="sl">
			   <label for="009"></label>
			   <img src="parte1/10_01_09.png"/>
			   <figcaption>Apresentação do segundo padrão para a rede (1, 0). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="010" name="sl">
			   <label for="010"></label>
			   <img src="parte1/10_01_09.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="011" name="sl">
			   <label for="011"></label>
			   <img src="parte1/10_01_11.png"/>
			   <figcaption>Apresentação do terceiro padrão para a rede (0, 1). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="012" name="sl">
			   <label for="012"></label>
			   <img src="parte1/10_01_11.png"/>
			   <figcaption>Apresentação do último padrão para a rede (0, 0). Como y = d, então os pesos são mantidos. Usando esta combinação de pesos, podemos calcular o erro da segunda iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="012a" name="sl">
			   <label for="012a"></label>
			   <img src="parte1/10_01_12a.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 0, w<sub>2</sub> = 0, &theta; = -2) da última apresentação de padrões para calcular o erro. Apenas o primeiro padrão está classificado incorretamente: logo, o erro quantitativo da segunda iteração é de 25%.</figcaption>
		   </li>
		</ul>
		<img src="parte1/10_01_01.png" class="fundo" style="visibility:hidden"/>
  </details>
  <details class="sub"><summary>&#x1f4c3; Resolução: 3&ordf; ~ 9&ordf; iterações</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas das 7 próximas iterações deste exercício da Rede Neural Perceptron.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="013" name="sl">
			   <label for="013"></label>
			   <img src="parte1/10_01_13.png"/>
			   <figcaption>Recomeçamos a apresentação de cada padrão para a rede na próxima iteração. O primeiro padrão (1, 1) é apresentado à rede, com a combinação de parâmetros (0, 0, -2). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="014" name="sl">
			   <label for="014"></label>
			   <img src="parte1/10_01_13.png"/>
			   <figcaption>Os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta;  definem as equações das retas usadas para a classificação. Note que temos 2 padrões classificados corretamente e os outros 2 na região de indefinição.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="015" name="sl">
			   <label for="015"></label>
			   <img src="parte1/10_01_15.png"/>
			   <figcaption>Fazendo os cálculos da mesma forma mostrada nas duas primeiras iterações, temos as classificações da quarta e da quinta iteração. Nestes casos, 3 padrões estão classificados corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="016" name="sl">
			   <label for="016"></label>
			   <img src="parte1/10_01_17.png"/>
			   <figcaption>Fazendo os cálculos da mesma forma mostrada nas duas primeiras iterações, temos as classificações da sexta e da sétima iteração. Nestes casos, 3 padrões estão classificados corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="017" name="sl">
			   <label for="017"></label>
			   <img src="parte1/10_01_19.png"/>
			   <figcaption>Fazendo os cálculos da mesma forma mostrada nas duas primeiras iterações, temos as classificações da oitava e da nona iteração. Os padrões ficam separados corretamente com a combinação de pesos da nona iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="018" name="sl">
			   <label for="018"></label>
			   <img src="parte1/10_01_20.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 2, w<sub>2</sub> = 3, &theta; = -4) da última apresentação de padrões para calcular o erro. Todos os padrões estão classificados corretamente. Logo, podemos finalizar o processo de aprendizagem desta Rede Neural.</figcaption>
		   </li>
		</ul>
		<img src="parte1/10_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte1/apostila_2020_1_19_0010a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício da Rede Neural Perceptron. Vamos usar entradas e saídas bipolares.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="019" name="sl">
			   <label for="019"></label>
			   <img src="parte1/10_02_01.png"/>
			   <figcaption>O primeiro padrão (1, 1) é apresentado à rede. Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="020" name="sl">
			   <label for="020"></label>
			   <img src="parte1/10_02_01.png"/>
			   <figcaption>Usando os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; que definem as equações das retas usadas para a classificação, temos apenas 1 padrão classificado corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="021" name="sl">
			   <label for="021"></label>
			   <img src="parte1/10_02_03.png"/>
			   <figcaption>O segundo padrão (1, -1) é apresentado à rede. Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="022" name="sl">
			   <label for="022"></label>
			   <img src="parte1/10_02_03.png"/>
			   <figcaption>Usando os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; que definem as equações das retas usadas para a classificação, temos 2 padrões classificados corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="023" name="sl">
			   <label for="023"></label>
			   <img src="parte1/10_02_05.png"/>
			   <figcaption>O terceiro padrão (-1, 1) é apresentado à rede. Como y &ne; d, então os pesos são atualizados. Na apresentação do último padrão, temos que y = d e os valores dos pesos são mantidos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="024" name="sl">
			   <label for="024"></label>
			   <img src="parte1/10_02_07.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 1, w<sub>2</sub> = 1, &theta; = -1) da última apresentação de padrões para calcular o erro. Todos os padrões estão classificados corretamente. Logo, podemos finalizar o processo de aprendizagem desta Rede Neural.</figcaption>
		   </li>
		</ul>
		<img src="parte1/10_02_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte1/apostila_2020_1_19_0010b.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0011.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0012.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Neural Perceptron com bolso:
<pre><code>0. Inicializar os pesos, o bias e a taxa de aprendizado: w = 0, <a alt="vetor de pesos do bolso">w<sup>bolso</sup> = 0</a>, &theta; = 0, &alpha; = 1 
	1. Enquanto o critério de parada</a> não for satisfeito, execute os passos 2-7:
		2. Para cada par de dados de treinamento (x,d), execute os passos 3-5:
		3. Calcule y* = &theta; + &sum;<sub>i</sub>x<sub>i</sub>w<sub>i</sub>
		4. Se y* &gt; &delta;, então y = 1
		   Se -&delta; ≤ y* ≤ &delta;, então y = 0
		   Se y* &lt; -&delta;, então y = -1 
		5. Atualize os pesos e a tendência:
		   Se y ≠ d, faça
		     w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> + &alpha;dx<sub>i</sub> e &theta;<sup>atual</sup> = &theta;<sup>anterior</sup> + &alpha;d 
		   Caso contrário
		     w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> e &theta;<sup>atual</sup> = &theta;<sup>anterior</sup>
		6. <a alt="guardamos no bolso a melhor combinação de pesos&#10;esta tática é muito usada nas Metaheurísticas para não perder bons pesos">Se w classifica corretamente mais exemplos do que w<sup>bolso</sup>:</a>  
		     w<sup>bolso</sup> = w; grave o número de exemplos corretos 
6. Teste a condição de parada.
</code></pre></figcaption>
   </details></div>
   <img src="parte1/apostila_2020_1_19_0012a.png"/>
   <figcaption>Para separar os dados em mais classes, podemos inserir mais neurônios na Rede Neural</figcaption>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0013.png"/>
  <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0014.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0015.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0016.png"/>
  <figcaption>Vamos utilizar a Regra Delta para deduzir as formas de atualizações dos pesos em algumas Redes Neurais. O princípio é sempre de buscar a minimização do erro de classificação de cada Rede Neural Artificial.</figcaption>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0017.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0018.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Neural Adaline:
<pre><code>0. Inicializar os pesos <a alt="pesos com valores aleatórios">(w = rnd)</a>, a tendência <a alt="bias nulo">(&theta; = 0)</a>
e a taxa de aprendizagem <a alt="taxa de aprendizagem com valor entre 0 e 1">0 &lt; &alpha; &lt; 1</a> (convergência fica muito lenta quando a taxa é muito 
próxima de zero; e a convergência não é garantida para valores muito próximos de 1).
	1. Enquanto o critério de parada não for satisfeito, execute os passos 2-5:
		2. Para cada par de dados para treinamento (x,d), execute os passos 3-4:
			3. Faça <a alt="primeiro calculamos o valor de y*">y* = &theta; + &sum;<sub>i</sub>x<sub>i</sub>w<sub>i</sub></a> 
			4. <a alt="os pesos e o bias são sempre atualizados">Atualize os pesos e a tendência:</a>
			    w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> + &alpha;(d – y*)x<sub>i</sub>  
			    &theta;<sup>atual</sup> = &theta;<sup>anterior</sup> + &alpha;(d – y*)
			    <a alt="função de ativação do tipo limiar">se y* ≥ 0, y = 1; caso contrário, y = 0 (ou y = -1 para bipolar)</a>
		5. <a alt="podem ser as mesmas condições usadas no Perceptron">Teste a condição de parada.</a> 
	6. Se a maior alteração de pesos não ultrapassa um limite mínimo de tolerância, pare; 
	caso contrário, continue. 
</code></pre></figcaption>
   </details></div>
  <img src="parte1/apostila_2020_1_19_0018a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício da Rede Neural Adaline. Vamos usar entradas e saídas bipolares.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="025" name="sl">
			   <label for="025"></label>
			   <img src="parte1/18_01_01.png"/>
			   <figcaption>A arquitetura da Rede Neural Adaline fica análoga à arquitetura que usamos no caso do Perceptron. O resumo dos cálculos está mostrado nesta imagem. Vamos inicializar com os pesos indicados de w e &theta; e a taxa de aprendizagem &alpha;.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="026" name="sl">
			   <label for="026"></label>
			   <img src="parte1/18_01_02.png"/>
			   <figcaption>O primeiro padrão (1, 1) é apresentado à rede, com a atualização automática dos pesos. Note que o termo &#9651;&theta; é comum na atualização dos pesos w<sub>1</sub> e w<sub>2</sub>; logo, podemos aplicar uma simplificação para estes cálculos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="027" name="sl">
			   <label for="027"></label>
			   <img src="parte1/18_01_03.png"/>
			   <figcaption>O padrão (1, -1) é apresentado à rede, com a atualização automática dos pesos. Note que a simplificação na atualização dos pesos foi aplicada neste passo.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="028" name="sl">
			   <label for="028"></label>
			   <img src="parte1/18_01_04.png"/>
			   <figcaption>O padrão (-1, 1) é apresentado à rede, com a atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="029" name="sl">
			   <label for="029"></label>
			   <img src="parte1/18_01_05.png"/>
			   <figcaption>O padrão (-1, -1) é apresentado à rede, com a atualização automática dos pesos. Note que a reta com os coeficientes dos pesos classifica todos os padrões corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="030" name="sl">
			   <label for="030"></label>
			   <img src="parte1/18_01_06.png"/>
			   <figcaption>Usando a equação do erro, similar à usada para deduzir a Regra Delta, temos que: E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = (1 - 1)<sup>2</sup> + (1 - 1)<sup>2</sup> + (1 - 1)<sup>2</sup> + (-1 - (-1))<sup>2</sup> = 0. O erro quantitativo também fica nulo, logo, podemos finalizar a aprendizagem desta Rede Neural.</figcaption>
		   </li>
		</ul>
		<img src="parte1/18_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte1/apostila_2020_1_19_0018b.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0019.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte2">Multi Layer Perceptron (MLP)</summary>
  <p>Material da página 19 até a página 40.</p>
  <img src="parte2/apostila_2020_1_19_0019.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0020.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0021.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
   <figcaption><p align="center">Neste caso, o parâmetro &beta; da função sigmoidal é igual a 1.
   <br>A derivada da função y<sub>k</sub> = tanh(y<sub>k</sub>*) com parâmetro &beta; = 1 é y'<sub>k</sub> = (1 - y<sub>k</sub><sup>2</sup>). 
   <br>Logo, a atualização de pesos w será <b>&#9651;w<sub>jk</sub> = &alpha;(1 - y<sub>k</sub><sup>2</sup>)(d<sub>k</sub> - y<sub>k</sub>)z<sub>j</sub></b>.</p></figcaption>
   </details></div>
  <img src="parte2/apostila_2020_20_40_0021a.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0022.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
   <figcaption><p align="center">As derivadas das funções y<sub>k</sub> = tanh(y<sub>k</sub>*) e z<sub>j</sub> = tanh(z<sub>j</sub>*) com parâmetro &beta; = 1 são:
   <br>y'<sub>k</sub> = tanh(y<sub>k</sub>*) = (1 - y<sub>k</sub><sup>2</sup>) e z'<sub>j</sub> = tanh(z<sub>j</sub>*) = (1 - z<sub>j</sub><sup>2</sup>). 
   <br>Logo, a atualização de pesos v será <b>&#9651;v<sub>ij</sub> = &alpha;&sum;<sub>k</sub>[(d<sub>k</sub> - y<sub>k</sub>)(1 - y<sub>k</sub><sup>2</sup>)w<sub>jk</sub>](1 - z<sub>j</sub><sup>2</sup>)x<sub>i</sub></b>.</p></figcaption>
   </details></div>
  <img src="parte2/apostila_2020_20_40_0022a.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0023.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0024.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0025.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0026.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo 1 de Rede Neural MLP: 1 camada escondida, funções de ativação sigmoidais, m saídas
<pre><code>0. Inicialize os <a alt="pesos w e bias &theta; com valores aleatórios">pesos das conexões e do bias com valores aleatórios</a>; 
inicialize a taxa de aprendizagem &alpha;. Para cada padrão de entrada, execute os passos de 1 a 3:
	1. <a alt="calculamos as saídas z da camada escondida de cada padrão de entrada&#10;depois, com os valores z encontramos os valores de cada saída yk">Calcule as entradas na camada escondida</a>, e a saída da rede:
	   z<sub>j</sub>* = &sum;<sub>i</sub>v<sub>ij</sub>x<sub>i</sub> + &theta;a<sub>j</sub>  &rArr;  z<sub>j</sub> = 1/(1 + e<sup>-z<sub>j</sub>*</sup>), onde j = 1, ..., p, i = 1, ..., n
	   y<sub>k</sub>* = &sum;<sub>j</sub>w<sub>jk</sub>z<sub>j</sub> + &theta;b<sub>k</sub>  &rArr;  y<sub>k</sub> = 1/(1 + e<sup>-y<sub>k</sub>*</sup>), onde k = 1, 2, ..., m 
	2. <a alt="as correções da camada de saída são feitas antes&#10;os valores encontrados são repassados para a camada escondida (backpropagation)">Calcule as correções das conexões da camada de saída:</a>
	   &#9651;w<sub>jk</sub> = &alpha;y<sub>k</sub>(1 – y<sub>k</sub>)(d<sub>k</sub> – y<sub>k</sub>)z<sub>j</sub>  &rArr;  w<sub>jk</sub> = w<sub>jk</sub> + &#9651;w<sub>jk</sub> 
	   &#9651;&theta;b<sub>k</sub> = &alpha;y<sub>k</sub>(1 – y<sub>k</sub>)(d<sub>k</sub> – y<sub>k</sub>)  &rArr;  &theta;b<sub>k</sub> = &theta;b<sub>k</sub> + &#9651;&theta;b<sub>k</sub> 
	3. <a alt="as correções da camada escondida são feitas por último">Calcule as correções das conexões da camada escondida:</a>
	   &#9651;v<sub>ij</sub> = &alpha;&sum;<sub>k</sub>[(d<sub>k</sub> – y<sub>k</sub>)y<sub>k</sub>(1 – y<sub>k</sub>)w<sub>jk</sub>]z<sub>j</sub>(1 - z<sub>j</sub>)x<sub>i</sub>  &rArr;  v<sub>ij</sub> = v<sub>ij</sub> + &#9651;v<sub>ij</sub> 
	   &#9651;&theta;a<sub>j</sub> = &alpha;&sum;<sub>k</sub>[(d<sub>k</sub> – y<sub>k</sub>)y<sub>k</sub>(1 – y<sub>k</sub>)w<sub>jk</sub>]z<sub>j</sub>(1 - z<sub>j</sub>)  &rArr;  &theta;a<sub>j</sub> = &theta;a<sub>j</sub> + &#9651;&theta;a<sub>j</sub> 
	4. <a alt="atualização linear: &alpha; = 0,95.&alpha; ou &alpha; = 0,9.&alpha;">Atualize a taxa de aprendizagem</a>, verifique os erros para todos os padrões de entrada, 
	e teste o <a alt="erro mínimo ou número máximo de iterações">critério de parada.</a>
 
</code></pre></figcaption>
   </details></div>
   <img src="parte2/apostila_2020_20_40_0026a.png"/>
   <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo 2 de Rede Neural MLP: 1 camada escondida, funções de ativação sigmoidais, 1 saída
<pre><code>0. Inicialize os <a alt="pesos w e bias &theta; com valores aleatórios">pesos das conexões e do bias com valores aleatórios</a>; 
inicialize a taxa de aprendizagem &alpha;. Para cada padrão de entrada, execute os passos de 1 a 3:
	1. <a alt="calculamos as saídas z da camada escondida de cada padrão de entrada&#10;depois, com os valores z encontramos os valores da saída y">Calcule as entradas na camada escondida</a>, e a saída da rede:
	   z<sub>j</sub>* = &sum;<sub>i</sub>v<sub>ij</sub>x<sub>i</sub> + &theta;a<sub>j</sub>  &rArr;  z<sub>j</sub> = 1/(1 + e<sup>-z<sub>j</sub>*</sup>), onde j = 1, ..., p, i = 1, ..., n
	   y = &sum;<sub>j</sub>w<sub>j</sub>z<sub>j</sub> + &theta;b  &rArr;  y = 1/(1 + e<sup>-y*</sup>), onde k = 1, 2, ..., m 
	2. <a alt="as correções da camada de saída são feitas antes&#10;os valores encontrados são repassados para a camada escondida (backpropagation)">Calcule as correções das conexões da camada de saída:</a>
	   &#9651;w<sub>j</sub> = &alpha;y(1 – y)(d – y)z<sub>j</sub>  &rArr;  w<sub>j</sub> = w<sub>j</sub> + &#9651;w<sub>j</sub> 
	   &#9651;&theta;b = &alpha;y(1 – y)(d – y)  &rArr;  &theta;b = &theta;b + &#9651;&theta;b 
	3. <a alt="as correções da camada escondida são feitas por último">Calcule as correções das conexões da camada escondida:</a>
	   &#9651;v<sub>ij</sub> = &alpha;(d – y)y(1 – y)w<sub>j</sub>z<sub>j</sub>(1 - z<sub>j</sub>)x<sub>i</sub>  &rArr;  v<sub>ij</sub> = v<sub>ij</sub> + &#9651;v<sub>ij</sub> 
	   &#9651;&theta;a<sub>j</sub> = &alpha;(d – y)y(1 – y)w<sub>j</sub>z<sub>j</sub>(1 - z<sub>j</sub>)  &rArr;  &theta;a<sub>j</sub> = &theta;a<sub>j</sub> + &#9651;&theta;a<sub>j</sub> 
	4. <a alt="atualização linear: &alpha; = 0,95.&alpha; ou &alpha; = 0,9.&alpha;">Atualize a taxa de aprendizagem</a>, verifique os erros para todos os padrões de entrada, 
	e teste o <a alt="erro mínimo ou número máximo de iterações">critério de parada.</a>
 
</code></pre></figcaption>
   </details></div>
   <img src="parte2/apostila_2020_20_40_0026b.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0027.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo 1 de Rede Neural MLP: 1 camada escondida, funções de ativação tanh, m saídas
<pre><code>0. Inicialize os <a alt="pesos w e bias &theta; com valores aleatórios">pesos das conexões e do bias com valores aleatórios</a>; 
inicialize a taxa de aprendizagem &alpha;. Para cada padrão de entrada, execute os passos de 1 a 3:
	1. <a alt="calculamos as saídas z da camada escondida de cada padrão de entrada&#10;depois, com os valores z encontramos os valores de cada saída yk">Calcule as entradas na camada escondida</a>, e a saída da rede:
	   z<sub>j</sub>* = &sum;<sub>i</sub>v<sub>ij</sub>x<sub>i</sub> + &theta;a<sub>j</sub>  &rArr;  z<sub>j</sub> = tanh(z<sub>j</sub>*), onde j = 1, ..., p, i = 1, ..., n
	   y<sub>k</sub>* = &sum;<sub>j</sub>w<sub>jk</sub>z<sub>j</sub> + &theta;b<sub>k</sub>  &rArr;  y<sub>k</sub> = tanh(y<sub>k</sub>*), onde k = 1, 2, ..., m 
	2. <a alt="as correções da camada de saída são feitas antes&#10;note que usamos a derivada da função tanh em todas as correções">Calcule as correções das conexões da camada de saída:</a>
	   &#9651;w<sub>jk</sub> = &alpha;(1 – y<sub>k</sub><sup>2</sup>)(d<sub>k</sub> – y<sub>k</sub>)z<sub>j</sub>  &rArr;  w<sub>jk</sub> = w<sub>jk</sub> + &#9651;w<sub>jk</sub> 
	   &#9651;&theta;b<sub>k</sub> = &alpha;(1 – y<sub>k</sub><sup>2</sup>)(d<sub>k</sub> – y<sub>k</sub>)  &rArr;  &theta;b<sub>k</sub> = &theta;b<sub>k</sub> + &#9651;&theta;b<sub>k</sub> 
	3. <a alt="as correções da camada escondida são feitas por último&#10;note que usamos as derivadas da função tanh">Calcule as correções das conexões da camada escondida:</a>
	   &#9651;v<sub>ij</sub> = &alpha;&sum;<sub>k</sub>[(d<sub>k</sub> – y<sub>k</sub>)(1 – y<sub>k</sub><sup>2</sup>)w<sub>jk</sub>](1 - z<sub>j</sub><sup>2</sup>)x<sub>i</sub>  &rArr;  v<sub>ij</sub> = v<sub>ij</sub> + &#9651;v<sub>ij</sub> 
	   &#9651;&theta;a<sub>j</sub> = &alpha;&sum;<sub>k</sub>[(d<sub>k</sub> – y<sub>k</sub>)(1 – y<sub>k</sub><sup>2</sup>)w<sub>jk</sub>](1 - z<sub>j</sub><sup>2</sup>)  &rArr;  &theta;a<sub>j</sub> = &theta;a<sub>j</sub> + &#9651;&theta;a<sub>j</sub> 
	4. <a alt="atualização linear: &alpha; = 0,95.&alpha; ou &alpha; = 0,9.&alpha;">Atualize a taxa de aprendizagem</a>, verifique os erros para todos os padrões de entrada, 
	e teste o <a alt="erro mínimo ou número máximo de iterações">critério de parada.</a>
 
</code></pre></figcaption>
  </details></div>
  <img src="parte2/apostila_2020_20_40_0027a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício da Rede Neural Multi Layer Perceptron (MLP). Vamos usar saídas binárias para classificar os padrões de entrada em dois conjuntos: A e B.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="031" name="sl">
			   <label for="031"></label>
			   <img src="parte2/27_01_01.png"/>
			   <figcaption>A arquitetura da Rede Neural deste primeiro exercício fica análoga à arquitetura que usamos nos exemplos Perceptron e Adaline. O resumo dos cálculos está mostrado nesta imagem. Vamos inicializar com os pesos indicados de w e &theta; e a taxa de aprendizagem &alpha; = 1.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="032" name="sl">
			   <label for="032"></label>
			   <img src="parte2/27_01_02.png"/>
			   <figcaption>O primeiro padrão (0, 2) é apresentado à rede. Calculamos a saída y* e aplicamos a função de ativação sigmóide (pois a saída está no intervalo [0,1]). Note que podemos simplificar a atualização dos pesos, pois o termo &#9651;&theta; é comum nas atualizações dos pesos w<sub>1</sub>, w<sub>2</sub>. </figcaption>
		   </li>
		   <li>
			   <input type="radio" id="033" name="sl">
			   <label for="033"></label>
			   <img src="parte2/27_01_03.png"/>
			   <figcaption>O padrão (1, 2) é apresentado à rede, com a atualização automática dos pesos. Aplicando a simplificação de atualização dos pesos, podemos calcular as atualizações para usarmos na próxima apresentação de padrão de entrada.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="034" name="sl">
			   <label for="034"></label>
			   <img src="parte2/27_01_04.png"/>
			   <figcaption>O padrão (1, 3) é apresentado à rede, com a atualização automática dos pesos. Este é o último padrão de entrada do conjunto com d = 1.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="035" name="sl">
			   <label for="035"></label>
			   <img src="parte2/27_01_05.png"/>
			   <figcaption>O padrão (2, 1) é apresentado à rede, com a atualização automática dos pesos. Este é o primeiro padrão de entrada do conjunto com d = 0.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="036" name="sl">
			   <label for="036"></label>
			   <img src="parte2/27_01_06.png"/>
			   <figcaption>O padrão (1, 0) é apresentado à rede, com a atualização automática dos pesos. Este é o último padrão de entrada nesta rede, finalizando a primeira iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="037" name="sl">
			   <label for="037"></label>
			   <img src="parte2/27_01_07.png"/>
			   <figcaption>Calculamos as saídas y* e y de cada padrão de entrada para encontrarmos o erro desta iteração. A equação do erro é a mesma que foi usada para deduzir a Regra Delta: E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,937. A interpretação geométrica da MLP pode ser melhor compreendida usando o gráfico em 3 dimensões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="038" name="sl">
			   <label for="038"></label>
			   <img src="parte2/27_01_08.png"/>
			   <figcaption>Na segunda iteração, precisamos atualizar a taxa de aprendizagem: &alpha; = &alpha;.0,95. O primeiro padrão (0, 2) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="039" name="sl">
			   <label for="039"></label>
			   <img src="parte2/27_01_09.png"/>
			   <figcaption>O padrão (1, 2) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="040" name="sl">
			   <label for="040"></label>
			   <img src="parte2/27_01_10.png"/>
			   <figcaption>O padrão (1, 3) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="041" name="sl">
			   <label for="041"></label>
			   <img src="parte2/27_01_11.png"/>
			   <figcaption>O padrão (1, 0) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="042" name="sl">
			   <label for="042"></label>
			   <img src="parte2/27_01_12.png"/>
			   <figcaption>O padrão (2, 1) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="043" name="sl">
			   <label for="043"></label>
			   <img src="parte2/27_01_13.png"/>
			   <figcaption>Calculamos as saídas y* e y de cada padrão de entrada para encontrarmos o erro desta iteração. A equação do erro é a mesma que foi usada para deduzir a Regra Delta: E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,859.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="044" name="sl">
			   <label for="044"></label>
			   <img src="parte2/27_01_14.png"/>
			   <figcaption>Ao final da 10&ordf; iteração, temos esta combinação de pesos. O erro nesta iteração é E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,222, que representa uma grande redução quando comparada com as duas primeiras iterações.</figcaption>
		   </li>
		</ul>
		<img src="parte2/27_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte2/apostila_2020_20_40_0027b.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício da Rede Neural Multi Layer Perceptron (MLP). Vamos usar saídas binárias para classificar os padrões de entrada em dois conjuntos A e B, além de uma camada escondida para acelerar a convergência.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="045" name="sl">
			   <label for="045"></label>
			   <img src="parte2/27_02_01.png"/>
			   <figcaption>A arquitetura da Rede Neural deste exercício tem 3 neurônios na camada escondida. O resumo dos cálculos está mostrado nesta imagem. Vamos inicializar com os pesos indicados de v, w &theta;a e &theta;b e a taxa de aprendizagem &alpha; = 1.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="046" name="sl">
			   <label for="046"></label>
			   <img src="parte2/27_02_02.png"/>
			   <figcaption>O primeiro padrão (0, 2) é apresentado à rede. Calculamos a saída z* e aplicamos a função de ativação sigmóide (na camada escondida, podemos aplicar a função tanh ou limiar). Com os valores z, calculamos a saída da rede y* com a função de ativação sigmóide.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="047" name="sl">
			   <label for="047"></label>
			   <img src="parte2/27_02_02a.png"/>
			   <figcaption>De acordo com o algoritmo Backpropagation, atualizamos primeiro os pesos da camada de saída w. Podemos simplificar a atualização dos pesos w, pois o termo &#9651;&theta;b é comum nas atualizações dos pesos w. </figcaption>
		   </li>
		   <li>
			   <input type="radio" id="048" name="sl">
			   <label for="048"></label>
			   <img src="parte2/27_02_02b.png"/>
			   <figcaption>De acordo com o algoritmo Backpropagation, atualizamos a seguir os pesos da camada de entrada v. Podemos simplificar a atualização dos pesos v, pois os termos &#9651;&theta;a<sub>1</sub> &#9651;&theta;a<sub>2</sub> e &#9651;&theta;a<sub>3</sub> são comuns nestas atualizações de pesos. </figcaption>
		   </li>
		   <li>
			   <input type="radio" id="049" name="sl">
			   <label for="049"></label>
			   <img src="parte2/27_02_03.png"/>
			   <figcaption>O padrão (1, 2) é apresentado à rede, com a atualização automática dos pesos. Aplicando a simplificação de atualização dos pesos, podemos calcular as atualizações para a próxima apresentação de padrão de entrada.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="050" name="sl">
			   <label for="050"></label>
			   <img src="parte2/27_02_04.png"/>
			   <figcaption>O padrão (1, 3) é apresentado à rede, com a atualização automática dos pesos. Este é o último padrão de entrada do conjunto com d = 1.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="051" name="sl">
			   <label for="051"></label>
			   <img src="parte2/27_02_05.png"/>
			   <figcaption>O padrão (2, 1) é apresentado à rede, com a atualização automática dos pesos. Este é o primeiro padrão de entrada do conjunto com d = 0.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="052" name="sl">
			   <label for="052"></label>
			   <img src="parte2/27_02_06.png"/>
			   <figcaption>O padrão (1, 0) é apresentado à rede, com a atualização automática dos pesos. Este é o último padrão de entrada nesta rede, finalizando a primeira iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="053" name="sl">
			   <label for="053"></label>
			   <img src="parte2/27_02_07.png"/>
			   <figcaption>Calculamos as saídas z* e z para determinar as saídas y* e y de cada padrão de entrada. A equação do erro é a mesma que foi usada para deduzir a Regra Delta: E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,268. A interpretação geométrica da MLP pode ser melhor compreendida usando o gráfico em 3 dimensões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="054" name="sl">
			   <label for="054"></label>
			   <img src="parte2/27_02_08.png"/>
			   <figcaption>Na segunda iteração, precisamos atualizar a taxa de aprendizagem: &alpha; = &alpha;.0,95. O primeiro padrão (0, 2) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="055" name="sl">
			   <label for="055"></label>
			   <img src="parte2/27_02_09.png"/>
			   <figcaption>No final da 10&ordf;  iteração, temos esta configuração de pesos. O erro nesta iteração é E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,102.</figcaption>
		   </li>
		</ul>
		<img src="parte2/27_02_07.png" class="fundo" style="visibility:hidden"/>
  </details></div>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0028.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício da Rede Neural Multi Layer Perceptron (MLP). Vamos usar saídas binárias para classificar os padrões de entrada com duas variáveis de saída y e uma camada escondida.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="056" name="sl">
			   <label for="056"></label>
			   <img src="parte2/28_01_01.png"/>
			   <figcaption>A arquitetura da Rede Neural deste exercício tem 3 neurônios na camada escondida. O resumo dos cálculos está mostrado nesta imagem. Vamos inicializar com os pesos indicados de v, w, &theta;a e &theta;b e a taxa de aprendizagem &alpha; = 1.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="057" name="sl">
			   <label for="057"></label>
			   <img src="parte2/28_01_02.png"/>
			   <figcaption>O primeiro padrão (-1, -1) é apresentado à rede. Calculamos a saída z* e aplicamos a função de ativação sigmóide (na camada escondida, podemos aplicar a função tanh ou limiar). Com os valores z, calculamos a saída da rede y* com a função de ativação sigmóide.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="058" name="sl">
			   <label for="058"></label>
			   <img src="parte2/28_01_02a.png"/>
			   <figcaption>De acordo com o algoritmo Backpropagation, atualizamos primeiro os pesos da camada de saída w. Podemos simplificar a atualização dos pesos w, pois os termos &#9651;&theta;b<sub>1</sub> e &#9651;&theta;b<sub>2</sub> são comuns nas atualizações dos pesos w. </figcaption>
		   </li>
		   <li>
			   <input type="radio" id="059" name="sl">
			   <label for="059"></label>
			   <img src="parte2/28_01_02b.png"/>
			   <figcaption>De acordo com o algoritmo Backpropagation, atualizamos a seguir os pesos da camada de entrada v. Podemos simplificar a atualização dos pesos v, pois os termos &#9651;&theta;a<sub>1</sub> &#9651;&theta;a<sub>2</sub> e &#9651;&theta;a<sub>3</sub> são comuns nestas atualizações de pesos. </figcaption>
		   </li>
		   <li>
			   <input type="radio" id="060" name="sl">
			   <label for="060"></label>
			   <img src="parte2/28_01_03.png"/>
			   <figcaption>O padrão (-1, 1) é apresentado à rede, com a atualização automática dos pesos. Aplicando a simplificação de atualização dos pesos, podemos calcular as atualizações para a próxima apresentação de padrão de entrada.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="061" name="sl">
			   <label for="061"></label>
			   <img src="parte2/28_01_04.png"/>
			   <figcaption>O padrão (1, -1) é apresentado à rede, com a atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="062" name="sl">
			   <label for="062"></label>
			   <img src="parte2/28_01_05.png"/>
			   <figcaption>O padrão (1, 1) é apresentado à rede, com a atualização automática dos pesos. Este é o último padrão de entrada nesta rede, finalizando a primeira iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="063" name="sl">
			   <label for="063"></label>
			   <img src="parte2/28_01_06.png"/>
			   <figcaption>Calculamos as saídas z* e z para determinar as saídas y* e y de cada padrão de entrada. A equação do erro é a mesma que foi usada para deduzir a Regra Delta: E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,753.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="064" name="sl">
			   <label for="064"></label>
			   <img src="parte2/28_01_07.png"/>
			   <figcaption>Na segunda iteração, precisamos atualizar a taxa de aprendizagem: &alpha; = &alpha;.0,99. O primeiro padrão (-1, -1) é apresentado à rede, com atualização automática dos pesos.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="065" name="sl">
			   <label for="065"></label>
			   <img src="parte2/28_01_08.png"/>
			   <figcaption>No final da 7&ordf;  iteração, temos esta configuração de pesos. O erro nesta iteração é E = &sum;<sub>k</sub>((d<sub>k</sub> - y)<sup>2</sup>)/2 = 0,523.</figcaption>
		   </li>
		</ul>
		<img src="parte2/28_01_07.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte2/apostila_2020_20_40_0028a.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0029.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0030.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0031.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0032.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0033.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0034.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p> 
  <img src="parte2/apostila_2020_20_40_0035.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0036.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0037.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0038.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0039.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
  <img src="parte2/apostila_2020_20_40_0040.png"/>
   <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte3">SVM, RBF e Hebb</summary>
  <p>Material da página 40 até a página 52.</p>
  <img src="parte3/apostila_2020_20_40_0040.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00041.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00042.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00043.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício de Support Vector Machine (SVM). A rede deve separar os dados de entrada em duas classes.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="066" name="sl">
			   <label for="066"></label>
			   <img src="parte3/43_01_00.png"/>
			   <figcaption>Utilizando a função de núcleo (1 + x<sup>T</sup>x), temos o problema de Programação Quadrática apresentado. Os valores de &alpha;<sub>i</sub> diferentes de zero nos mostram quais serão os vetores suporte: 2, 4 e 6.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="067" name="sl">
			   <label for="067"></label>
			   <img src="parte3/43_01_01.png"/>
			   <figcaption>Substituindo os valores de x na função de decisão, encontramos a função de 2&ordm; grau. A parábola faz a separação dos dados nas classes 1 e 2.</figcaption>
		   </li>
		</ul>
		<img src="parte3/43_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00044.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os resultados e as interpretações geométricas deste exercício de Support Vector Machine (SVM). A rede deve separar os dados de entrada em duas classes.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="068" name="sl">
			   <label for="068"></label>
			   <img src="parte3/44_01_00.png"/>
			   <figcaption>Utilizando a função de núcleo (1 + x<sup>T</sup>x), precisamos desenvolvê-la para inserir os dados de entrada das variáveis x<sub>1</sub> e x<sub>2</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="069" name="sl">
			   <label for="069"></label>
			   <img src="parte3/44_01_01.png"/>
			   <figcaption>Substituindo os valores de x<sub>1</sub> e x<sub>2</sub> na função de decisão, encontramos os vetores de decisão.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="070" name="sl">
			   <label for="070"></label>
			   <img src="parte3/44_01_02.png"/>
			   <figcaption>Resolvendo o problema de programação quadrática, todas as variáveis de decisão ficam com os respectivos valores $\mathsf{\alpha_i = {1 \over 8}}$, ou seja, todas as variáveis representam vetores suportes. Substituindo estes valores, temos o vetor w.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="071" name="sl">
			   <label for="071"></label>
			   <img src="parte3/44_01_03.png"/>
			   <figcaption>A função decisão fica representada por f(x) = &minus;x<sub>1</sub>x<sub>2</sub>. Todos os dados de entrada ficam classificados corretamente com a SVM apresentada.</figcaption>
		   </li>
		</ul>
		<img src="parte3/44_01_00.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00044a.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00045.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00046.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00047.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00048.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Neural de bases radiais (RBF):
<pre><code>0. Considere uma base de dados (x<sub>i</sub>, d<sub>i</sub>), i = 1, 2,..., p, onde x<sub>i</sub> é um exemplo da base de dados 
   e d é o vetor de saídas desejadas correspondentes.
1. Defina o número <a alt="centros das bases radiais">q de neurônios ocultos (bases radiais)</a>, em geral escolhe-se q &le; n. 
   Selecione aleatoriamente q exemplos do conjunto de dados, e faça a seguinte atribuição:
   u<sub>j</sub> = x<sub>j</sub>, j = 1, 2,..., q.
2. Especifique <a alt="raios das bases radiais">o(s) valor(es) do(s) raio(s) da função de base radial</a>, &sigma;<sub>j</sub>. 
   Cada neurônio pode ter um raio diferente, para termos maior diversificação da RBF.
3. Para cada exemplo da base de dados x<sub>i</sub>, onde i = 1, 2, ..., p, execute os passos 4 e 5:
	4. Calcule <a alt="função gaussiana de cada neurônio">a ativação de cada neurônio j</a> da camada escondida:
	   &phiv;<sub>j</sub> = e<sup>-1/(2&sigma;<sup>2</sup>)‖x<sub>i</sub>&minus;u<sub>j</sub>‖<sup>2</sup></sup> 
	5. <a alt="matriz G das ativações dos neurônios">Atribua os valores das ativações dos neurônios</a> na matriz G:
	   G<sub>i,j</sub> = &phiv;<sub>j</sub>, e G<sub>i,q+1</sub> = &theta;
6. Após a apresentação de todos os exemplos, <a alt="vetor de pesos">calcule os pesos da saída:</a>
   w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d
<a alt="dedução do cálculo para o vetor de pesos">Temos essa expressão de w, pois:</a>
   Gw = d  &rArr;  G<sup>T</sup>Gw = G<sup>T</sup>d  &rArr;  (G<sup>T</sup>G)<sup>-1</sup>(G<sup>T</sup>G)w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d  &rArr;  w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d.
7. <a alt="saída da rede">Calcule a saída de cada exemplo:</a> y<sub>k</sub> = &sum;<sub>j=1</sub><sup>q+1</sup>w<sub>jk</sub>&phiv;<sub>j</sub>. Calcule o erro de classificação.

</code></pre></figcaption>
   </details></div>
  <img src="parte3/apostila_2020_40_52_00048a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões com a rede neural Radial Basis Function (RBF). A rede deve separar os dados de entrada em duas classes usando 2 centros.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="072" name="sl">
			   <label for="072"></label>
			   <img src="parte3/48_01_00.png"/>
			   <figcaption>Vamos começar com a apresentação do padrão de entrada (x<sub>1</sub>, x<sub>2</sub>) = (0, 2), com &sigma; = $\mathsf{\sqrt {0,5}}$. O resultado da ativação de cada neurônio da camada escondida será guardado na primeira linha da matriz G: g<sub>1</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="073" name="sl">
			   <label for="073"></label>
			   <img src="parte3/48_01_01.png"/>
			   <figcaption>Agora temos as apresentações dos padrões de entrada (1, 2) e (1, 3). O resultado da ativação de cada neurônio da camada escondida será guardado nas linhas da matriz G: g<sub>2</sub> e g<sub>3</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="074" name="sl">
			   <label for="074"></label>
			   <img src="parte3/48_01_02.png"/>
			   <figcaption>Agora temos as apresentações dos padrões de entrada (1, 0) e (2, 1). O resultado da ativação de cada neurônio da camada escondida será guardado nas linhas da matriz G: g<sub>4</sub> e g<sub>5</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="075" name="sl">
			   <label for="075"></label>
			   <img src="parte3/48_01_03.png"/>
			   <figcaption>Agora podemos calcular o vetor de pesos usando a matriz G. Note que a terceira coluna desta matriz tem valores iguais a 1, pois são as ativações de &theta;. Temos o vetor de pesos calculado da seguinte maneira: w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="076" name="sl">
			   <label for="076"></label>
			   <img src="parte3/48_01_04.png"/>
			   <figcaption>Podemos calcular as saídas e os erros quadráticos desta rede para os dois primeiros padrões de entrada: y = w<sub>1</sub>&phiv;<sub>1</sub> + w<sub>2</sub>&phiv;<sub>2</sub> + &theta; e E<sub>k</sub> = (d<sub>k</sub> &minus; y)<sup>2</sup>)/2.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="077" name="sl">
			   <label for="077"></label>
			   <img src="parte3/48_01_05.png"/>
			   <figcaption>Seguem os cálculos das saídas e os erros quadráticos desta rede mais dois padrões de entrada.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="078" name="sl">
			   <label for="078"></label>
			   <img src="parte3/48_01_06.png"/>
			   <figcaption>Para finalizar, são mostrados os cáculos da saída e do erro quadrático da rede para o último padrão de entrada. O erro quadrático total desta RBF ficou em E = 0,219.</figcaption>
		   </li>
		</ul>
		<img src="parte3/48_01_00.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00048b.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões com a rede neural Radial Basis Function (RBF). A rede deve separar os dados de entrada em duas classes com 3 centros.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="079" name="sl">
			   <label for="079"></label>
			   <img src="parte3/48_02_01.png"/>
			   <figcaption>Vamos começar com a apresentação do padrão de entrada (x<sub>1</sub>, x<sub>2</sub>) = (0, 2), com &sigma; = $\mathsf{\sqrt {0,5}}$. O resultado da ativação de cada neurônio da camada escondida será guardado na primeira linha da matriz G: g<sub>1</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="080" name="sl">
			   <label for="080"></label>
			   <img src="parte3/48_02_02.png"/>
			   <figcaption>Agora temos as apresentações dos padrões de entrada (1, 2) e (1, 3). O resultado da ativação de cada neurônio da camada escondida será guardado nas linhas da matriz G: g<sub>2</sub> e g<sub>3</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="081" name="sl">
			   <label for="081"></label>
			   <img src="parte3/48_02_03.png"/>
			   <figcaption>Agora temos as apresentações dos padrões de entrada (1, 0) e (2, 1). O resultado da ativação de cada neurônio da camada escondida será guardado nas linhas da matriz G: g<sub>4</sub> e g<sub>5</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="082" name="sl">
			   <label for="082"></label>
			   <img src="parte3/48_02_04.png"/>
			   <figcaption>Agora podemos calcular o vetor de pesos usando a matriz G. Note que a quarta coluna desta matriz tem valores iguais a 1, pois são as ativações de &theta;. Temos o vetor de pesos calculado da seguinte maneira: w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="083" name="sl">
			   <label for="083"></label>
			   <img src="parte3/48_02_05.png"/>
			   <figcaption>Podemos calcular as saídas e os erros quadráticos desta rede para os dois primeiros padrões de entrada: y = w<sub>1</sub>&phiv;<sub>1</sub> + w<sub>2</sub>&phiv;<sub>2</sub> + w<sub>3</sub>&phiv;<sub>3</sub> + &theta; e E<sub>k</sub> = (d<sub>k</sub> &minus; y)<sup>2</sup>)/2.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="084" name="sl">
			   <label for="084"></label>
			   <img src="parte3/48_02_06.png"/>
			   <figcaption>Seguem os cálculos das saídas e os erros quadráticos desta rede mais dois padrões de entrada.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="085" name="sl">
			   <label for="085"></label>
			   <img src="parte3/48_02_07.png"/>
			   <figcaption>Para finalizar, são mostrados os cáculos da saída e do erro quadrático da rede para o último padrão de entrada. O erro quadrático total desta RBF ficou em E = 0,0057.</figcaption>
		   </li>
		</ul>
		<img src="parte3/48_02_03.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00048c.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões da função "OU EXCLUSIVO" com a rede neural Radial Basis Function (RBF). Vamos utilizar 2 centros.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="086" name="sl">
			   <label for="086"></label>
			   <img src="parte3/48_03_01.png"/>
			   <figcaption>Vamos começar com a apresentação dos padrões de entrada (x<sub>1</sub>, x<sub>2</sub>) = (1, 1) e (-1, 1), com &sigma; = $\mathsf{\sqrt {0,5}}$. O resultado da ativação de cada neurônio da camada escondida será guardado nas duas primeiras linha da matriz G: g<sub>1</sub> e g<sub>2</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="087" name="sl">
			   <label for="087"></label>
			   <img src="parte3/48_03_02.png"/>
			   <figcaption>Agora temos as apresentações dos padrões de entrada (-1, -1) e (1, -1). O resultado da ativação de cada neurônio da camada escondida será guardado nas linhas da matriz G: g<sub>3</sub> e g<sub>4</sub>.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="088" name="sl">
			   <label for="088"></label>
			   <img src="parte3/48_03_03.png"/>
			   <figcaption>Agora podemos calcular o vetor de pesos usando a matriz G. Note que a terceira coluna desta matriz tem valores iguais a 1, pois são as ativações de &theta;. Temos o vetor de pesos calculado da seguinte maneira: w = (G<sup>T</sup>G)<sup>-1</sup>G<sup>T</sup>d.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="089" name="sl">
			   <label for="089"></label>
			   <img src="parte3/48_03_04.png"/>
			   <figcaption>Podemos calcular as saídas e os erros quadráticos desta rede para os dois primeiros padrões de entrada: y = w<sub>1</sub>&phiv;<sub>1</sub> + w<sub>2</sub>&phiv;<sub>2</sub> + &theta; e E<sub>k</sub> = (d<sub>k</sub> &minus; y)<sup>2</sup>)/2.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="090" name="sl">
			   <label for="090"></label>
			   <img src="parte3/48_03_05.png"/>
			   <figcaption>Temos que o erro é igual a ZERO para este problema de classificação usando a RBF de 2 centros.</figcaption>
		   </li>
		</ul>
		<img src="parte3/48_03_03.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00048d.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00049.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00050.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Neural de Hebb:
<pre><code>0. <a alt="pesos iniciam nulos">Inicialize os pesos w<sub>i</sub> = 0</a>, onde i = 1, 2, ..., n
	1. <a alt="atualização de pesos parecida com a do Perceptron">Para cada par de treinamento (x,d),</a> faça:
	2. w<sub>i</sub><sup>atual</sup> = w<sub>i</sub><sup>anterior</sup> + &alpha;x<sub>i</sub>d<sub>i</sub> 
	   &theta;<sub>i</sub><sup>atual</sup> = &theta;<sub>i</sub><sup>anterior</sup> + &alpha;d<sub>i</sub> 
	3. <a alt="calculamos a saída y*">Faça y* = w<sub>i</sub>x<sub>i</sub> + &theta;,</a> onde i = 1, 2, ..., n
4. <a alt="teste de convergência similar ao que usamos no Perceptron e MLP">Teste a convergência.</a> Se necessário, repita os passos 1-3.

</code></pre></figcaption>
   </details></div>
  <img src="parte3/apostila_2020_40_52_00050a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões da função "OU" com a rede neural de Hebb, com &alpha; = 1.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="091" name="sl">
			   <label for="091"></label>
			   <img src="parte3/50_01_01.png"/>
			   <figcaption>Vamos começar com a apresentação dos padrões de entrada (x<sub>1</sub>, x<sub>2</sub>) = (1, 1) e (1, -1) para a rede. As atualizações dos pesos são automáticas e produzem o vetor (w<sub>1</sub>, w<sub>2</sub>, &theta;) = (2, 0, 2).</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="092" name="sl">
			   <label for="092"></label>
			   <img src="parte3/50_01_02.png"/>
			   <figcaption>Continuando a apresentação dos padrões de entrada: (-1, 1) e (-1, -1). As atualizações dos pesos produzem o vetor (w<sub>1</sub>, w<sub>2</sub>, &theta;) = (2, 2, 2).</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="093" name="sl">
			   <label for="093"></label>
			   <img src="parte3/50_01_03.png"/>
			   <figcaption>Ao final da 1&ordf; iteração, temos todos os padrões classificados corretamente. Logo, o treinamento pode ser finalizado.</figcaption>
		   </li>
		</ul>
		<img src="parte3/50_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00050b.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões com a rede neural de Hebb, com &alpha; = 1. Precisamos deixar os padrões de entrada no intervalo [-1, 1] para que a rede de Hebb funcione adequadamente.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="094" name="sl">
			   <label for="094"></label>
			   <img src="parte3/50_02_01.png"/>
			   <figcaption>Vamos começar com a apresentação dos padrões de entrada (x<sub>1</sub>, x<sub>2</sub>) = (-1, 0.33) e (-0.33, 0.33) para a rede. As atualizações dos pesos são automáticas e produzem o vetor (w<sub>1</sub>, w<sub>2</sub>, &theta;) = (-1.33, 0.66, 2).</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="095" name="sl">
			   <label for="095"></label>
			   <img src="parte3/50_02_02.png"/>
			   <figcaption>Continuando a apresentação dos padrões de entrada: (-0.33, 1) e (-0.33, -1). As atualizações dos pesos produzem o vetor (w<sub>1</sub>, w<sub>2</sub>, &theta;) = (-1.33, 2.66, 2).</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="096" name="sl">
			   <label for="096"></label>
			   <img src="parte3/50_02_03.png"/>
			   <figcaption>Ao final da 1&ordf; iteração, o vetor de pesos (w<sub>1</sub>, w<sub>2</sub>, &theta;) = (-1.66, 2.99, 1). Todos os padrões são classificados corretamente, e o treinamento da rede pode ser finalizado.</figcaption>
		   </li>
		</ul>
		<img src="parte3/50_02_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00050c.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00051.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
  <img src="parte3/apostila_2020_40_52_00052.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Algoritmo comentado</summary>
   <figcaption>Algoritmo da Rede Heteroassociativa:
<pre><code>0. <a alt="pesos iniciam nulos">Inicialize os pesos w<sub>ij</sub> = 0</a>, onde i = 1, 2, ..., n, j = 1, 2, ..., m.
	1. Para cada par de treinamento (x,d),</a> faça os passos 2-4:
	2. <a alt="calculamos a saída y*">y<sub>j</sub>* = &sum;<sub>i</sub>x<sub>i</sub>w<sub>ij</sub></a>
	3. <a alt="calculamos a saída y">Se y<sub>j</sub>* &gt; 0</a>, y<sub>j</sub> = 1
	   Se y<sub>j</sub>* = 0, y<sub>j</sub> = 0
	   Se y<sub>j</sub>* &lt; 0, y<sub>j</sub> = -1
	4. <a alt="atualização de pesos parecida com a do Perceptron">w<sub>ij</sub><sup>atual</sup> = w<sub>ij</sub><sup>anterior</sup> + &alpha;x<sub>i</sub>d<sub>i</sub></a> 
5. <a alt="teste de convergência similar ao que usamos no Perceptron e MLP">Reduza &alpha; e teste a convergência.</a> Se necessário, repita os passos de 1-4.

</code></pre></figcaption>
   </details></div>
  <img src="parte3/apostila_2020_40_52_00052a.png"/>
  <div class="combo"><details class="sub"><summary>&#x1f4c3; Resolução</summary>
	<p>Vamos acompanhar os cálculos deste exercício de classificação de padrões com a rede neural Heteroassociativa, com &alpha; = 1.</p>
	  <ul class="slider">
		  <li>
			   <input type="radio" id="097" name="sl">
			   <label for="097"></label>
			   <img src="parte3/52_01_01.png"/>
			   <figcaption>Vamos começar com a apresentação dos padrões de entrada (x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub>, x<sub>4</sub>) = (1, 0, 0, 0) e (1, 1, 0, 0) para a rede. As atualizações dos pesos são automáticas e produzem a matriz de pesos indicada w<sub>ij</sub>, com i = 1, 2, 3, 4 e j = 1, 2.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="098" name="sl">
			   <label for="098"></label>
			   <img src="parte3/52_01_02.png"/>
			   <figcaption>Continuando a apresentação dos padrões de entrada: (0, 0, 0 ,1) e (0, 0, 1, 1). As atualizações dos pesos produzem a matriz de pesos indicada w<sub>ij</sub>, com i = 1, 2, 3, 4 e j = 1, 2.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="099" name="sl">
			   <label for="099"></label>
			   <img src="parte3/52_01_03.png"/>
			   <figcaption>Multiplicando-se a matriz de pesos W pelos vetores dos dados de entrada, temos o reconhecimento destes padrões. O processo de treinamento desta rede pode ser finalizado.</figcaption>
		   </li>
		</ul>
		<img src="parte3/52_01_01.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte3/apostila_2020_40_52_00052b.png"/>
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte4">Mapas auto-organizáveis</summary>
  <p>Material da página 53 até a página 66.</p>
  <img src="parte4/apostila_2020_53_81_00053.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00054.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00055.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00056.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00057.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00058.png"/>
  <img src="parte4/apostila_2020_53_81_00058a.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00059.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00060.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00061.png"/>
  <img src="parte4/apostila_2020_53_81_00061a.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00062.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00063.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00064.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00065.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
  <img src="parte4/apostila_2020_53_81_00066.png"/>
  <img src="parte4/apostila_2020_53_81_00066a.png"/>
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte5">Redes Temporais</summary>
  <p>Material da página 66 até a página 81.</p>
  <img src="parte5/apostila_2020_53_81_00066.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00067.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00068.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00069.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00070.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00071.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00072.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00073.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00074.png"/>
  <img src="parte5/apostila_2020_53_81_00074a.png"/>
  <img src="parte5/apostila_2020_53_81_00074b.png"/>
  <img src="parte5/apostila_2020_53_81_00074c.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00075.png"/>
  <img src="parte5/apostila_2020_53_81_00075a.png"/>
  <img src="parte5/apostila_2020_53_81_00075b.png"/>
  <img src="parte5/apostila_2020_53_81_00075c.png"/>
  <img src="parte5/apostila_2020_53_81_00075d.png"/>
  <img src="parte5/apostila_2020_53_81_00075e.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00076.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00077.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00078.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00079.png"/>
  <img src="parte5/apostila_2020_53_81_00079a.png"/>
  <img src="parte5/apostila_2020_53_81_00079b.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
  <img src="parte5/apostila_2020_53_81_00080.png"/>
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
</details>
<h3>Outras Metaheurísticas</h3>
<details>
  <summary id="parte6">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte6" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte7">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte7" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte8">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte8" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte9">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte9" class="topo">voltar ao topo</a></p>
</details>

<details style="border-bottom: 1px solid #a2dec0;">
  <summary id="parte10">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte10" class="topo">voltar ao topo</a></p>
</details>

<h4>página desenvolvida por:</h4> 
<p>Paulo Henrique Siqueira</p>  
<p><b>contato:</b> paulohscwb@gmail.com </p>

<h4>O desenvolvimento deste material de construções geométricas faz parte do Grupo de Estudos em Expressão Gráfica (GEEGRAF) da Universidade Federal do Paraná (UFPR)</h4>  

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Licença Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png"/></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Metaheurísticas e Aplicações</span> de <a xmlns:cc="http://creativecommons.org/ns#" href="https://paulohscwb.github.io/ia/" property="cc:attributionName" rel="cc:attributionURL">Paulo Henrique Siqueira</a> está licenciado com uma Licença <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons - Atribuição-NãoComercial 4.0 Internacional</a>.

<h4>Como citar este trabalho:</h4> 
<p>Siqueira, P.H., "Metaheurísticas e Aplicações". Disponível em: <https://paulohscwb.github.io/ia/>, Janeiro de 2021.</p>

<h4>Referências:</h4>
<ol>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
	<li></li>
<ol>