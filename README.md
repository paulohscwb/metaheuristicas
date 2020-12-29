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
  <summary id="parte1">Redes Neurais Artificiais</summary>
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
6. Teste a condição de parada.</code></pre></figcaption>
   </details></div>
   <img src="parte1/apostila_2020_1_19_0009a.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0010.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
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
			   <input type="radio" id="002" name="sl" checked>
			   <label for="002"></label>
			   <img src="parte1/10_01_01.png"/>
			   <figcaption>Os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; definem as equações das retas usadas para a classificação. O parâmetro &delta; cria uma região de indefinição para a classificação.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="003" name="sl" checked>
			   <label for="003"></label>
			   <img src="parte1/10_01_03.png"/>
			   <figcaption>Apresentação do segundo padrão para a rede (1, 0). Como y = &theta; + x<sub>1</sub>w<sub>1</sub> + x<sub>2</sub>w<sub>2</sub> = 1 + 1.1 + 0.1 = 2 &ne; d = -1, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="004" name="sl" checked>
			   <label for="004"></label>
			   <img src="parte1/10_01_03.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="005" name="sl" checked>
			   <label for="005"></label>
			   <img src="parte1/10_01_05.png"/>
			   <figcaption>Apresentação do terceiro padrão para a rede (0, 1). Como y &ne; d, então os pesos são atualizados. Como os coeficientes das variáveis x<sub>1</sub> e x<sub>2</sub> ficaram nulos, não temos a interpretação geométrica nesta apresentação de padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="006" name="sl" checked>
			   <label for="006"></label>
			   <img src="parte1/10_01_05.png"/>
			   <figcaption>Apresentação do último padrão para a rede (0, 0). Como y = d, então os pesos são mantidos. Usando esta combinação de pesos, podemos calcular o erro da primeira iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="006a" name="sl" checked>
			   <label for="006a"></label>
			   <img src="parte1/10_01_06a.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 0, w<sub>2</sub> = 0, &theta; = 1) da última apresentação de padrões para calcular o erro. Apenas o último padrão está classificado corretamente: logo, o erro quantitativo nesta primeira iteração é de 75%.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="007" name="sl" checked>
			   <label for="007"></label>
			   <img src="parte1/10_01_07.png"/>
			   <figcaption>Recomeçamos a apresentação de cada padrão para a rede na próxima iteração. O primeiro padrão (1, 1) é apresentado à rede, com a combinação de parâmetros (0, 0, 1). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="008" name="sl" checked>
			   <label for="008"></label>
			   <img src="parte1/10_01_07.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="009" name="sl" checked>
			   <label for="009"></label>
			   <img src="parte1/10_01_09.png"/>
			   <figcaption>Apresentação do segundo padrão para a rede (1, 0). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="010" name="sl" checked>
			   <label for="010"></label>
			   <img src="parte1/10_01_10.png"/>
			   <figcaption>Note que as equações definidas com os coeficientes de w<sub>1</sub>, w<sub>2</sub> e &theta; ainda não classificam corretamente todos dos padrões.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="011" name="sl" checked>
			   <label for="011"></label>
			   <img src="parte1/10_01_11.png"/>
			   <figcaption>Apresentação do terceiro padrão para a rede (0, 1). Como y &ne; d, então os pesos são atualizados.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="012" name="sl" checked>
			   <label for="012"></label>
			   <img src="parte1/10_01_12.png"/>
			   <figcaption>Apresentação do último padrão para a rede (0, 0). Como y = d, então os pesos são mantidos. Usando esta combinação de pesos, podemos calcular o erro da segunda iteração.</figcaption>
		   </li>
		   <li>
			   <input type="radio" id="012a" name="sl" checked>
			   <label for="012a"></label>
			   <img src="parte1/10_01_12a.png"/>
			   <figcaption>Usamos a combinação de pesos (w<sub>1</sub> = 0, w<sub>2</sub> = 0, &theta; = -2) da última apresentação de padrões para calcular o erro. Apenas o último padrão está classificado corretamente: logo, o erro quantitativo nesta primeira iteração é de 75%.</figcaption>
		   </li>
		</ul>
		<img src="parte1/10_01_02.png" class="fundo" style="visibility:hidden"/>
  </details></div>
  <img src="parte1/apostila_2020_1_19_0010a.png"/>
  <img src="parte1/apostila_2020_1_19_0010b.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0011.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0012.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
   <img src="parte1/apostila_2020_1_19_0013.png"/>
  <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0014.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0015.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0016.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0017.png"/>
   <p class="topop"><a href="#parte1" class="topo">voltar ao topo</a></p>
  <img src="parte1/apostila_2020_1_19_0018.png"/>
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