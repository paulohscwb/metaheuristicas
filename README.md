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

<details>
  <summary id="parte1">Redes Neurais Artificiais - Perceptron e Adaline</summary>
  <p>Material da página 1 até a página xx.</p>
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
			   <figcaption>A arquitetura da Rede Neural fica análoga à arquitetura que usamos no caso do Perceptron. O resumo dos cálculos está mostrado nesta imagem. Vamos inicializar com os pesos indicados de w e &theta; e a taxa de aprendizagem &alpha;.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="026" name="sl">
			   <label for="026"></label>
			   <img src="parte1/18_01_02.png"/>
			   <figcaption>O primeiro padrão (1, 1) é apresentado à rede, com a atualização automática dos pesos. Por exemplo, &delta;w<sub>1</sub> = &alpha;(d - y*).x<sub>1</sub> = 0,5.(1 - 0,8).1 = 0,5.0,2 = 0,1. Logo, w<sub>1</sub> = w<sub>1</sub> + &delta;w<sub>1</sub> = 0,3 + 0,1 = 0,4.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="026a" name="sl">
			   <label for="026a"></label>
			   <img src="parte1/18_01_02.png"/>
			   <figcaption>Os cálculos dos demais pesos são feitos analogamente. Usando os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; que definem a equação da reta usada para a classificação, temos 2 padrões classificados corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="027" name="sl">
			   <label for="027"></label>
			   <img src="parte1/18_01_03.png"/>
			   <figcaption>O padrão (1, -1) é apresentado à rede, com a atualização automática dos pesos. A reta com os coeficientes dos pesos classifica 2 padrões corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="028" name="sl">
			   <label for="028"></label>
			   <img src="parte1/18_01_04.png"/>
			   <figcaption>O padrão (-1, 1) é apresentado à rede, com a atualização automática dos pesos. A reta com os coeficientes dos pesos classifica 3 padrões corretamente.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="029" name="sl">
			   <label for="029"></label>
			   <img src="parte1/18_01_05.png"/>
			   <figcaption>O padrão (-1, -1) é apresentado à rede, com a atualização automática dos pesos. A reta com os coeficientes dos pesos classifica todos os padrões corretamente.</figcaption>
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
  <summary id="parte2">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte2" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte3">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte3" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte4">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte4" class="topo">voltar ao topo</a></p>
</details>

<details>
  <summary id="parte5">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte5" class="topo">voltar ao topo</a></p>
</details>

<details style="border-bottom: 1px solid #a2dec0;">
  <summary id="parte6">Título</summary>
  <p>Material da página xx até a página xxx.</p>
  
  <p class="topop"><a href="#parte6" class="topo">voltar ao topo</a></p>
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