# QuantitativeAnalysisProject
This project has the goal to analyze the correlation between return of the stocks AMZN, GOOGL and WMT. 


## Introduction
Como referência, foi utilizada a data de 9 de outubro de 2025. Serão analisadas as ações da Amazon (AMZN), Walmart (WMT) e Google (GOOGL). O estudo contou com quatro análises:
- 1. Cálculo do Beta da Amazon em relação ao S&P 500
- 2. Correlação entre Amazon Walmart e Google e teste de significância
- 3. Análise Fundamental
- 4. Volatilidade e Risco


## 1. Beta

O fator beta é um indicador que pode medir a volatilidade de um ativo em relação a uma outra variável. Para calculá-lo foram utilizados duas metodologias:

Método 1: cálculo baseado na relação estatística
<p>
$$
  \beta = \frac{covariance(r_{1},r_{2})}{variance(r_{1})}
$$
</p>


Método 2: cálculo do coeficiente angular da regressão linear
<br>
<p>

<img width="721" height="448" alt="image" src="https://github.com/user-attachments/assets/9ce73a73-d47e-4bb9-ac28-1029f381a6c7" />


## Cálculo de Correlação

Para as análises assumimos o período de 5 anos de série histórica como feito no item anterior.
<br>
A correlação (𝜌) foi calculada conforme a fórmula. Foi utilizado também o método .corr() do pandas, para comparação.
<p>
<p>
$$
\rho = \frac{Cov(x_{1},x_{2})}{σ_{1}*σ{2}}
$$
<p>

*Correlação entre os ativos:*
 Ticker | AMZN | WMT | GOOGL
--- | --- | --- | ---
AMZN | 1.000000 | 0.268064 | 0.616656
WMT |  0.268064 | 1.000000 | 0.202805
GOOGL | 0.616656 | 0.202805 | 1.000000 

### Interpretação da correlação

Geramos duas hipóteses, a hipótese nula e a hipótese alternativa
Para testar as hipóteses de correlação foram feitos os testes t e o teste do p-valor.
O objetivo dos testes é verificar se a análise tem significância estatística linear.
Os resultados indicam que ambas as correlações são estatisticamente significativas (p < 0,05), portanto, não ocorrem por acaso.

* Amazon × Walmart: r=0.43, t=3.68, p = 0.00031 → há uma correlação positiva moderada, mostrando que os retornos das duas empresas tendem a se mover na mesma direção, embora não de forma muito forte.

* Amazon × Google:
r=0.77, t = 10.36, p≈0.00000 → existe uma correlação positiva forte e altamente significativa, indicando que os preços das ações variam de maneira bastante semelhante.

Assim, conclui-se que os retornos da Amazon estão claramente relacionados aos de ambas as empresas, mas a relação é muito mais intensa com o Google. Podemos concluir que as ações se comportam de forma semelhante



## 3. Análise Fundamental

A Amazon atua em dois segmentos principais: serviços de computação em nuvem (AWS) e comércio eletrônico. Essa diversificação posiciona a empresa em um ponto de interseção entre setores distintos, competindo tanto com o Walmart, no varejo digital, quanto com o Google e outras big techs, no setor de tecnologia e infraestrutura em nuvem.

Na análise de correlações entre retornos de ações, observou-se que os retornos da Amazon e da Google apresentam alta correlação, evidenciando que ambas as empresas tendem a seguir tendências semelhantes de valorização e desvalorização. Essa relação indica que o desempenho de mercado da Amazon está mais fortemente associado ao segmento tecnológico, especialmente aos serviços de cloud computing e publicidade digital, do que às atividades puramente de varejo. A análise de significância estatística reforça essa conclusão, mostrando que a relação entre Amazon e Google é consistente e relevante do ponto de vista estatístico e econômico.

Por outro lado, a correlação entre Amazon e Walmart, embora positiva, mostrou-se menos intensa, refletindo a diferença estrutural entre os modelos de negócio. Enquanto o Walmart mantém foco predominante no varejo físico e na eficiência logística, a Amazon tem ampliado suas receitas e margens por meio da tecnologia, serviços de assinatura e infraestrutura digital, que apresentam dinâmicas de mercado distintas.

O beta da Amazon, estimado em 1,36, indica alta sensibilidade em relação ao mercado (S&P 500). Isso significa que, em períodos de valorização do índice, a Amazon tende a apresentar ganhos superiores à média, enquanto em momentos de queda generalizada, sofre desvalorizações mais acentuadas.

Em resumo, a análise demonstra que o desempenho da Amazon está mais alinhado às tendências do setor de tecnologia do que ao varejo tradicional, o que reforça sua natureza híbrida — uma companhia que, apesar de forte no e-commerce, é hoje impulsionada pelos resultados da AWS e dos serviços digitais.



## 4. Análise de Volatilidade

Foi calculada a volatilidade diária média dos últimos 5 anos, que corresponde ao desvio padrão da série histórica. Mas para a análise de risco foi analisada a volatilidade anual pois faria mais sentido para comparar análises de longo prazo, para assim decidir qual é mais arriscada.


Ticker | Volatilidade média diária
--- | ---
AMZN | 0.022069
GOOGL | 0.019539
WMT | 0.012921

Ticker | Volatilidade média anual
--- | ---
AMZN | 0.350341
GOOGL | 0.310167
WMT | 0.205113

## Conclusões

Com base nos valores calculados, observa-se que a Amazon apresenta a maior volatilidade média dos retornos nos últimos cinco anos. Além disso, seu beta elevado indica maior sensibilidade ao desempenho do mercado, especialmente ao movimento do S&P 500. Em conjunto, esses fatores evidenciam que a Amazon possui o nível de risco mais elevado entre as empresas analisadas.
Sua atuação em setores como tecnologia, computação em nuvem e e-commerce, faz com que seus retornos sejam fortemente impactados por mudanças nas condições macroeconômicas e nas expectativas de crescimento global.

Em contraste, o Walmart apresenta um perfil mais estável, caracterizado por menor volatilidade.
Já a Google ocupa uma posição intermediária resultando em um risco moderado.

Apesar de ser uma métrica central para avaliar o comportamento dos retornos, a volatilidade não deve ser analisada isoladamente. Outros elementos também influenciam o risco de uma empresa, como:

* Riscos sistemáticos de mercado, refletidos pelo beta e pelas condições macroeconômicas;
* Riscos financeiros, associados à estrutura de capital e à alavancagem;
* Riscos operacionais e regulatórios, decorrentes de mudanças legais, concorrência e inovação tecnológica.

Portanto, a avaliação de risco deve integrar tanto indicadores quantitativos (como volatilidade e beta) quanto aspectos qualitativos relacionados à gestão, competitividade e fundamentos econômicos da empresa.


## References
1. https://algotrading101.com/learn/yahoo-finance-api-guide/
2. https://pages.stern.nyu.edu/~adamodar/podcasts/cfspr20/session7slides.pdf
3. https://www.investopedia.com/terms/c/correlationcoefficient.asp
4. https://en.wikipedia.org/wiki/Pearson_correlation_coefficient
