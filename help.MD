# Documentação Métricas

## Proporção  de types de  pronomes relativos  em relação à quantidade de tokens de  pronomes relativos no texto 

**Nome da Métrica**: relative_pronouns_diversity_ratio

**Interpretação**: pronomes relativos introduzem orações subordinadas adjetivas, substantivas e adverbiais, que expandem o conteúdo de um sintagma nominal e aumentam a complexidade textual. Sua forma mais simples é o “que”. Se houver uso de outros pronomes relativos, a complexidade textual aumenta.

**Descrição da métrica**: Proporção de types de pronomes relativos  em relação à quantidade de tokens de  pronomes relativos no texto 

**Definição dos termos que aparecem na descrição da métrica**: pronomes relativos retomam e qualificam um nome que os antecedem. Suas formas são: que, o que, o qual, os quais, a qual, as quais, cujo, cujos, cuja, cujas, quem, quando, onde, como, quanto, quantos, quanta, quantas. Muitos deles são ambíguos funcionalmente (podem atuar como outro tipo de pronome), por isso a etiqueta <rel> é importante para capturar apenas aqueles com função relativa.

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta <rel>, sem considerar repetições; divide-se o resultado pela soma de todas as ocorrências da etiqueta <rel> do texto, considerando as repetições.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: A escola na qual estudo é muito rigorosa, mas os professores que dão aula para mim são muito bons. A professora de gramática, a qual dá aula para mim desde o sexto ano, tem uma didática fantástica. 

**Contagens**: 3 pronomes relativos ((em) a qual, que, a qual ), dos quais 2 sem considerar repetições.

**Resultado Esperado**: 2/3 = 0,667

**Resultado Obtido**: 0,667 

**Status**: correto




## Proporção de conjunções difíceis em relação à quantidade de palavras do texto




**Nome da Métrica**: hard_conjunctions_ratio

**Interpretação**: quanto maior a métrica, maior a complexidade textual

**Descrição da métrica**: Proporção de conjunções difíceis em relação a todas as palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: “conjunções difíceis” é uma das categorias atribuídas por Lívia Cucato, linguista da GUTEN, a um conjunto de conjunções. A lista conjuncoes_fund_2 é de conjunções difíceis e a lista conjuncoes_fund_1 é de conjunções fáceis. As duas listas incluem tanto conjunções constituídas de uma única palavra quanto locuções conjuntivas (ou seja, duas ou mais palavras que funcionam como uma conjunção, como por exemplo: “a fim de que” (conjunção final), “cada vez que” (conjunção temporal) “se bem que” (conjunção concessiva)). A lista conjunções_fund_2 é composta das seguintes palavras e expressões: todavia, eis, a fim de, ao passo que, para que, conforme, tais, ou seja, contudo, bem como, logo, à medida que, entretanto, desde que, mesmo que, ainda que, de acordo com, uma vez que, por sua vez, sobretudo, até, ainda, caso, no entanto, nem, quanto, já, como, já que, outrossim, mas também, como também, não só, mas ainda, tampouco, senão também, bem assim, ademais, antes, não obstante, sem embargo, ao passo que, de outra forma, em todo caso, aliás, de outro modo, por conseguinte, em consequência de, por consequência, consequentemente, conseguintemente, isso posto, pelo que, de modo que, de maneira que, de forma que, em vista disso, por onde, porquanto, posto que, isto é, ademais, senão, dado que, visto como, vez que, de vez que, pois que, agora, na medida em que, sendo que, como que, como quer que, eis que, sendo assim, tal qual, ao invés de, conquanto, por muito que, visto que, uma vez que, quanto mais, quanto menos, se bem que, apesar de que, suposto que, ainda quando, quando mesmo, a despeito de, conquanto que, sem embargo de que, por outro lado,

em contrapartida, sem embargo, muito embora, inclusive se, por mais que, por menos que, por pouco que, contanto que, salvo se, com tal que, caso que, consoante, tal que, de forma que, à proporção que, ao passo que, mal, tão logo, entretanto, sob esse aspecto, sob esse prisma, sob esse ponto de vista, sob esse enfoque, embora, portanto, além disso.

**Forma de cálculo da métrica**: identificam-se as palavras do texto que estão na lista de “conjunções difíceis” e divide-se pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador NLTK

**Limitações da métrica**: 

**Crítica**:  

1) não se sabe como a lista de conjunções foi compilada, nem o critério para separar as conjunções fáceis das difíceis. Há advérbios e preposições misturados na lista, como “agora” e “até” e conjunções ambíguas com outras categorias gramaticais, como “mal”.

2) a proporção deveria ser calculada em relação ao total de conjunções, que é a classe à qual pertencem as conjunções difíceis.

**Projeto**: GUTEN

**Teste**: Visto que muitas pessoas saíram feridas, foi necessário tomar uma medida imediata a fim de neutralizar os danos causados e reverter a situação.

**Contagens**: 23 palavras e 2 conjunções difíceis (a fim de, visto que)

**Resultado Esperado**: 2/23 = 0,087

**Resultado Obtido**: 0,087 

**Status**: correto




## Proporção de conjunções fáceis em relação à quantidade de palavras do texto




**Nome da Métrica**: easy_conjunctions_ratio

**Interpretação**: quanto maior a métrica, menor a complexidade textual

**Descrição da métrica**: Proporção de conjunções fáceis em relação a todas as palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: “conjunções fáceis” é uma das categorias atribuídas por Lívia Cucato, linguista da GUTEN, a um conjunto de conjunções. A lista conjuncoes_fund_1 é de conjunções fáceis e a lista conjuncoes_fund_2 é de conjunções difíceis. As duas listas incluem tanto conjunções constituídas de uma única palavra quanto locuções conjuntivas (ou seja, duas ou mais palavras que funcionam como uma conjunção, como por exemplo: “a fim de que” (conjunção final), “cada vez que” (conjunção temporal) “se bem que” (conjunção concessiva)). A lista conjunções_fund_1 contém as seguintes palavras e expressões: como, se, mas, quando, ou, que, porque, e, assim, porém, caso, por isso que

por isso, por enquanto, enquanto isso, enquanto, pois, além de, então, daí, por exemplo, ou seja, sem que, para que, cada vez que, antes que, assim como, tanto quanto, feito, que nem, toda vez que, a não ser que, depois que, até que, na medida em que, desde, nem bem, tanto que, segundo, assim que, tanto que, tão que, sem que, ora. 

**Forma de cálculo da métrica**: identificam-se as palavras do texto que estão na lista de “conjunções fáceis” e divide-se pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador NLTK

**Limitações da métrica**: 

**Crítica**:  

1) A origem do léxico não está descrita. Nenhuma marca é usada para desambiguização é utilizada. Por exemplo, o particípio “feito” pode ter várias funções e só esporadicamente é usado como conjunção: “Ele chegou feito um foguete”. A ambiguidade afeta a estatística.

2) Os critérios para separar as conjunções fáceis das difíceis não são claros. Por exemplo, “além de” é considerada fácil e “além disso” é considerada difícil.

3) a proporção deveria ser calculada em relação ao total de conjunções, que é a classe à qual pertencem as conjunções fáceis; comparar com o total de palavras enfraquece a métrica.

**Projeto**: GUTEN

**Teste**: Eles brincaram o dia todo e foi muito divertido. Além de brincarem, fizeram muitos amigos.

**Contagens**: 15 palavras e 2 conjunções fáceis (e, além de)

**Resultado Esperado**: 2/15 = 0,133

**Resultado Obtido**: 0,133 

**Status**: correto




## Proporção de palavras de conteúdo simples em relação a todas palavras de conteúdo do texto





**Nome da Métrica**: simple_word_ratio 

**Interpretação**: quanto maior a Proporção, menor a complexidade do texto

**Descrição da métrica**: proporção de palavras de conteúdo simples, sobre o total de palavras de conteúdo do texto

**Definição dos termos que aparecem na descrição da métrica**:

**Palavras Simples**: são palavras de baixa complexidade. Atualmente é utilizada a lista de palavras do Dicionário de palavras simples de Maria Tereza Biderman.

**Palavras de Conteúdo**: são as palavras que pertencem às classes gramaticais abertas (infinitas) da língua, ou seja, substantivos, adjetivos, verbos e advérbios.

**Forma de cálculo da métrica**: Calcula-se a Proporção de palavras de conteúdo simples dividindo-se a quantidade de palavras de conteúdo simples do texto sobre o total de palavras de conteúdo do texto. Há dois contadores: um de palavras de conteúdo e um de palavras de conteúdo que estão na lista de palavras simples.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: a precisão do cálculo está condicionada à precisão dos recursos utilizados (lematizador, tagger e lista de palavras simples).

**Crítica**: usando o lema, todas as formas de um mesmo verbo que está na lista de palavras simples são automaticamente classificadas como simples. Isso não é o ideal, pois as diversas formas de um verbo têm diferentes níveis de complexidade.

**Projeto**: AIC

**Teste**: Mesmo assim, o pão francês chegou cerca de uma hora mais tarde para os fregueses, que entenderam o atraso.

**Contagens**: 19 palavras, 11 palavras de conteúdo (mesmo, assim, pão, francês, chegou, hora, mais, tarde, fregueses, entenderam, atraso), 10 palavras de conteúdo na lista de palavras simples (mesmo, assim, pão, francês, chegar, hora, mais, tarde, entender, atraso)

**Resultado Esperado**: 0,909 (10/11)

**Resultado Obtido**: 0,909

**Status**: correto




## Proporção de substantivos em relação à quantidade de palavras do texto




**Nome da Métrica**: noun_ratio

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: proporção de substantivos em relação ao total de palavras do texto.

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se as ocorrências de substantivos (tags ‘N’ e ‘NPROP’) 

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger 

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Acessório utilizado por adolescentes, o boné é um dos itens que compõem a vestimenta idealizada pela proposta.

**Contagens**: 17 palavras, 5 substantivos

**Resultado Esperado**: 6/17 = 0,352

**Resultado Obtido**: 0,352

**Status**: correto




## Média das frequências das palavras de conteúdo mais raras das sentenças do texto




**Nome da Métrica**: min_cw_freq

**Interpretação**: teoricamente, quanto maior a frequência, menor a complexidade da palavra

**Descrição da métrica**: Média das frequências absolutas das palavras de conteúdo mais raras das sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: frequência absoluta é a quantidade de vezes que uma palavra ocorre em um corpus, portanto, varia em função do tamanho do corpus; palavras de conteúdo são substantivos, verbos, adjetivos e advérbios; as palavras mais raras são as que têm a menor frequência em comparação com as outras palavras de conteúdo de cada sentença.

**Forma de cálculo da métrica**: identificam-se todas as palavras de conteúdo no texto. Para cada uma delas, procura-se a frequência na lista de frequências do Corpus Brasileiro. Identificam-se as palavras que apresentam a menor frequência entre as palavras de conteúdo de cada sentença. Somam-se essas frequências mínimas e divide-se o resultado pela quantidade de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet e lista de frequências do Corpus Brasileiro

**Limitações da métrica**: 

O Corpus Brasileiro possui muitos vieses devido ao desbalanceamento de suas fontes de textos, portanto, suas frequências não são um bom reflexo das frequências de palavras na língua geral.

A lista de palavras do corpus não traz categorias gramaticais e junta as frequências de formas homônimas, como por exemplo, o "a" artigo, o "a" preposição e o "a" pronome ou o pronome “sua” com a forma verbal “sua” (3ª pessoa do singular do presente do indicativo do verbo “suar”). Por isso, ao se buscar uma palavra de conteúdo na lista de frequências, nem sempre se encontra apenas a frequência da palavra na categoria gramatical almejada. 

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste 1**: A Casa tem em torno de 160 contratos para serem analisados.

**Contagens**: 
	palavras de conteúdo: 'Casa', 'tem', 'contratos', 'serem', 'analisados'
	frequências: [350476, 899042, 32471, 94817, 29643], respectivamente.
	frequência mínima: 29643

**Resultado Esperado**: 29643.0 (29643/1)

**Resultado Obtido**: 29643 (a palavra que tem menor frequência tem 29643 ocorrências)

**Status**: correto

**Teste 2**: Os partidos estão mais cautelosos.

**Contagens**: 
	palavras de conteúdo: 'partidos', 'estão', 'mais', 'cautelosos'
	Frequências [55099, 390250, 2326660, 635], respectivamente.
	Frequência mínima 635

**Resultado Esperado**: 635 (635/1)

**Resultado Obtido**: 635 

**Status**: correto




## Fórmula Dale Chall adaptada




**Nome da Métrica**: dalechall adapted

**Interpretação**: quanto maior o valor da métrica, maior a complexidade textual

**Descrição da métrica**: a fórmula de leiturabilidade de Dalechall adaptada combina a quantidade de palavras não familiares com a quantidade média de palavras por sentença. A métrica tem uma equivalência com os níveis escolares, conforme segue (Chall, Jeanne Sternlicht; Dale, Edgar (May 1, 1995). Readability revisited. ISBN 1571290087):

4,9 ou menos => nível 4 ou abaixo
5,0 a 5,9 => níveis 5 – 6
6,0 a 6,9 => níveis 7 – 8
7,0 a 7,9 => níveis 9 – 10
8,0 a 8,9 => níveis 11 – 12
9,0 a 9,9 => níveis 13 – 15 (universitários)
10 ou mais => nível 16 ou acima (graduados)

**Definição dos termos que aparecem na descrição da métrica**: palavras não familiares são aquelas que não constam do vocabulário básico conhecido por alunos do quarto ano. Para fins desta métrica, foram utilizadas as entradas do dicionário Biderman de palavras simples.

**Forma de cálculo da métrica**: primeiro conta-se a quantidade de palavras de cada sentença, somam se as quantidades e divide-se o resultado pela quantidade de sentenças do texto, para encontrar a média de palavras por sentença; depois buscam-se todas as palavras do texto na lista de palavras simples e conta-se 1 a cada palavra não encontrada na lista (o contador representa as palavras não familiares). Finalmente, usa-se a fórmula a seguir para calcular a métrica:

(0.1579 * percentual de palavras não familiares) + (0.0496 * quantidade média de palavras por sentença) + 3.6365

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**: 

**Projeto**: GUTEN

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 38 palavras, 2 sentenças, média de 19 palavras por sentença, 19 palavras não contidas na lista de palavras simples.

Temos 50% de palavras fora da lista de palavras simples

**Resultado Esperado**: (0.1579 * 0,5) + (0.0496 * 19) + 3.6365 = 4,658 (0,079+0,94+3,6365)

**Resultado Obtido**: 4,658

**Status**: correto




## Quantidade média de adjuntos adverbiais por oração do texto




**Nome da Métrica**: adjunct_per_clause

**Interpretação**: quanto maior a proporção de adjuntos adverbiais por oração, maior a complexidade textual

**Descrição da métrica**: média de adjuntos adverbiais por oração

**Definição dos termos que aparecem na descrição da métrica**: uma oração corresponde a um verbo principal. 

**Forma de cálculo da métrica**: Contam-se todas as ocorrências das etiquetas @ADVL,@>ADVL e @<ADVL e depois divide-se o resultado pelo número de orações do texto. Para calcular o número de orações, contam-se as ocorrências de verbos e subtraem-se dos resultados as ocorrências de verbos auxiliares (V - aux).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: AIC

**Teste**: A resposta de Trump ao primeiro ataque terrorista em solo americano desde o início do seu mandato é dura e polêmica. Ontem, ele disse que cogitava enviar Saipov para a prisão de Guantánamo, a mesma que o seu antecessor democrata Barack Obama esvaziou e planejava desativar por completo. Guantánamo se tornou famosa quando se tornou o presídio dos combatentes capturados no Afeganistão após a invasão liderada pelos Estados Unidos depois dos atentados de 11 de setembro de 2001. As condições dos presos mantidos na base naval americana foram motivo de indignação internacional e alvo de duras críticas, tanto por parte de governos como de organizações humanitárias internacionais.

**Contagens**: 13 orações (é, disse, cogitava, enviar, esvaziou, planejava, desativar, tornou, tornou, capturados, liderada, mantidos, foram) e 8 adjuntos adverbiais (em solo americano, desde o início do seu mandato, ontem, por completo, quando se tornou..., no Afeganistão, após a invasão..., depois dos atentados de...)

**Resultado Esperado**: 0,615

**Resultado obtido**: 0,615 

**Status**: correto 




## Média de sentidos por palavra de conteúdo do texto




**Nome da Métrica**: content_words_ambiguity

**Interpretação**: não está clara a relação da métrica com a complexidade. 

**Descrição da métrica**: Média de sentidos por palavra de conteúdo do texto 

**Definição dos termos que aparecem na descrição da métrica**: a quantidade de sentidos é o número de sentidos que uma palavra tem no dicionário TEP (Thesaurus Eletrônico do Português.

**Forma de cálculo da métrica**: Para cada palavra de conteúdo do texto (substantivos, verbos, adjetivos e advérbios), soma-se o número de sentidos que ela apresenta no TEP (http://www.nilc.icmc.usp.br/tep2/); depois divide-se o resultado pelo número de palavras de conteúdo do texto que foram encontradas no TEP.

**Recursos de PLN utilizados durante o cálculo**: tagger nlpnet e TEP Thesaurus Eletrônico do Português

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger e da estratégia de lematização utilizada, pois se as categorias de palavras de conteúdo não forem devidamente identificadas e lematizadas, as palavras não poderão ser procuradas no TEP. 

**Crítica**: 

Teoricamente, a ambiguidade é um fator que aumenta a complexidade. Utilizar a quantidade de sentidos da palavra para medir ambiguidade, porém, pode não resultar em uma boa métrica, pois as palavras mais raras (e mais complexas) são as que possuem menos sentidos e as palavras mais frequentes são as que possuem mais sentidos. As palavras mais frequentes são, também, as primeiras a serem adquiridas e, portanto, as mais simples. Por exemplo, o verbo “ser” tem 12 sentidos no TEP e, por isso, contribui para a obtenção de um resultado alto nesta métrica. Não se pode inferir, contudo, que a ocorrência do verbo “ser” aumente a complexidade do texto. É possível que essa métrica tenha se originado no tratamento automático da ambiguidade. Por isso, é preciso atentar para o fato de que o que é ambíguo para a máquina não é necessariamente ambíguo para o ser humano. 

**Projeto**: Coh-Metrix-Port

**Teste**: O menino colou na prova, embora soubesse que poderia ser pego.

**Contagens**: 7 palavras de conteúdo, com um total de 52 sentidos
	2 substantivos (menino, prova), com 1 e 9 sentidos no TEP 
	5 verbos (colou, soubesse, poderia, ser, pego) com  4, 7, 2, 12 e 17 sentidos no TEP 
	Nenhum adjetivo e nenhum advérbio.
	A lematização não identificou o verbo “pegar”, por isso o cálculo foi feito com 6 palavras e u

**Resultado Esperado**: 7,43 (52/7)

**Resultado Obtido**:  5,83 (35/6, pois não foi identificado o verbo “pegar” a partir da forma “pego”)

**Status**:  correto, considerando o erro do tagger na identificação da classe de “pego” (verbo “pegar”)




## Proporção de sentidos dos advérbios do texto em relação à  quantidade de advérbios do texto




**Nome da Métrica**: adverbs_ambiguity

**Interpretação**: não está clara a relação da métrica com a complexidade.

**Descrição da métrica**: Ambiguidade de Advérbios. Proporção entre a quantidade de sentidos dos advérbios do texto no TEP e a quantidade de advérbios do texto.

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: Para cada advérbio do texto (etiqueta ADV), soma-se o número de sentidos que ele apresenta no TEP (http://www.nilc.icmc.usp.br/tep2/) e divide-se o total pelo número de advérbios do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet e TEP Thesaurus Eletrônico do Português

**Limitações da métrica**: há palavras que não estão no TEP e, quando isso ocorre, o número de sentidos é 0. Também pode ocorrer falha de POS tagging e de lematização, impedindo a identificação do lema a ser procurado no TEP.

**Crítica**: teoricamente, a ambiguidade é um fator que aumenta a complexidade. Utilizar a quantidade de sentidos da palavra para medir ambiguidade, porém, pode não resultar em uma boa métrica, pois as palavras mais raras (e mais complexas) são as que possuem menos sentidos.

O cálculo não está considerando a etiqueta PDEN (palavras denotativas) e as contrações de preposição com advérbios (ex: daqui, dali) PREP+ADV.

**Projeto**: Coh-Metrix-Port

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 5 advérbios (não, mais, já, não, também) com 1, 5, 4, 1 e 4 sentidos respectivamente. 

O tagger identificou 5 advérbios ['não', 'a', 'mais', 'já', 'não'] e 4 lemas ['não', 'mais', 'já', 'não'], os quais possuem 1, 5, 4, 1 sentidos respectivamente]

**Resultado Esperado**: 15/5 = 3,0

**Resultado Obtido**: 2,75 (11/4, porque o advérbio “também” está anotado como PDEN)

**Status**: correto, considerando a limitação do tagger




## Quantidade média de orações por sentença




**Nome da Métrica**: clauses_per_sentence

**Interpretação**: quanto maior o número de orações por sentença, maior a complexidade

**Descrição da métrica**: média de orações por sentença

**Definição dos termos que aparecem na descrição da métrica**: oração é a unidade do texto que apresenta um verbo principal 

**Forma de cálculo da métrica**: Conta-se a quantidade de orações e divide-se o resultado pelo número de sentenças. Para computar a quantidade de orações, somam-se todos os verbos e subtraem-se os verbos auxiliares (V – aux)

**Recursos de PLN utilizados durante o cálculo**: sentenciador, para delimitar sentenças e tagger, para etiquetar verbos e verbos auxiliares. O classificador usa o parser Palavras tanto para sentenciar quanto para fazer as funções de tagger

**Limitações da métrica**: o parser não distingue particípios passados nas funções de verbo, substantivo e adjetivo, considerando-os todos verbos. Isso pode levar a uma superestimativa do número de orações.

**Crítica**: 

**Projeto**: AIC

**Teste**: 

Tendemos a pensar que os hereges são pessoas que nadam contra a corrente, indivíduos inclinados a desafiar o conhecimento dominante. Às vezes, porém, um herege é apenas um pensador convencional que permanece olhando na mesma direção, ao passo que todos os demais passaram a olhar na direção contrária. Quando, em 1957, John Yudkin aventou pela primeira vez a possibilidade de o açúcar representar um perigo para a saúde pública, a hipótese foi levada a sério, assim como seu proponente. Ao se aposentar, catorze anos depois, tanto a teoria como seu autor haviam sido ridicularizados e marginalizados. Somente agora, postumamente, é que seu trabalho vem sendo reconduzido ao pensamento científico consolidado.

**Contagens**: 5 sentenças, 16 orações

**Resultado Esperado**: 3,20 (16/5)

**Resultado Obtido**: 3,00 (o parser reconheceu 15 orações)

**Status**: correto, considerando a limitação do parser



## Proporção de orações relativas em relação à quantidade de orações do texto




**Nome da Métrica**: relative_clauses

**Interpretação**: orações relativas estão associadas à maior complexidade textual, portanto, quanto maior a proporção, maior a complexidade

**Descrição da métrica**: proporção de orações relativas em relação ao total de orações do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: Contam-se as ocorrências da etiqueta <rel> e divide-se pelo número de orações do texto. O número de orações é obtido contando-se as ocorrências de verbos menos as ocorrências de verbos auxiliares. (V-aux).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a etiqueta <rel> marca pronomes relativos, não somente aqueles que introduzem orações, o que pode levar a uma superestimativa do número de orações relativas.

**Crítica**: 

**Projeto**: AIC

**Teste 1**: O presidente dos EUA, Donald Trump, defendeu pelo Twitter nesta quinta-feira que o terrorista uzbeque responsável pelo atentado em Nova York desta semana seja condenado à morte. Sayfullo Saipov pediu que a bandeira do Estado Islâmico fosse pendurada no quarto do hospital onde está sendo tratado. O homem de 28 anos, que vive há sete anos nos Estados Unidos, ficou ferido no abdômen por um tiro da polícia, que conseguiu prendê-lo logo após ele ter atropelado pedestres e ciclistas numa ciclovia de Manhattan na terça-feira.

**Contagens**: 11 orações, 3 relativas

**Resultado Esperado**: 0,273

**Resultado Obtido**: 0,273

**Status**: correto




## Desvio padrão das proporções entre as palavras de conteúdo e a quantidade de palavras das sentenças



**Nome da Métrica**: content_word standard_deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre as palavras de conteúdo e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: palavras de conteúdo são substantivos, verbos, adjetivos e advérbios.

**Forma de cálculo da métrica**: Calcula-se a proporção de palavras de conteúdo por quantidade de palavras para cada sentença. Calcula-se o desvio padrão .

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet e nltk toolkit

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger e do sentenciador.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Como marcar pessoas em fotos no Facebook. 1) Clique na foto para expandi-la. 2) Passe o cursor sobre a foto e clique em “marcar foto” na parte inferior. 3) Clique na pessoa na foto e comece a digitar o nome dela. 4) Escolha o nome completo da pessoa que você desejar marcar, quando for exibido. 5) Clique em “finalizar marcação”.

**Contagens**:
6 sentenças, 
Palavras de conteúdo por sentença [4, 3, 8, 6, 8, 3]
Palavras por sentença [7, 7, 16, 14, 16, 6]
Proporções de palavras de conteúdo por sentença [0,57, 0,43, 0,5, 0,42, 0,5, 0,5] 

**O programa identificou**: 
Palavras de conteúdo por sentença [4, 4, 9, 7, 9, 5]
Palavras por sentença [8, 8, 19, 15, 17, 9]
Proporções de palavras de conteúdo por sentença [0.5, 0.5, 0.47, 0.47, 0.53, 0.56]

**Resultado Esperado**: 0,055

**Resultado Obtido**: 0,031 (o tokenizador está contando pontuações como palavras e isso aumenta o divisor do cálculo)

**Status**: correto, considerando as limitações do tokenizador




## Proporção máxima de palavras de conteúdo em relação à quantidade de palavras das sentenças





**Nome da Métrica**: content_word max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção Máxima de palavras de conteúdo por quantidade de palavras nas sentenças

**Definição dos termos que aparecem na descrição da métrica**: palavras de conteúdo são substantivos, verbos, adjetivos e advérbios.

**Forma de cálculo da métrica**: Calcula-se a proporção de palavras de conteúdo por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a maior proporção.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet e nltk toolkit

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger e do sentenciador.

**Crítica**: as proporções de palavras de conteúdo pela quantidade de palavras nas sentenças são muito próximas umas das outras e por isso têm baixo poder discriminativo.

**Projeto**: GUTEN

**Teste**: Como marcar pessoas em fotos no Facebook. 1) Clique na foto para expandi-la. 2) Passe o cursor sobre a foto e clique em “marcar foto” na parte inferior. 3) Clique na pessoa na foto e comece a digitar o nome dela. 4) Escolha o nome completo da pessoa que você desejar marcar, quando for exibido. 5) Clique em “finalizar marcação”.

**Contagens**: 6 sentenças 
Palavras de conteúdo por sentença [4, 3, 8, 6, 8, 3]
Palavras por sentença [7, 7, 16, 14, 16, 6]
Proporções de palavras de conteúdo por sentença [0,57, 0,43, 0,5, 0,42, 0,5, 0,5] 

**O programa identificou**: 
Palavras de conteúdo por sentença [4, 4, 9, 7, 9, 5]
Palavras por sentença [8, 8, 19, 15, 17, 9]
Proporções de palavras de conteúdo por sentença [0.5, 0.5, 0.47, 0.47, 0.53, 0.56]

**Resultado Esperado**: 0,57

**Resultado Obtido**: 0,53 (o tokenizador está contando pontuações como palavras e isso aumenta o divisor do cálculo)

**Status**: correto, considerando as limitações do tokenizador



## Proporção Mínima de palavras de conteúdo por quantidade de palavras nas sentenças




**Nome da Métrica**: content_word min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção Mínima de palavras de conteúdo por quantidade de palavras nas sentenças

**Definição dos termos que aparecem na descrição da métrica**: palavras de conteúdo são substantivos, verbos, adjetivos e advérbios.

**Forma de cálculo da métrica**: Calcula-se a proporção de palavras de conteúdo por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger e do sentenciador.

**Crítica**: as proporções de palavras de conteúdo pela quantidade de palavras nas sentenças são muito próximas umas das outras e por isso têm baixo poder discriminativo.

**Projeto**: GUTEN

**Teste**: Como marcar pessoas em fotos no Facebook. 1) Clique na foto para expandi-la. 2) Passe o cursor sobre a foto e clique em “marcar foto” na parte inferior. 3) Clique na pessoa na foto e comece a digitar o nome dela. 4) Escolha o nome completo da pessoa que você desejar marcar, quando for exibido. 5) Clique em “finalizar marcação”.

**Contagens**: 6 sentenças 
Palavras de conteúdo por sentença [4, 3, 8, 6, 8, 3]
Palavras por sentença [7, 7, 16, 14, 16, 6]
Proporções de palavras de conteúdo por sentença [0,57, 0,43, 0,5, 0,42, 0,5, 0,5] 

**O programa identificou**: 
Palavras de conteúdo por sentença [4, 4, 9, 7, 9, 5]
Palavras por sentença [8, 8, 19, 15, 17, 9]
Proporções de palavras de conteúdo por sentença [0.5, 0.5, 0.47, 0.47, 0.53, 0.56]

**Resultado Esperado**: 0,42

**Resultado Obtido**: 0,47 (o tokenizador está contando pontuações como palavras e isso aumenta o divisor do cálculo)

**Status**: correto, considerando as limitações do tokenizador



## Proporção de Verbos no Pretérito Mais que Perfeito do Indicativo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: indicative_pluperfect_ratio

**Interpretação**: o pretérito mais que perfeito é um verbo pouco frequente e está associado a alta complexidade. Portanto, quanto maior a métrica, maior a complexidade.

**Descrição da métrica**: proporção de verbos no pretérito mais que perfeito do modo indicativo, em relação ao total de verbos do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V MQP.*IND e divide-se o resultado pelo total de verbos flexionados do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras. A terceira pessoa do plural dos tempos pretérito perfeito e pretérito mais que perfeito são iguais, o que gera ambiguidade, aumentando indevidamente a estatística desta métrica.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Trechos do vídeo foram exibidos pela rede britânica BBC e mostram uma fileira de corpos com ferimentos claramente provocados por tiros.

**Contagens**: 2 verbos, os dois flexionados (foram, mostram).

A forma “foram” está usada no pretérito perfeito, mas como se trata de uma forma ambígua, o parser a reconheceu com 2 etiquetas: pretérito mais que perfeito e pretérito perfeito, fazendo o cálculo da métrica computar 3 verbos flexionados

**Resultado Esperado**: 0

**Resultado Obtido**: 0,333 (1/3) 

**Status**: correto, considerando a limitação do parser




## Estatística de Horoné




**Nome da Métrica**: honore

**Interpretação**: quanto mais alto o valor, mais rico o texto é lexicalmente, o que está associado a maior complexidade.

**Descrição da métrica**: Estatística de Honoré 

**Definição dos termos que aparecem na descrição da métrica**: N é o número total de tokens, V_1 é o número de palavras do vocabulário que aparecem uma única vez, e V é o número de palavras lexicais. (HONORÉ, 1979; THOMAS et al., 2005):

**Forma de cálculo da métrica**: R = 100 * logN / (1 - (V_1 / V)) 

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  Descrição da métrica: Estatística de Horoné

**Crítica**: 

**Projeto**: Coh-Metrix-Dementia 

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: N= 95 tokens, V_1 = 69 hapax legomena, V = 78 types

**Resultado Esperado**: 100 * log95 / (1-(69/78) => (100 * 1,97772)/ (1- 0,885) => 197,772/0,115 => 1719,756

**Resultado Obtido**: 1714,027

**Status**: correto, considerando arredondamentos



## Proporção  de types de pontuações em relação à quantidade de tokens de pontuações no texto 





**Nome da Métrica**: punctuation_diversity

**Interpretação**: não é clara a relação entre diversidade de sinais de pontuação e complexidade textual.

**Descrição da métrica**: Proporção de types de sinais de pontuação em relação aos tokens de sinais de pontuação do texto. Essa métrica presume que, dados dois textos que tenham a mesma quantidade de sinais de pontuação, o mais complexo é aquele que contém maior diversidade de sinais de pontuação. Instanciando: um texto com um parênteses, dois pontos de exclamação, 5 vírgulas e 12 pontos finais seria mais complexo que um texto com 12 vírgulas e 8 pontos finais.

**Definição dos termos que aparecem na descrição da métrica**: por sinais de pontuação, entende-se: ponto final; vírgula, dois pontos, ponto-e-vírgula, ponto de exclamação, ponto de interrogação,  parênteses, reticências, travessão (. , : ; ! ? () ... _ )

**Forma de cálculo da métrica**: divide-se a quantidade de sinais de pontuação diferentes (sem repetição) pela quantidade total de sinais de pontuação.

**Recursos de PLN utilizados durante o cálculo**: parser, na função de tokenizador

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste 1**: 

Trata-se de uma mudança radical: ao longo das três últimas décadas, no mínimo, o papel de arquivilão era atribuído à gordura saturada. No momento em que Yudkin fazia sua pesquisa, nos anos 60, uma nova ortodoxia nutricional se afirmava: a alimentação saudável deveria ser pobre em gordura. Yudkin liderava um grupo cada vez menor de dissidentes que creditava ao açúcar – e não à gordura – a causa mais provável de males como obesidade, doença cardíaca e diabetes. 

**Contagens**: 12 sinais de pontuação e 4 tipos de sinais de pontuação (ponto, dois pontos, vírgula, travessão) 

**Resultado Esperado**: 4/12 = 0,33

**Resultado obtido**: 0,33

**Status**: correto




## Média dos tamanhos médios dos sintagmas nominais nas sentenças




**Nome da Métrica**: mean_noun_phrase

**Interpretação**: quanto maior o resultado, maior a complexidade textual

**Descrição da métrica**: Média dos tamanhos médios dos sintagmas nominais nas sentenças

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: a partir das árvores de dependência do LX-Parser, localizam-se os NPs de alto nível (que não são filhos de outros NPs). Conta-se a quantidade palavras de cada NP, calcula-se o tamanho médio de NP por sentença e, depois, somam-se as médias obtidas e divide-se o resultado pela quantidade sentenças.

**Recursos de PLN utilizados durante o cálculo**: LX-Parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do LX-Parser.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Três geneticistas norte-americanos receberam o Nobel por desvendarem o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68, compartilham o prêmio de Medicina ou Fisiologia. Ao isolar, a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER), eles foram pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Contagens**: 3 sentenças com 96 palavras e 9 NPs de alto nível:

1. Três geneticistas norte-americanos 
2. o Nobel
3. o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal
4. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68,
5. o prêmio de Medicina ou Fisiologia
6. os anos 1970
7. genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER),
8. eles
9. pioneiros em estabelecer conexões diretas entre DNA e comportamento.

O LX-Parser identificou 4 sentenças com 96 palavras e 11 NPs de alto nível, como segue:
1. Três geneticistas norte-americanos
2. o Nobel
3. o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal
4. Jeffrey C. 
5. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 
6. 68,
7. o prêmio de Medicina ou Fisiologia
8. Ao
9. a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER),
10. eles
11. pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Resultado Esperado**: 10.8 (13 + 11 + 6,25/3)

**Resultado Obtido**: 7,39 (13 + 2 + 6.33 + 8.25 / 4)

**Status**: correto, consideradas as limitações do parser



## Mínimo entre os tamanhos de sintagmas nominais do texto





**Nome da Métrica**: min_noun_phrase

**Interpretação**: quanto maior o resultado, maior a complexidade textual

**Descrição da métrica**: Mínimo entre os sintagmas nominais do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: a partir das árvores de dependência do LX-Parser, localizam-se os NPs de alto nível (que não são filhos de outros NPs). Conta-se a quantidade palavras de cada NP, e localiza-se o menor tamanho entre todos.

**Recursos de PLN utilizados durante o cálculo**: LX-Parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do LX-Parser.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Três geneticistas norte-americanos receberam o Nobel por desvendarem o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68, compartilham o prêmio de Medicina ou Fisiologia. Ao isolar, a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER), eles foram pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Contagens**: 3 sentenças com 96 palavras e 9 NPs de alto nível. A primeira sentença com 3 NPs (3, 2, 34 palavras). A segunda sentença com 2 NPs (16 e 6 palavras). A terceira com 4 NPs (3, 12, 1, 9 palavras). Tamanhos mínimos dos NPs nas sentenças: 2, 6 e 1, respectivamente.

**Resultado Esperado**: 1 

**Resultado Obtido**: 1

**Status**: correto




## Máximo entre os tamanhos de sintagmas nominais do texto




**Nome da Métrica**: max_noun_phrase

**Interpretação**: quanto maior o resultado, maior a complexidade textual

**Descrição da métrica**: Máximo entre os sintagmas nominais do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: a partir das árvores de dependência do LX-Parser, localizam-se os NPs de alto nível (que não são filhos de outros NPs). Conta-se a quantidade palavras de cada NP, e localiza-se o maior tamanho entre todos.

**Recursos de PLN utilizados durante o cálculo**: LX-Parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do LX-Parser.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Três geneticistas norte-americanos receberam o Nobel por desvendarem o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68, compartilham o prêmio de Medicina ou Fisiologia. Ao isolar, a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER), eles foram pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Contagens**: 3 sentenças com 96 palavras e 9 NPs de alto nível. A primeira sentença com 3 NPs (3, 2, 34 palavras). A segunda sentença com 2 NPs (16 e 6 palavras). A terceira com 4 NPs (3, 12, 1, 9 palavras). Tamanhos máximos dos NPs nas sentenças: 34, 16 e 12, respectivamente.

**Resultado Esperado**: 34

**Resultado Obtido**: 34

**Status**: correto




## Desvio-padrão do tamanho dos sintagmas nominais do texto




**Nome da Métrica**: std_noun_phrase

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual. Ela ajuda a interpretar o resultado da média. 

**Descrição da métrica**: Desvio-padrão do tamanho dos sintagmas nominais do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: : a partir das árvores de dependência do LX-Parser, localizam-se os NPs de alto nível (que não são filhos de outros NPs). Conta-se a quantidade palavras de cada NP e calcula-se o desvio-padrão entre os tamanhos (quanto os tamanhos desviam da média)

**Recursos de PLN utilizados durante o cálculo**: LX-Parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do LX-Parser

**Projeto**: GUTEN

**Teste**: Três geneticistas norte-americanos receberam o Nobel por desvendarem o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68, compartilham o prêmio de Medicina ou Fisiologia. Ao isolar, a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER), eles foram pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Contagens**: 3 sentenças com 96 palavras e 9 NPs de alto nível. A primeira sentença com 3 NPs (3, 2, 34 palavras). A segunda sentença com 2 NPs (16 e 6 palavras). A terceira com 4 NPs (3, 12, 1, 9 palavras). 
    10. Três geneticistas norte-americanos 
    11. o Nobel
    12. o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal
    13. Jeffrey C. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 68,
    14. o prêmio de Medicina ou Fisiologia
    15. os anos 1970
    16. genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER),
    17. eles
    18. pioneiros em estabelecer conexões diretas entre DNA e comportamento.

O LX-Parser errou na identificação de 3 NPs: os de 16, 3 e 12 palavras, gerando 5 NPs com 2, 12, 1, 1 e 22 palavras, conforme segue:
    12. Três geneticistas norte-americanos
    13. o Nobel
    14. o mecanismo por trás do ciclo circadiano, o relógio biológico que regula em animais e plantas os padrões diários de comportamento e funções vitais, como o metabolismo, níveis de hormônio, sono e temperatura corporal
    15. Jeffrey C. 
    16. Hall, de 72 anos, Michael Rosbash, de 73, e Michael W. Young, de 
    17. 68,
    18. o prêmio de Medicina ou Fisiologia
    19. Ao
    20. a partir dos anos 1970, genes ligados ao ritmo biológico, como o timeless (TIM) e o period (PER),
    21. eles
    22. pioneiros em estabelecer conexões diretas entre DNA e comportamento.

**Resultado Esperado**: 10,157 (desvio entre 3, 2, 34, 16, 6, 3, 12, 1, 9)

**Resultado Obtido**: 10,45 (desvio entre 3, 2, 34, 2, 12, 1, 6, 1, 22, 1, 9)

**Status**: correto, considerando as limitações do parser




## Quantidade de Sentenças no texto




**Nome da Métrica**: sentences

**Interpretação**: quanto maior o número de sentenças, maior a complexidade

**Descrição da métrica**: quantidade de sentenças no texto

**Definição dos termos que aparecem na descrição da métrica**: sentença é o segmento do texto iniciado por letra maiúscula e terminado por ponto final, ponto de interrogação, ponto de exclamação ou reticências. 

**Forma de cálculo da métrica**: contam-se as sentenças reconhecidas pelo sentenciador

**Recursos de PLN utilizados durante o cálculo**: sentenciador

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 4 sentenças

**Resultado Esperado**: 4

**Resultado Obtido**: 4

**Status**: correto




## Proporção de orações subordinadas reduzidas pela quantidade de orações do texto




**Nome da Métrica**: infinite_subordinate_clauses

**Interpretação**:.quanto maior o resultado da métrica, maior a complexidade

**Descrição da métrica**: Proporção de orações subordinadas reduzidas em relação à quantidade de orações do texto

**Definição dos termos que aparecem na descrição da métrica**: orações subordinadas reduzidas são aquelas formadas por verbos nas formas nominais (ou infinitas): infinitivo, gerúndio e particípio

**Forma de cálculo da métrica**: contam-se as ocorrências de verbo principal nas formas infinitas (<mv>.*V (INF|PCP|GER)(?!.*ICL-AUX) e divide-se pelo total de orações (V – aux).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Ele, determinado a entrar na universidade e sempre estudando horas a fio, foi o único a se lembrar do prazo final para inscrição no vestibular. 

**Contagens**: 5 verbos, 4 nas formas infinitas (determinado, entrar, estudando, lembrar)

**Resultado Esperado**: 0,80

**Resultado Obtido**: 0,80

**Status**: correto



## Quantidade Média de palavras antes dos verbos principais das orações principais das sentenças




**Nome da Métrica**: words_before_main_verb

**Interpretação**: quanto maior a métrica, maior a carga de memória exigida e maior a complexidade textual

**Descrição da métrica**: quantidade média de palavras antes dos verbos principais das orações principais das sentenças

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: localiza-se a etiqueta “main_verb” na árvore sintática e contam-se as palavras que a precedem. Se não houver “main_verb”, localiza-se o primeiro verbo flexionado da sentença e procede-se à contagem de palavras que o precedem.

**Recursos de PLN utilizados durante o cálculo**: MaltParser e a POS tagger do nlpnet.

**Limitações da métrica**: o código da métrica, ao invés de identificar verbos nas formas nominais usando etiquetas morfossintáticas, usa 4 terminações, insuficientes: ('do', 'ar', 'er', 'ir'). As terminações de infinitivo seriam –ar, -er, -ir, -or; as de gerúndio, -ando, -endo, -indo, -ondo e as de particípio regulares seriam –ado e –ido, mas há ainda muitas formas irregulares de particípio. Seria muito melhor usar etiquetas para isso. 

A contagem de palavras antes do verbo identificado como principal inclui sinais de pontuação.

**Críticas**: 

**Projeto**: Coh-Metrix-Port

**Teste 1**: 

O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro.

**Contagens**: 2 orações, 1 principal (entrou) e 1 subordinada adjetiva restritiva reduzida de particípio (aprovada); 3 palavras antes da oração principal (o, acessório, polêmico).

**Resultado Esperado**: 3

**Resultado Obtido**: 3

**Status**: correto

**Teste 2**:

Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 orações, 1 principal (receberão) e 1 subordinada adverbial condicional (aprovada), 1 subordinada adjetiva explicativa reduzida de particípio (completados); 8 palavras antes da oração principal, considerando a vírgula (se, a, ideia, for, aprovada, “,”, os, estudantes).

**Resultado Esperado**: 8

**Resultado Obtido**: 8

**Status**: correto

**Teste 3**:

Nas inserções que já circulam, o PMDB ataca as denúncias feitas pela Procuradoria Geral da República (PGR) contra o presidente Michel Temer, por conta da Operação Lava Jato, e faz comparações entre a situação econômica de hoje e a do governo Dilma Rousseff.

**Contagens**: 4 orações, 1 subordinada adjetiva restritiva (circulam) e 1 coordenada assindética (ataca), 1 subordinada adjetiva restritiva reduzida de particípio (aprovada), 1 coordenada sindética (faz). 8 palavras antes do primeiro verbo da oração “atacam”, considerando a vírgula (nas, inserções, que, já, circulam, “,”, o, PMDB)

**Resultado Esperado**: 8

**Resultado Obtido**: 8

**Status**: correto



## Quantidade Mínima de palavras por sentença




**Nome da Métrica**: sentence_length_min

**Interpretação**: não há relação direta entre a métrica e a complexidade textual

**Descrição da métrica**: Quantidade mínima de palavras por sentença

**Definição dos termos que aparecem na descrição da métrica**: a quantidade mínima de palavras por sentença é o tamanho da menor sentença do texto

**Forma de cálculo da métrica**: Calculam-se as quantidades de palavras de todas as sentenças do texto. Classificam-se resultados e identifica-se a menor quantidade

**Recursos de PLN utilizados durante o cálculo**: tokenizador nltk

**Limitações da métrica**:  

**Crítica**: é preciso conferir a forma de tokenização utilizada, pois a quantidade mínima de palavras foi de 11, ao invés de 10. É possível que as pontuações estejam sendo consideradas ou que as contrações estejam sendo desfeitas (ex: do = de + o)

**Projeto**: GUTEN

**Teste**: O papel do código aberto é permitir a inovação localmente. A inovação é dificultada quando se demanda muito capital (seja dinheiro ou “alicerce”) para começar. As restrições insensatas que nos são impostas, chamadas “patentes” e “direitos autorais”, impedem as pessoas de construir sobre ideias geradas, e algumas grandes ideias são perdidas por nunca poderem superar a “inércia” gerada por essas restrições.

**Contagens**: 3 orações, com 10, 15 e 36 palavras

**Resultado Esperado**: 10 

**Resultado Obtido**: 10

**Status**: correto




## Quantidade Máxima de palavras por sentença




**Nome da Métrica**: sentence_length_max

**Interpretação**: não há relação direta entre a métrica e a complexidade textual

**Descrição da métrica**: Quantidade máxima de palavras por sentença

**Definição dos termos que aparecem na descrição da métrica**: a quantidade máxima de palavras por sentença é o tamanho da maior sentença do texto

**Forma de cálculo da métrica**: Calculam-se as quantidades de palavras de todas as sentenças do texto. Classificam-se resultados e identifica-se a maior quantidade

**Recursos de PLN utilizados durante o cálculo**: tokenizador nltk

**Limitações da métrica**:  

**Crítica**: é preciso conferir a forma de tokenização utilizada; como o resultado da maior sentença deu 43 ao invés de 36, é possível que as pontuações estejam sendo consideradas.

**Projeto**: GUTEN

**Teste**: O papel do código aberto é permitir a inovação localmente. A inovação é dificultada quando se demanda muito capital (seja dinheiro ou “alicerce”) para começar. As restrições insensatas que nos são impostas, chamadas “patentes” e “direitos autorais”, impedem as pessoas de construir sobre ideias geradas, e algumas grandes ideias são perdidas por nunca poderem superar a “inércia” gerada por essas restrições.

**Contagens**: 3 orações, com 11, 15 e 36 palavras

**Resultado Esperado**: 36 

**Resultado Obtido**: 37 (o tokenizador anotou como NUM (numeral) as aspas abertas antes de “direitos autorais”

**Status**: correto, considerando a limitação do tokenizador




## Quantidade de diferentes tempos-modos verbais que ocorrem no texto




**Nome da Métrica**: verbal_time_moods_diversity

**Interpretação**: quanto maior a diversidade de tempos e modos verbais, maior a complexidade

**Descrição da métrica**: Quantidade de diferentes tempos e modos verbais no texto

**Definição dos termos que aparecem na descrição da métrica**: há 10 tempos e modos verbais identificados pela métrica: indicativo: presente, pretérito imperfeito, pretérito perfeito, pretérito mais que perfeito, futuro, futuro do pretérito; subjuntivo: presente, pretérito imperfeito, futuro; imperativo. Portanto, o resultado pode variar de 0 a 10. 

**Forma de cálculo da métrica**: contam-se os diferentes tipos de tempo e modo verbal que ocorrem no texto. 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Ele fizera questão de enfatizar que, embora houvesse chegado tarde, havia telefonado antecipadamente para avisar do atraso. A empresa não quer ouvir os argumentos dele e afirmou que fará de tudo para demiti-lo dentro da lei.

**Contagens**: 6 tempos/modo verbais (fizera, houvesse, havia, quer, afirmou, fará)

**Resultado Esperado**: 6

**Resultado Obtido**: 6

**Status**: correto



## Média das proporções de Nomes Próprios em relação à quantidade de palavras das Sentenças




**Nome da Métrica**: named_entity_ratio_sentence

**Interpretação**: segundo hipotetizado por Feng et al., 2010* (A Comparison of Features for Automatic Readability Assessment), quanto maior a quantidade de entidades mencionadas, maior a carga de memória requerida e, portanto, maior a complexidade textual. 

**Descrição da métrica**: Média das proporções de nomes próprios em relação à quantidade de palavras das Sentenças

**Definição dos termos que aparecem na descrição da métrica**: entidade nomeada é uma entidade do mundo real, como pessoas, lugares, datas, organizações, produtos, etc. que pode ser denotada por meio de um nome. O reconhecimento de entidades nomeadas é uma subtarefa do processamento de línguas naturais. Nessa métrica só estão sendo reconhecidas as entidades nomeadas que possuem nome próprio em letra maiúscula, capturadas por meio da etiqueta morfossintática PROP do parser Palavras.

**Forma de cálculo da métrica**: contam-se as ocorrências da etiqueta PROP em cada sentença e divide-se o resultado pela quantidade de palavras da sentença (proporção de entidades nomeadas por quantidade de palavras das sentenças). Depois somam-se todas as proporções calculadas e divide-se o resultado pelo número de sentenças, para obter a média das proporções.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Romero Jucá já disse que presidente deve vetar trecho sobre PIS-Cofins.

**Contagens**: 10 palavras, 2 PROP (Romero=Jucá  e PIS-Cofins)

**Resultado Esperado**: 0,20

**Resultado Obtido**: 0,20

**Status**: correto




## Quantidade média de apostos por oração do texto




**Nome da Métrica**: apposition_per_clause

**Interpretação**: apostos estão associados a uma maior complexidade textual

**Descrição da métrica**: quantidade média de apostos por oração 

**Definição dos termos que aparecem na descrição da métrica**: aposto é um constituinte sintático que especifica algo sobre um NP. É identificado por meio da etiqueta @APP do parser Palavras.

**Forma de cálculo da métrica**: Contam-se as ocorrências da etiqueta @APP e divide-se pelo número de orações do texto. O número de orações é obtido contando-se as ocorrências de verbos menos as ocorrências de verbos auxiliares. (V-<aux>)).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: o desempenho do parser Palavras na identificação de apostos é bem fraca, de acordo com vários testes que fizemos. 

**Crítica**: Essa métrica é muito forte, por isso é importante que seja bem capturada. A etiqueta APP do parser Palavras não está capturando todos os apostos. 

**Projeto**: AIC

**Teste 1**: O homem, um militar de alta patente, chegou em um carro blindado, prova de que se sente ameaçado. Só hoje, segunda-feira, soubemos que ele veio verificar a presença de meliantes, na maioria infantis, na nossa escola.

**Contagens**: 4 apostos, 6 orações (o Palavras identificou 5 orações porque classificou “veio verificar” como um só VP)

**Resultado Esperado**: o correto seria 0,66, mas se considerarmos o erro do Palavras, o esperado é 0,8.

**Resultado obtido**: 0,0 (o parser não anotou nenhum APP)

**Status**: incorreto

**Teste 2**: A Ecologia, ciência que investiga as relações dos seres vivos entre si e com o meio em que vivem, adquiriu grande destaque no mundo atual.

**Contagens**: 1 aposto, 2 orações

**Resultado Esperado**: 0,5

**Resultado Obtido**: 0,0 (o parser não anotou nenhum APP)

**Status**: incorreto

**Teste 3**: O homem mais rico do mundo, Bill Gates, é um grande filantropo.

**Contagens**: 1 aposto, 1 oração

**Resultado Esperado**: 1,0

**Resultado Obtido**: 1,0

**Status**: correto




## Proporção de palavras que denotam negação em relação à quantidade de palavras do texto





**Nome da Métrica**: negation_ratio

**Interpretação**: a negação é mais complexa que a afirmação, portanto, quanto maior a métrica, maior a complexidade textual

**Descrição da métrica**: proporção de palavras que denotam negação em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: as palavras que denotam negação para fins desta métrica são: não, nem, nunca, tampouco, jamais (sempre que forem ADV).

**Forma de cálculo da métrica**: contam-se as ocorrências de palavras de negação no texto e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet.

**Limitações da métrica**: a precisão da métrica depende do desempenho do nlpnet.

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: É importante que as refeições sejam equilibradas, não forneçam nem mais e nem menos daquilo que o nosso corpo precisa. 

**Contagens**: 20 palavras, 3 negações (não, nem, nem)

**Resultado Esperado**: 3/20 = 0,15

**Resultado Obtido**: 0,15

**Status**: correto




## Proporção de sinais de pontuação em relação à quantidade de palavras do texto.




**Nome da Métrica**: punctuation_ratio

**Interpretação**: não é clara a relação entre a proporção de sinais de pontuação e complexidade textual.

**Descrição da métrica**: proporção de sinais de pontuação em relação à quantidade de palavras.

**Definição dos termos que aparecem na descrição da métrica**: por sinais de pontuação, entende-se: ponto final; vírgula, dois pontos, ponto-e-vírgula, ponto de exclamação, ponto de interrogação,  parênteses, reticências, travessão (. , : ; ! ? () ... _ )

**Forma de cálculo da métrica**: Contam-se os sinais de pontuação e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de tokenizador

**Limitações da métrica**:  

**Crítica**: avaliar todos os sinais de pontuação conjuntamente não parece ser uma boa estratégia, pois eles têm diferentes impactos sobre a complexidade. Por exemplo: pontos de interrogação e exclamação estão associados a textos mais próximos do leitor e, portanto, mais fáceis de ler. Muitas vírgulas podem indicar textos mais complexos, ao passo que muitos pontos finais podem indicar textos mais simples. 

**Projeto**: GUTEN

**Teste**: 

Trata-se de uma mudança radical: ao longo das três últimas décadas, no mínimo, o papel de arquivilão era atribuído à gordura saturada. No momento em que Yudkin fazia sua pesquisa, nos anos 60, uma nova ortodoxia nutricional se afirmava: a alimentação saudável deveria ser pobre em gordura. Yudkin liderava um grupo cada vez menor de dissidentes que creditava ao açúcar – e não à gordura – a causa mais provável de males como obesidade, doença cardíaca e diabetes. 

**Contagens**: 12 sinais de pontuação e 83 palavras (contando as 7 descontrações)

**Resultado Esperado**: 12/83 = 0,14

**Resultado obtido**: 0,14

**Status**: correto




## Proporção de pronomes oblíquos em relação a todos os pronomes do texto




**Nome da Métrica**: oblique_pronouns_ratio

**Interpretação**: pronomes oblíquos estão associados a uma maior complexidade textual

**Descrição da métrica**: Proporção de pronomes oblíquos em relação a todos os pronomes do texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes oblíquos são aqueles usados prioritariamente como objetos diretos ou indiretos (o, a, os, as, lo, la, los, las, no, na, nos, nas, lhe, lhes, me, mim, te, ti, se, si, ele, ela, eles, elas, nós, vós, conosco, convosco, comigo, contigo, consigo). Os pronomes oblíquos precedidos da preposição “com”, contraídos (comigo, contigo, etc.) ou não contraídos (com ele, com eles, etc.) podem ser também adjuntos adverbiais de companhia (ex: viajar conosco, viajar com eles). Os pronomes oblíquos precedidos de preposição podem ser complemento nominal (ex: saudade de mim). A ambiguidade funcional das formas: ele, ela, eles, elas, nós e vós é resolvida pela etiqueta PROPESS, pois os pronomes pessoais do caso reto têm etiqueta específica (PROSUB). A ambiguidade funcional das formas o, a, os, as também é tratada (elas podem ser artigos – ART e, no caso de “a”, até preposição – PREP). O “se” (que pode ser conjunção – KC ou KS) também é desambiguizado, porém as funções do “se” pronome (índice de apassivação, de indeterminação do sujeito, recíproco, reflexivo) não são discriminadas.

**Forma de cálculo da métrica**: contam-se todas as ocorrências de pronomes que estejam na lista de pronomes oblíquos e tenham a etiqueta “PROPESS”. 

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: A etiqueta “PROPESS” não pega as formas contraídas dos pronomes oblíquos, mesmo que essas formas estejam no léxico da métrica. As formas contraídas dos pronomes oblíquos são: dele, dela, deles, delas, nele, nela, neles, nelas, comigo, contigo, consigo, conosco, convosco. Para capturar as formas contraídas seria necessário usar o léxico e a etiqueta PREP+PROPESS. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Ele não queria os créditos só para si: queria nos reconhecer como colaboradores valiosos. Nós ficamos motivados com a atitude que ele teve conosco. Ao que tudo indica, ele se preocupa conosco.

**Contagens**: 10 pronomes (ele, si, nos, nós, ele, conosco, tudo, ele, se, conosco), 1 do caso oblíquo (nos), sem considerar o “conosco”, que tagger não reconhece.

**Resultado Esperado**: 1/10 = 0,10

**Resultado Obtido**: 0,10 

**Status**: correto




## Proporção  de types de preposições em relação à quantidade de tokens de preposições no texto 




**Nome da Métrica**: preposition_diversity

**Interpretação**: não está clara a relação entre a diversidade de preposições e a complexidade textual

**Descrição da métrica**: proporção de preposições distintas em relação ao total de preposições do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: 

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet. Se fosse o Palavras, haveria descontração e reconhecimento das locuções prepositivas (multipalavras), pois todas são anotadas como PREP.

**Limitações da métrica**: 

**Crítica**: 

1) a métrica está utilizando tokenização sem descontração, o que dá muita diferença em matéria de preposições. A preposição “por”, por exemplo, é tratada como um caso diferente cada vez que se combina com um artigo diferente. Com isso, uma única preposição produz 5 preposições diferentes para fins de cálculo de diversidade: por; por+o= pelo; por+a=pela; por+os=pelos; por+as=pelas. O mesmo ocorre para as preposições “de” e “a”.

2) cada um dos tokens que constituem as locuções prepositivas estão sendo tratados como uma preposição. Por exemplo, “além de” é contado pelo classificador como duas preposições: “além” e “de”. 

**Projeto**: GUTEN

**Teste**: Nem é preciso argumentar contra a ineficiência do sistema prisional brasileiro. Ele foi reprovado por todas as pessoas para as quais foi solicitada uma avaliação. Nele não se pode confiar e dele não se pode esperar nada além do estímulo à violência.

**Contagens**: 8 preposições, 7 diferentes preposições (contra, de, por, para, em, além de, a)

**Resultado Esperado**: 0,875

**Resultado Obtido**: 0,889 (o sistema reconheceu 9 preposições, sendo 8 diferentes)

**Status**: correto, considerando as limitações da métrica

**Teste**: Essas pessoas estão vivendo abaixo da linha de pobreza e pouco se pode fazer a respeito disso.

**Contagens**: 3 preposições, 3 diferentes preposições 

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de pronomes possessivos nas terceiras pessoas em relação à quantidade de pronomes possessivos do texto




**Nome da Métrica**: third_person_possessive_pronouns

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: proporção de pronomes possessivos de terceira pessoa em relação à quantidade total de pronomes possessivos no texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes possessivos indicam posse. Os das terceiras pessoas são: seu, seus, sua, suas, dele, deles, dela, delas.

**Forma de cálculo da métrica**: contam-se as ocorrências das etiquetas <poss 3S> e <poss 3P>, pronomes possessivos de segunda pessoa no singular e no plural, respectivamente. Divide-se o resultado pela soma de todos os pronomes possessivos do texto (<poss 1S>, <poss 1P>, <poss 2S>, <poss 2P>, <poss 3S>, <poss 3P>)

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger

**Limitações da métrica**: no português brasileiro as formas de segunda pessoa foram suplantadas pelo uso de “você” e “vocês”, que usam a flexão e os pronomes possessivos de terceira pessoa. Portanto, não é possível distinguir os possessivos que se referem a “você” e “vocês” dos possessivos que se referem a “ele, ela, eles, elas”, o que gera ambiguidade. Para resolver a ambiguidade, usam-se as formas “dele, deles, dela, delas”, mas o parser não reconhece essas formas como pronomes possessivos e sim com contrações da preposição “de” com os pronomes pessoais de terceira pessoa. 

**Crítica**: 

**Projeto**: AIC

**Teste**: Seus olhos são mais escuros do que os dela, mas ainda são claros se comparados aos meus. 

**Contagens**: 2 pronomes possessivos na terceira pessoa (seus, dela) e 1 pronome possessivo na primeira pessoa (meus). 

**Resultado Esperado**: 2/3 = 0,66

**Resultado Obtido**: 0,50 (porque o parser não reconhece o pronome “dela”)

**Status**: correto (considerando a limitação do parser)




## Proporção de verbos flexionados em relação a todos os verbos do texto




**Nome da Métrica**: inflected_verbs

**Interpretação**: não é clara a relação entre verbos flexionados e complexidade

**Descrição da métrica**: Proporção de verbos flexionados em relação a todos os verbos do texto

**Definição dos termos que aparecem na descrição da métrica**: verbos flexionados são aqueles que sofreram flexão para adequarem-se à pessoa, ao número, ao modo e ao tempo verbais.

**Forma de cálculo da métrica**: contam-se todas as ocorrências de VFIN (formas verbais flexionadas) e divide-se pela quantidade de V (todos os verbos do texto). 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger.

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: AIC

**Teste**: É importante observar os testes que têm sido feitos após a retirada do país da Comunidade Europeia. 

**Contagens**: 5 verbos, 2 flexionados (é, têm) e 3 não flexionados (observar, sido, feitos)

**Resultado esperado**: 2/5 = 0,4

**Resultado Obtido**: 0,40 

**Status**: correto




## Proporção de verbos no gerúndio, particípio ou infinitivo em relação a todos os verbos do texto



**Nome da Métrica**: non-inflected_verbs

**Interpretação**: não é clara a relação entre verbos não flexionados e complexidade textual

**Descrição da métrica**: Proporção de verbos não flexionados em relação a todos os verbos do texto

**Definição dos termos que aparecem na descrição da métrica**: verbos não flexionados são aqueles que estão na forma nominal (infinitivo, gerúndio e particípio) e podem tanto constituir orações subordinadas reduzidas quanto sintagmas verbais com cadeias de verbos auxiliares (nessas cadeias, apenas o primeiro verbo é flexionado).

**Forma de cálculo da métrica**: contam-se todas as ocorrências de V INF + V GER + V PCP) e divide-se pela quantidade de V (todos os verbos do texto). 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger.

**Limitações da métrica**: o parser Palavras não distingue a função do particípio, considerando-o sempre verbo (pode ser adjetivo ou substantivo), o que pode superestimar o valor dessa métrica.

**Crítica**: 

**Projeto**: AIC

**Teste**: É importante observar os testes que têm sido feitos após a retirada do país da Comunidade Europeia. 

**Contagens**: 5 verbos, 2 flexionados (é, têm) e 3 não flexionados (observar, sido, feitos)

**Resultado esperado**: 3/5 = 0,6

**Resultado Obtido**: 0,60 

**Status**: correto




## Quantidade média de referentes que se repetem nos pares de sentenças do texto




**Nome da Métrica**: adj_arg_ovl

**Interpretação**: repetição de referentes é um recurso de simplificação; portanto, quanto maior a métrica, menor a complexidade textual (exceto em textos constituídos de uma única sentença)

**Descrição da métrica**: Quantidade média de referentes que se repetem nos pares de sentenças adjacentes do texto

**Definição dos termos que aparecem na descrição da métrica**: pares de sentenças adjacentes são todas as possíveis combinações de 2 sentenças em sequência, por exemplo: 1-2, 2-3, 3-4, 4-5 (em um texto com 5 sentenças); referentes são substantivos e pronomes.

**Forma de cálculo da métrica**: em cada par de sentenças adjacentes, procuram-se referentes em comum. Cada coincidência identificada nos pares de sentenças adjacentes acumula 1 no contador. Ao final, divide-se o resultado do contador pela quantidade de pares de sentenças adjacentes do texto.

**Recursos de PLN utilizados durante o cálculo**: sentenciador nltk, POS tagger nlpnet 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As crianças aprendem muito rápido. Pesquisas mostram que até os três anos de vida, o desenvolvimento do cérebro ocorre num ritmo bem acelerado. O que os pais fazem no dia-a-dia, como ler, cantar e demonstrar carinho, é crucial para o desenvolvimento saudável da criança. Mas de acordo com certo estudo, apenas cerca da metade dos pais com crianças entre dois e oito anos lê diariamente para elas. Você talvez se pergunte: ‘Será que ler para o meu filho realmente faz diferença?’

**Contagens**: 

5 sentenças, 4 pares de sentenças adjacentes (o sentenciador, porém, reconheceu 6 sentenças, o que produziu 5 pares de sentenças adjacentes). 

2 referentes que se repetem em sentenças adjacentes: desenvolvimento (2-3), pais (3-4)

**Resultado Esperado**: 0,50 (2/4)

**Resultado Obtido**: 0,40 (2/5)

**Status**: correto, considerando a limitação do sentenciador




## Quantidade média de referentes que se repetem nos pares de sentenças adjacentes do texto




**Nome da Métrica**: arg_ovl

**Interpretação**: repetição de referentes é um recurso de simplificação; portanto, quanto maior a métrica, menor a complexidade textual (exceto em textos constituídos de uma única sentença)

**Descrição da métrica**: Quantidade média de referentes que se repetem nos pares de sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: referentes são substantivos ou pronomes; pares de sentenças são todas as possíveis combinações de 2 sentenças do texto: 1-2, 1-3, 2-3 (em um texto com 3 sentenças).

**Forma de cálculo da métrica**: em cada par de sentenças, procura-se referentes em comum. Cada coincidência encontrada acumula 1 no contador. Ao final, divide-se o resultado do contador pela quantidade de pares de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: sentenciador nltk, POS tagger nlpnet 

**Limitações da métrica**: a precisão da métrica depende do desempenho do sentenciador, do tagger e do stemmer

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As crianças aprendem muito rápido. Pesquisas mostram que até os três anos de vida, o desenvolvimento do cérebro ocorre num ritmo bem acelerado. O que os pais fazem no dia-a-dia, como ler, cantar e demonstrar carinho, é crucial para o desenvolvimento saudável da criança. Mas de acordo com certo estudo, apenas cerca da metade dos pais com crianças entre dois e oito anos lê diariamente para elas. Você talvez se pergunte: ‘Será que ler para o meu filho realmente faz diferença?’

**Contagens**: 

10 pares de sentenças no texto (1-2, 1-3, 1-4, 1-5, 2-3, 2-4, 2-5, 3-4, 3-5, 4-5). O sentenciador, contudo, reconheceu 6 sentenças (uma é constituída pelas aspas, totalmente vazia), o que produziu 15 pares de sentenças.

4 referentes que se repetem nos pares: crianças (1-4), anos (2-4) desenvolvimento (2-3), pais (3-4). 

**Resultado Esperado**: 0,40 (4/10)

**Resultado Obtido**: 0,267 (4/15)

**Status**: correto, considerando a limitação do sentenciador




## Quantidade média de radicais de palavras de conteúdo que se repetem nos pares de sentenças do texto. 




**Nome da Métrica**: adj_stem_ovl

**Interpretação**: repetição de referentes é um recurso de simplificação; portanto, quanto maior a métrica, menor a complexidade textual (exceto em textos constituídos de uma única sentença).

**Descrição da métrica**: Quantidade média de radicais de palavras de conteúdo que se repetem nos pares de sentenças adjacentes do texto. 

**Definição dos termos que aparecem na descrição da métrica**: radicais são a parte inicial das palavras flexionáveis, desprezando-se a parte flexionável (ex: menin é o radical de menino, menina, menininho, meninos, etc.); palavras de conteúdo são substantivos, verbos, adjetivos e advérbios; sentenças adjacentes são 2 sentenças do texto em sequência: 1-2, 2-3, 3-4 (em um texto com 4 sentenças).

**Forma de cálculo da métrica**: em cada par de sentenças adjacentes, procura-se radicais de palavras de conteúdo em comum. Cada coincidência de radical identificada nos pares de sentenças adjacentes acumula 1 no contador. Ao final, divide-se o resultado do contador pela quantidade de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: sentenciador nltk, POS tagger nlpnet e DELAF para reconhecer a raiz das palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do sentenciador e do tagger. 

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As crianças aprendem muito rápido. Pesquisas mostram que até os três anos de vida, o desenvolvimento do cérebro ocorre num ritmo bem acelerado. O que os pais fazem no dia-a-dia, como ler, cantar e demonstrar carinho, é crucial para o desenvolvimento saudável da criança. Mas de acordo com certo estudo, apenas cerca da metade dos pais com crianças entre dois e oito anos lê diariamente para elas. Você talvez se pergunte: ‘Será que ler para o meu filho realmente faz diferença?’

**Contagens**: 

5 sentenças, 4 pares de sentenças adjacentes (o sentenciador, porém, reconheceu 6 sentenças, o que produziu 5 pares de sentenças adjacentes)

5 radicais de palavras de conteúdo que se repetem nas adjacentes: desenvolvimento (2-3), pais (3-4), ler/lê (3-4), criança/crianças (3-4), lê/ler (4-5).

**Resultado Esperado**: 1,25 (5/4)

**Resultado Obtido**: 1,0 (5/5)

**Status**: correto, considerando a limitação do sentenciador




## Quantidade média de radicais de palavras de conteúdo que se repetem nos pares de sentenças adjacentes do texto




**Nome da Métrica**: stem_ovl

**Interpretação**: repetição de referentes é um recurso de simplificação; portanto, quanto maior a métrica, menor a complexidade textual (exceto em textos constituídos de uma única sentença).

**Descrição da métrica**: Quantidade média de radicais de palavras de conteúdo que se repetem nos pares de sentenças do texto. 

**Definição dos termos que aparecem na descrição da métrica**: radicais são a parte inicial das palavras flexionáveis (despreza-se a parte flexionável: menin- é o radical de menino, menina, menininho, meninos, etc.); palavras de conteúdo são substantivos, verbos, adjetivos e advérbios; pares de sentenças são todas as possíveis combinações de 2 sentenças do texto: 1-2, 1-3, 2-3 (em um texto com 3 sentenças).

**Forma de cálculo da métrica**: em cada par de sentenças, procura-se radicais de palavras de conteúdo em comum. Cada coincidência de radical identificada nos pares de sentenças adjacentes acumula 1 no contador. Ao final, divide-se o resultado do contador pela quantidade de pares de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: sentenciador nltk, POS tagger nlpnet e DELAF para reconhecer a raiz das palavras

**Limitações da métrica**: a precisão da métrica é dependente do desempenho dos recursos utilizados

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As crianças aprendem muito rápido. Pesquisas mostram que até os três anos de vida, o desenvolvimento do cérebro ocorre num ritmo bem acelerado. O que os pais fazem no dia-a-dia, como ler, cantar e demonstrar carinho, é crucial para o desenvolvimento saudável da criança. Mas de acordo com certo estudo, apenas cerca da metade dos pais com crianças entre dois e oito anos lê diariamente para elas. Você talvez se pergunte: ‘Será que ler para o meu filho realmente faz diferença?’

**Contagens**: 

10 pares de sentenças (1-2, 1-3, 1-4, 1-5, 2-3, 2-4, 2-5, 3-4, 3-5, 4-5). O sentenciador reconheceu mais uma sentença, devido aos parênteses na última sentença, o que gerou 15 pares.

8 radicais que se repetem nos pares de sentenças do texto: criança (1-3), criança (1-4), criança (3-4), ano (2-4), desenvolvimento (2-3), pais (3-4), fazer (3-5), ler (3-4), ler (3-5) e ler (4-5).

**Resultado Esperado**: 1,00 (10/10)

**Resultado Obtido**: 0,667 (10/15)

**Status**: correto, considerando a limitação do sentenciador




## Quantidade média de palavras de conteúdo que se repetem nos pares de sentenças adjacentes do texto




**Nome da Métrica**: adj_cw_ovl

**Interpretação**: repetição de referentes é um recurso de simplificação; portanto, quanto maior a métrica, menor a complexidade textual (exceto em textos constituídos de uma única sentença).

**Descrição da métrica**: Quantidade média de palavras de conteúdo que se repetem nos pares de sentenças adjacentes do texto. 

**Definição dos termos que aparecem na descrição da métrica**: palavras de conteúdo são substantivos, verbos, adjetivos e advérbios; pares de sentenças adjacentes são todas as possíveis combinações de 2 sentenças do texto em sequência: 1-2, 2-3, 3-4 (em um texto com 4 sentenças).

**Forma de cálculo da métrica**: em cada par de sentenças adjacentes, procuram-se palavras de conteúdo em comum. Cada coincidência identificada acumula 1 no contador. Ao final, divide-se o resultado do contador pela quantidade de pares de sentenças adjacentes do texto.

**Recursos de PLN utilizados durante o cálculo**: sentenciador nltk, POS tagger nlpnet.

**Limitações da métrica**: a precisão da métrica é dependente do desempenho dos recursos utilizados

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As crianças aprendem muito rápido. Pesquisas mostram que até os três anos de vida, o desenvolvimento do cérebro ocorre num ritmo bem acelerado. O que os pais fazem no dia-a-dia, como ler, cantar e demonstrar carinho, é crucial para o desenvolvimento saudável da criança. Mas de acordo com certo estudo, apenas cerca da metade dos pais com crianças entre dois e oito anos lê diariamente para elas. Você talvez se pergunte: ‘Será que ler para o meu filho realmente faz diferença?’

**Contagens**: 

4 pares de sentenças adjacentes (o sentenciador, porém, reconheceu 6 sentenças, o que produziu 5 pares de sentenças adjacentes), 

2 palavras de conteúdo que se repetem nos pares: desenvolvimento (2-3), pais (3-4)

**Resultado Esperado**: 0,50 (2/4)

**Resultado Obtido**: 0,4 (2/5)

**Status**: correto, considerando a limitação do sentenciador.




## Proporção de Verbos no Pretérito Imperfeito do Indicativo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: indicative_imperfect_ratio

**Interpretação**: o pretérito imperfeito do indicativo é um tempo frequente. Pode ocorrer em textos de diferentes níveis de complexidade. Não está claro qual sua relação com o nível de complexidade do texto.

**Descrição da métrica**: proporção de verbos no pretérito imperfeito do modo indicativo, em relação ao total de verbos do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V.*IMPF.*IND e divide-se o resultado pelo total de verbos flexionados do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: A conclusão da investigação do exército sobre o caso, que vazou para a imprensa, afirma que as acusações de homicídio doloso (com intenção) eram "infundadas".

**Contagens**: 3 verbos flexionados (vazou, afirma, eram); 1 verbo no pretérito imperfeito do indicativo (eram)

**Resultado Esperado**: 0,333 (1/3)

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de Verbos no Futuro do Pretérito do Indicativo em relação à quantidade de verbos flexionados do texto





**Nome da Métrica**: indicative_condition_ratio 

**Interpretação**: o futuro do pretérito do indicativo não está entre os tempos verbais mais frequentes e pode estar associado a complexidade mediana. Portanto, quanto maior a métrica, maior a complexidade.

**Descrição da métrica**: proporção de verbos no futuro do pretérito do indicativo em relação ao total de verbos flexionados do texto

**Definição dos termos que aparecem na descrição da métrica**: o futuro do pretérito do indicativo chama-se “condicional” na gramática do português europeu e corresponde ao “conditional” do inglês.

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta 'V.*COND’ e divide-se o resultado pelo total de verbos flexionados do texto (VFIN).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras 

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Com a oferta do uniforme, as escolas públicas poderão torná-lo obrigatório, o que eliminaria a roupa como um indicador de diferenças sociais nas escolas e não criaria constrangimento aos alunos mais pobres.

**Contagens**: 3 verbos flexionados (poderão, eliminaria, criaria), dois dos quais no futuro do pretérito do indicativo (eliminaria e criaria)

**Resultado Esperado**: 0,666 (2/3)

**Resultado Obtido**: 0,666

**Status**: correto




## Proporção de Verbos no Futuro do Presente do Indicativo em relação à quantidade de verbos flexionados do texto




**Nome da Métrica**: indicative_future_ratio 

**Interpretação**: o futuro do indicativo não está entre os tempos verbais mais frequentes e pode estar associado a complexidade mediana. Portanto, quanto maior a métrica, maior a complexidade.

**Descrição da métrica**: proporção de verbos no futuro do indicativo em relação ao total de verbos flexionados do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta 'V.*FUT*IND e divide-se o resultado pelo total de verbos flexionados do texto (VFIN).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras 

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Pescadores tentarão retirar o maior número de peixes da espécie, que pode atingir 20 centímetros de comprimento e um quilo.

**Contagens**: 2 verbos flexionados (tentarão, pode), 1 no futuro do indicativo (tentarão)

**Resultado Esperado**: 0,50 (1/2)

**Resultado Obtido**: 0,50

**Status**: correto




## Proporção de Verbos no Presente do Indicativo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: indicative_present_ratio

**Interpretação**: o presente do indicativo é o tempo verbal de mais frequente de todas as formas flexionadas. Pode ocorrer em textos de diferentes níveis de complexidade. 

**Descrição da métrica**: proporção de verbos no presente do modo indicativo, em relação ao total de verbos flexionados do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V.*PR.*IND e divide-se o resultado pelo total de verbos flexionados do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste 1**: 

O secretário da Segurança Pública, Enio Bacci, disse que o aumento está ligado à legislação branda contra desmanches, ao aumento da frota e ao chamado golpe do seguro -- quando o dono vende o carro a bandidos e recebe um novo da seguradora, mas reconheceu que precisa ajustar a repressão.

**Contagens**: 

6 verbos, 4 no presente do indicativo (está, vende, recebe, precisa), 2 no pretérito perfeito (disse, reconheceu)

O parser, contudo, reconheceu indevidamente o substantivo “desmanches” como mais um verbo (no presente do subjuntivo).

**Resultado Esperado**: 0,667 (4/6) ou 0,571 (4/7) se considerarmos o erro do parser

**Resultado Obtido**: 0,571 

**Status**: correto 




## Proporção de Verbos no Presente do Subjuntivo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: subjunctive_present_ratio

**Interpretação**: o presente do subjuntivo é um tempo usado com menor frequência e sua ocorrência pode estar associada a maior complexidade

**Descrição da métrica**: Proporção de Verbos no Presente do Subjuntivo em relação ao total de verbos flexionados do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V.*PR.*SUBJ e divide-se o resultado pelo total de verbos flexionados (VFIN) do texto. 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser Palavras. Como as terceiras pessoas do presente do subjuntivo são ambíguas com as terceiras pessoas do imperativo e o parser por default anota todas como subjuntivo, esta métrica pode ser superestimada.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: A regra obriga as legendas a fechar nos Estados apenas coligações que não colidam com as nacionais.

**Contagens**: 2 verbos flexionados, 1 no presente do indicativo (obriga) e 1 no presente do subjuntivo (colidam)

**Resultado Esperado**: 0,50 (1/2)

**Resultado Obtido**: 0,50

**Status**: correto




## Proporção de Verbos no Pretérito Imperfeito do Subjuntivo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: subjunctive_imperfect_ratio

**Interpretação**: o imperfeito do subjuntivo é um tempo usado com menor frequência e sua ocorrência pode estar associada a maior complexidade

**Descrição da métrica**: Proporção de Verbos no Pretérito Imperfeito do Subjuntivo em relação ao total de verbos flexionados

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta 'V.*IMPF.*SUBJ' e divide-se o resultado pelo total de verbos flexionados do texto. 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Não fosse o aspecto financeiro, o projeto teria o apoio incondicional de Balzano e do presidente da Famurs, Flávio Luiz Lammel.

**Contagens**: 2 verbos flexionados, 1 no imperfeito do subjuntivo (fosse) e 1 no futuro do pretérito do indicativo (teria).

**Resultado Esperado**: 0,50 (1/2)

**Resultado Obtido**: 0,50

**Status**: correto




## Proporção de Verbos no Futuro do Subjuntivo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: subjunctive_future_ratio

**Interpretação**: o futuro do subjuntivo é um tempo usado com menor frequência e sua ocorrência pode estar associada a maior complexidade

**Descrição da métrica**: Proporção de Verbos no Futuro do Subjuntivo em relação ao total de verbos flexionados

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V.*FUT.*SUBJ e divide-se o resultado pelo total de verbos flexionados do texto. 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser Palavras

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Se a idéia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 2 verbos flexionados, 1 no futuro do subjuntivo (for) e 1 no futuro do indicativo (receberão)

**Resultado Esperado**: 0,50 (1/2)

**Resultado Obtido**: 0,50

**Status**: correto




## Proporção de orações na voz passiva analítica em relação à quantidade de orações do texto




**Nome da Métrica**: passive_ratio 

**Interpretação**: quanto maior a Proporção de passivas no texto, mais complexo ele é. Justificativa: a voz passiva é uma estrutura que as crianças adquirem tardiamente

**Descrição da métrica**: Proporção de orações na voz passiva analítica em relação à quantidade de orações do texto. 

**Definição dos termos que aparecem na descrição da métrica**: há duas formas de voz passiva: a sintética e a analítica (desenvolvida). Esta métrica trata apenas da voz passiva analítica, constituída do verbo SER seguido de um verbo principal na forma do particípio passado. A voz passiva sintética é muito difícil de ser capturada, uma vez que é construída com a partícula “se”, muito ambígua no português e, por isso mesmo, sujeita a muitas imprecisões de anotação do parser.

**Forma de cálculo da métrica**: localizam-se todos os verbos auxiliares (<aux>) seguidos de verbo SER no particípio passado (PCP). Esses casos são contados e constituem o numerador do cálculo. O denominador é a quantidade de orações do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: o parser Palavras não distingue particípio passado usado como verbo do usado como adjetivo ou substantivo, o que pode prejudicar essa métrica. Isso pode levar a uma superestimativa das passivas no texto. Exemplos de construções que atendem à heurística mas não são passivas: Ele é entendido no assunto. Ele é aposentado. Eu sou agradecido por tudo que você fez.

**Críticas**: 

Textos simples contêm menos passivas, mas o inverso não é verdadeiro, pois há textos complexos que contêm poucas passivas também. Portanto, a ausência ou baixa proporção de passivas não é evidência de baixa complexidade. A alta proporção de passivas, pelo contrário, pode ser evidência de maior complexidade. 

Embora no inglês a passiva seja reconhecidamente um complexificador, no português ela é muito mais frequente. Temos que ter o cuidado de não dar à passiva o mesmo peso que os classificadores de complexidade textual do inglês dão.

**Projeto**: AIC

**Teste**: A campanha para designar as sete maravilhas do mundo moderno foi organizada pelo empresário e cineasta suíço Bernard Weber, que afirma ter sido motivado a defender a preservação do patrimônio histórico após a destruição dos budas gigantes de Bamiyan, no Afeganistão, pelos talibãs, em 2001.

**Contagens**: 5 orações, 2 passivas (designar, foi organizada, afirma, sido motivado, defender)

**Resultado Esperado**: 0,4

**Resultado Obtido**: 0,4

**Status**: correto




## Proporção de orações subordinadas pela quantidade de orações do texto




**Nome da Métrica**: subordinate_clauses

**Interpretação**: as orações subordinadas são estruturas mais complexas, que demandam mais esforço de processamento. Portanto, quanto maior o resultado, maior a complexidade.

**Descrição da métrica**: proporção de orações subordinadas em relação a todas orações do texto. 

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: computam-se as orações subordinadas reduzidas de infinitivo, gerúndio e particípio. Para isso, buscam-se verbos nas formas infinitivas, excluindo-se aqueles precedidos de verbos auxiliares (<mv>.*V (INF|PCP|GER) menos ICL-AUX); somam-se, a essas, as orações subordinadas introduzidas por conjunções subordinativas (KS) e orações subordinadas relativas (<rel>). Essa métrica tem origem no AIC, mas foi refeita durante do convênio ICMC-GUTEN.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras.

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser na atribuição das etiquetas utilizadas no cálculo.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Ele e amigos, como Giovane Silva Ferreira, 13 anos, passam as tardes pescando o peixe, depois levado para uma associação de artesãos que faz o curtimento da pele do animal.

**Contagens**: 4 orações (passam, pescando, levado, faz), 1 subordinada reduzida de gerúndio (pescando), 1 subordinada reduzida de particípio (levado), 1 subordinada relativa (que faz).

**Resultado Esperado**: 0,75

**Resultado Obtido**: 0,75

**Status**: correto




## Proporção de conjunções coordenativas em relação a todas as orações do texto




**Nome da Métrica**: coordinate_conjunctions_per_clauses

**Interpretação**: as conjunções coordenativas unem orações, palavras e outros constituintes sintáticos. Não está clara a sua relação com o nível de complexidade do texto. 

**Descrição da métrica**: proporção de conjunções coordenativas em relação ao total de orações do texto

**Definição dos termos que aparecem na descrição da métrica**: conjunções coordenativas são uma classe de palavras que unem duas orações independentes ou duas palavras de conteúdo ou dois sintagmas nominais. Ex: “Inovou e ficou rico”, “João e Maria”, “bonito, porém caro”, “agora e sempre”, “bonitinha, mas ordinária”.

**Forma de cálculo da métrica**: Divide-se a quantidade de conjunções coordenativas (etiqueta KC do parser Palavras) pela quantidade total de orações do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras para identificar as conjunções. 

**Limitações da métrica**: 

**Crítica**: originalmente essa métrica pretendia capturar as orações coordenadas, porém a heurística se mostrou falha por dois motivos: 1) há orações coordenadas não introduzidas por conjunções (chamadas assindéticas); 2) a etiqueta KC não é exclusiva das conjunções que ligam orações (coordenadas sindéticas). Outros algoritmos foram testados para essa finalidade, inclusive com auxílio do criador do parser Palavras, Eckhard Bick, mas não se mostraram eficientes. 

**Projeto**: AIC

**Teste**: O cientista político André Marenco afirma que a Justiça Eleitoral tem sido rigorosa em relação à propaganda antes do prazo legal e que a verticalização impôs aos partidos a conciliação de nacionais e regionais.

**Contagens**: 3 orações (afirma, tem sido, impôs), 2 conjunções coordenativas (e, e)

**Resultado Esperado**: 0,667

**Resultado Obtido**: 0,667

**Status**: correto




## Proporção de conjunções coordenativas em relação a todas as conjunções do texto




**Nome da Métrica**: ratio_coordinate_conjunctions

**Interpretação**: as conjunções coordenativas parecem ser índice de estruturas menos complexas que as conjunções subordinativas. Assim, quanto maior o resultado da métrica, menor a complexidade. 

**Descrição da métrica**: proporção de conjunções coordenativas em relação ao total de conjunções do texto

**Definição dos termos que aparecem na descrição da métrica**: há dois tipos de conjunções: coordenativas e subordinativas. Conjunções coordenativas são uma classe de palavras que unem duas orações independentes ou duas palavras de conteúdo ou dois sintagmas nominais. Conjunções subordinativas introduzem orações subordinadas.

**Forma de cálculo da métrica**: Divide-se a quantidade de conjunções coordenativas (etiqueta KC) pela quantidade total de conjunções coordenativas e subordinativas do texto (etiquetas KC + KS).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras para identificar as conjunções. 

**Limitações da métrica**: a precisão da métrica depende da precisão do parser Palavras na identificação das conjunções.

**Crítica**: 

**Projeto**: AIC

**Teste 1**: Conforme as pesquisas progrediram, a equipe descobriu que a resistência não se estende só ao gambá propriamente dito, mas também às cuícas e outros parentes do animal, todos caçadores de cobras, que teriam tido vantagens em desenvolver tais defesas bioquímicas.

**Contagens**: 2 conjunções coordenativas (mas, e) e 2 conjunções subordinativas (conforme, que). O parser, porém, não reconheceu “conforme” como KS.

**Resultado Esperado**: 0,667 (2/3, considerando a limitação do parser)

**Resultado Obtido**: 0,667

**Status**: correto

**Teste 2**: Na zona rural da Venezuela, as pessoas diziam que o gambá era resistente às picadas, mas não se sabia como.

**Contagens**: 1 conjunção coordenativa (mas) e 2 conjunções subordinativas (que, como). O parser, porém, reconheceu também o “se” como KS, quando na verdade ele é um pronome, índice de indeterminação do sujeito.

**Resultado Esperado**: 0,333 (1/3, considerando a limitação do parser)

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de conjunções subordinativas em relação a todas conjunções do texto




**Nome da Métrica**: ratio_subordinate_conjunctions 

**Interpretação**: as conjunções subordinativas, por introduzirem orações subordinadas, indicam estruturas mais complexas que conjunções coordenativas. Teoricamente, portanto, quanto maior o resultado, maior a complexidade.

**Descrição da métrica**: proporção de conjunções subordinativas em relação à soma de conjunções subordinativas e coordenativas do texto. 

**Definição dos termos que aparecem na descrição da métrica**: há dois tipos de conjunções: coordenativas e subordinativas. Conjunções coordenativas são uma classe de palavras que unem duas orações independentes ou duas palavras de conteúdo ou dois sintagmas nominais. Conjunções subordinativas introduzem orações subordinadas.

**Forma de cálculo da métrica**: identificam-se todas as conjunções do texto (etiquetas KC e KS). Divide-se a quantidade de conjunções subordinativas (etiqueta KS do parser Palavras) pela quantidade total de conjunções do texto (etiquetas KC + KS).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras.

**Limitações da métrica**: a precisão da métrica depende da precisão do parser Palavras na identificação das conjunções.

**Crítica**: 

**Projeto**: AIC

**Teste**: O secretário da Segurança Pública, Enio Bacci, disse que o aumento está ligado à legislação branda contra desmanches, ao aumento da frota e ao chamado golpe do seguro -- quando o dono vende o carro a bandidos e recebe um novo da seguradora, mas reconheceu que precisa ajustar a repressão.

**Contagens**: 5 conjunções, 3 coordenativas (e, e, mas) e 2 subordinativas (que, que)

**Resultado Esperado**: 0,4 (2/5)

**Resultado Obtido**: 0,4

**Status**: correto




## Proporção de sentenças sem verbos em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_zero_clause

**Interpretação**: quanto maior a proporção, menor a complexidade

**Descrição da métrica**: quantidade de sentenças sem nenhum verbo, ou seja, frases e não orações

**Definição dos termos que aparecem na descrição da métrica**: sentença sem oração é aquela que não apresenta nenhum verbo

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças sem orações (sem verbos), verifica-se em cada sentença a quantidade de verbos e conta-se as ocorrências de 0 verbos; depois divide-se a quantidade de sentenças sem verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar à superestimativa de quantidade de sentenças total do texto e à ocorrência artificial de sentenças sem verbo (vide teste abaixo).

**Crítica**: 

**Projeto**: AIC

**Teste**: A retirada de chapéus e bonés da cabeça em ambientes fechados.

**Contagens**: nenhuma oração (observa-se, contudo, que essa sentença é artificial, gerada por um recurso do parser de quebrar orações longas em duas partes, usando como divisor os dois pontos. A sentença original era: “Professores ainda temem que a distribuição do acessório dificulte a imposição, nas classes, de uma regra da boa conduta: a retirada de chapéus e bonés da cabeça em ambientes fechados.”)

**Resultado Esperado**: 1 

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 1 oração em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_one_clause

**Interpretação**: quanto maior a proporção, menor a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham apenas 1 oração

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 1 única oração (com 1 verbo principal), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares e contam-se os resultados que derem 1; depois divide-se a quantidade de sentenças com 1 verbo pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar à superestimativa de quantidade de sentenças e à ocorrência artificial de sentenças com apenas 1 verbo.

**Crítica**: 

**Projeto**: AIC

**Teste**: Em 29 de maio de 2002, Antônio Britto (PPS) cumpria agenda no Vale do Sinos.

**Contagens**: 1 verbo, 1 oração: cumpria

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 2 orações em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_two_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 2 orações

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 2 orações (com 2 verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares  e contam-se os resultados que derem 2; depois divide-se a quantidade de sentenças com 2 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a superestimar a quantidade total de sentenças, bem como a subestimar ou superestimar a quantidade de sentenças com 2 verbos (se a sentença original tiver 2 verbos, a quebra gera uma subestimativa; se a sentença original tiver 3 ou mais verbos e a quebra gerar pelo menos 1 sentença com 2 verbos, temos uma superestimativa).

**Crítica**: 

**Projeto**: AIC

**Teste**: Professores ainda temem que a distribuição do acessório dificulte a imposição, nas classes, de uma regra da boa conduta:

**Contagens**: 2 verbos, 2 orações (oração quebrada pelo parser, por isso termina com dois-pontos)

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 3 orações em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_three_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 3 orações

**Definição dos termos que aparecem na descrição da métrica**: 

* oração é uma unidade sintática que contém um verbo e os constituintes ligados a ele. O predicado pode ser formado por um único verbo (verbo principal) ou por uma locução verbal, isto é, um verbo principal acompanhado de um ou mais verbos auxiliares.

* Sentença é a unidade sintática iniciada por letra maiúscula E terminada por ponto final, ponto de exclamação, ponto de interrogação ou reticências. 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 3 orações (com 3 verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares e contam-se os resultados que derem 3; depois divide-se a quantidade de sentenças com 3 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a subestimar a quantidade de sentenças com 3 verbos.

**Crítica**: 

**Projeto**: AIC

**Teste**: Uma parcela critica o uniforme, porque acredita que ele ameaçaria a individualidade de cada um.

**Contagens**: 3 verbos, 3 orações: critica, acredita, ameaçaria

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 4 orações em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_four_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 4 orações

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 4 orações (com 4 verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares  e contam-se os resultados que derem 4; depois divide-se a quantidade de sentenças com 4 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a subestimar a quantidade de sentenças com 4 verbos.

**Crítica**: 

**Projeto**: AIC

**Teste**: Silva adquiriu uma tela de retenção com 150 metros, que deve ser instalada para isolar o trecho da barragem mais usado pelos banhistas, com 3,7 mil hectares de área.

**Contagens**: 4 verbos, 4 orações: principais: adquiriu, instalada, isolar, usado (deve e ser são verbos auxiliares e não contam)

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 5 orações em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_five_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 5 orações

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 5 orações (com 5 verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares  e contam-se os resultados que derem 5; depois divide-se a quantidade de sentenças com 5 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a subestimar a quantidade de sentenças com 5 verbos.

**Crítica**: 

**Projeto**: AIC

**Teste**: Estamos cadastrando ferros-velhos, mas não tivemos um trabalho forte contra a clonagem e agora vamos atacar para valer _ admitiu Bacci.

**Contagens**: 5 verbos, 5 orações: cadastrando, tivemos, atacar, valer, admitiu (estamos e vamos são verbos auxiliares e não contam)

**Resultado Esperado**: 1

**Resultado Obtido**:  1

**Status**: correto




## Proporção de sentenças com 6 orações em relação a todas as sentenças do texto




**Nome da Métrica**: sentences_with_six_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 6 orações

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 6 orações (com 6 verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares  e contam-se os resultados que derem 6; depois divide-se a quantidade de sentenças com 6 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a subestimar a quantidade de sentenças com 6 verbos. Além disso, o Palavras considera todos as formas de particípio como formas verbais, quando na verdade os particípios podem funcionar como substantivos e adjetivos também (vide teste abaixo).

**Crítica**: 

**Projeto**: AIC

**Teste**: Uma dúvida que paira hoje na Assembléia é se Ubirajara Amaral Macalão, principal envolvido na compra e no desvio de selos, era qualificado para ocupar a direção do Departamento de Serviços Administrativos (DSA).

**Contagens**: 6 verbos: paira, é, envolvido (adjetivo particípio), era, qualificado (adjetivo particípio), ocupar. Como a forma de cálculo das orações é via quantidade de verbos não auxiliares, a quantidade de orações é 6.

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção de sentenças com 7 ou mais orações em relação a todas as sentenças do texto



**Nome da Métrica**: sentences_with_seven_more_clauses

**Interpretação**: quanto maior a proporção, maior a complexidade

**Descrição da métrica**: Proporção de sentenças que contenham 7 ou mais orações

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: para obter o total de sentenças, utiliza-se o sentenciador do parser; para obter a quantidade de sentenças com 7 ou mais orações (com 7 ou mais verbos principais), verifica-se em cada sentença a quantidade de verbos, subtraem-se os verbos auxiliares e contam-se os resultados que derem mais que 6; depois divide-se a quantidade de sentenças com mais de 6 verbos pela quantidade total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser

**Limitações da métrica**:  a precisão da métrica depende do desempenho do parser. O parser Palavras gera uma quebra de sentença sempre que a sentença é longa, utilizando como ponto de quebra a ocorrência de dois-pontos ou ponto-e-vírgula. Esse fato pode levar o sistema a subestimar a quantidade de sentenças com 7 ou mais verbos. Além disso, o Palavras considera todos as formas de particípio como formas verbais, quando na verdade os particípios podem funcionar como substantivos e adjetivos também (vide teste abaixo).

**Crítica**: 

**Projeto**: AIC

**Teste**: Os aparelhos no teto, explica Simões, são os preferidos pela possibilidade de puxar a tela para cima quando não é usada, deixando o equipamento menos visível, dificultando furtos.

**Contagens**: 7 verbos, 7 orações: explica, são, preferidos (particípio adjetivo), puxar, usada, deixando, dificultando.

**Resultado Esperado**: 1

**Resultado Obtido**: 1

**Status**: correto




## Proporção mínima de substantivos em relação à quantidade de palavras das sentenças



**Nome da Métrica**: nouns min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção mínima de substantivos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são consideradas substantivos as palavras anotadas com as etiquetas N e NPROP pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de substantivos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os substantivos.

**Limitações da métrica**:

**Crítica**: ao analisarmos o resultado desta métrica nos três níveis de complexidade do corpus PorSimples, não foi identificada uma tendência que correlacione a quantidade de substantivos à complexidade textual

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 11, 8 e 7 substantivos respectivamente. O nlpnet reconheceu os adjetivos “Fundamental” e “Médio” como nomes próprios, por estarem grafados com inicial maiúscula, por isso a primeira sentença ficou com 13 substantivos. Proporções: 13/30 = 0,433; 8/21 = 0,381; 7/18 = 0,388

**Resultado Esperado**: 0,023

**Resultado Obtido**: 0,023

**Status**: correto




## Desvio padrão das proporções entre substantivos e a quantidade de palavras das sentenças




**Nome da Métrica**: nouns standard deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre substantivos e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são consideradas substantivos as palavras anotadas com as etiquetas N e NPROP pelo POS tagger nlpnet. Desvio-padrão é o quanto as medidas variam em relação à média.

**Forma de cálculo da métrica**: Calcula-se a proporção de substantivos por quantidade de palavras para cada sentença. Em seguida, calcula-se o desvio-padrão das proporções obtidas.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os substantivos.

**Limitações da métrica**:

**Crítica**: ao analisarmos o resultado desta métrica nos três níveis de complexidade do corpus PorSimples, não foi identificada uma tendência que correlacione a quantidade de substantivos à complexidade textual

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 13, 8 e 7 substantivos respectivamente. O nlpnet reconheceu os adjetivos “Fundamental” e “Médio” como nomes próprios, por estarem grafados com inicial maiúscula. Proporções; 13/30 = 0,433, 8/21 = 0,381, 7/18 = 0,388.

**Resultado Esperado**: 0,023 

**Resultado Obtido**: 0,023 

**Status**: correto




## Proporção máxima de substantivos em relação à quantidade de palavras das sentenças




**Nome da Métrica**: nouns max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção máxima de substantivos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são consideradas substantivos as palavras anotadas com as etiquetas N e NPROP pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de substantivos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a maior proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os substantivos.

**Limitações da métrica**:

**Crítica**: ao analisarmos o resultado desta métrica nos três níveis de complexidade do corpus PorSimples, não foi identificada uma tendência que correlacione a quantidade de substantivos à complexidade textual

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 12, 8 e 7 substantivos respectivamente. O nlpnet reconheceu os adjetivos “Fundamental” e “Médio” como nomes próprios, por estarem grafados com inicial maiúscula, por isso a primeira sentença ficou com 13 substantivos. Proporções: 13/30 = 0,433; 8/21 = 0,381; 7/18 = 0,388

**Resultado Esperado**: 0,381

**Resultado Obtido**: 0,381

**Status**: correto




## Índice Gunning Fox




**Nome da Métrica**: gunning fox

**Interpretação**: quanto maior a métrica, maior a complexidade

**Descrição da métrica**: Índice Gunning Fox de leiturabilidade

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: O índice Gunning Fox de leiturabilidade calcula a média de palavras por sentença do texto, soma o percentual de palavras com 3 ou mais sílabas no texto e multiplica o resultado por 0,4.

**Recursos de PLN utilizados durante o cálculo**: sentenciador, tokenizador e separador de sílabas

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério – justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 19 palavras com 3 ou mais sílabas em 38 palavras e 2 sentenças

**Resultado Esperado**: (38/2 + 19/38) x 0,4 => 19,5 x 0,4 = 7,8

**Resultado Obtido**: 7,8

**Status**: correto




## Proporção mínima de adjetivos em relação à quantidade de palavras das sentenças




**Nome da Métrica**: adjectives min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção mínima de adjetivos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados adjetivos as palavras anotadas com as etiquetas ADJ pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de adjetivos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os adjetivos

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 5, 1 e 1 adjetivos, respectivamente. O nlpnet não reconheceu “Fundamental” e “Médio” como adjetivos, porque estão grafados com inicial maiúscula, por isso a primeira sentença ficou com 3 adjetivos. Proporções: 3/30 = 0,1, 1/21 = 0,048, 1/18 = 0,056. 

**Resultado Esperado**: 1/21 = 0,048

**Resultado Obtido**: 0,048

**Status**: correto




## Desvio padrão das proporções entre adjetivos e a quantidade de palavras das sentenças




**Nome da Métrica**: adjectives standard deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre adjetivos e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados adjetivos as palavras anotadas com as etiquetas ADJ pelo POS tagger nlpnet. Desvio-padrão é o quanto as medidas variam em relação à média.

**Forma de cálculo da métrica**: Calcula-se a proporção de adjetivos por quantidade de palavras para cada sentença. Em seguida, calcula-se o desvio-padrão das proporções obtidas.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os adjetivos

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 5, 1 e 1 adjetivos, respectivamente. O nlpnet não reconheceu “Fundamental” e “Médio” como adjetivos, porque estão grafados com inicial maiúscula, por isso a primeira sentença ficou com 3 adjetivos. Proporções: 3/30 = 0,1, 1/21 = 0,048, 1/18 = 0,056. 

**Resultado Esperado**: 0,023

**Resultado Obtido**: 0,023 

**Status**: correto




## Proporção máxima de adjetivos em relação à quantidade de palavras das sentenças




**Nome da Métrica**: adjectives max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção máxima de adjetivos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados adjetivos as palavras anotadas com as etiquetas ADJ pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de adjetivos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a maior proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os adjetivos

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças de 30, 21 e 18 palavras, e um total de 5, 1 e 1 adjetivos, respectivamente. O nlpnet não reconheceu “Fundamental” e “Médio” como adjetivos, porque estão grafados com inicial maiúscula, por isso a primeira sentença ficou com 3 adjetivos. Proporções: 3/30 = 0,1, 1/21 = 0,048, 1/18 = 0,056. 

**Resultado Esperado**: 0,1

**Resultado Obtido**: 0,1 

**Status**: correto




## Proporção mínima de advérbios em relação à quantidade de palavras das sentenças




**Nome da Métrica**: adverbs min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção mínima de advérbios em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados advérbios as palavras anotadas com as etiquetas ADV e PDEN pelo POS tagger nlpnet. Há também a etiqueta de contrações de preposições com advérbios: PREP+ADV.

**Forma de cálculo da métrica**: Calcula-se a proporção de advérbios por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os advérbios

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, com 0, 1, 0, 1 e 0 advérbios (o nlpnet não reconheceu “só” como advérbio). Proporções: 0/15 = 0; 1/12 = 0,083; 0/12 = 0; 1/15 = 0,067; 0/8 = 0

**Resultado Esperado**: 0

**Resultado Obtido**: 0

**Status**: correto




## Proporção de Advérbios em relação à quantidade de palavras do texto




**Nome da Métrica**: adverbs

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção de advérbios em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados advérbios as palavras anotadas com as etiquetas ADV,  PREP+ADV e PDEN

**Forma de cálculo da métrica**: Divide-se a quantidade de advérbios pela quantidade de palavras do texto. 

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os advérbios

**Limitações da métrica**: a precisão da métrica depende do desempenho do nlpnet.

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste 1**: Daqui a alguns anos, certamente seremos menos deslumbrados com as redes sociais. Agora, porém, muitos abusos são cometidos por conta desse deslumbramento.

**Contagens**: 22 palavras e 4 advérbios (daqui, certamente, menos, agora) 

**Resultado Esperado**: 0,182 (4/22)

**Resultado Obtido**: 0,182

**Status**: correto

**Teste 2**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.

**Contagens**: 5 sentenças com um total de 62 palavras (total 62) e 5 a advérbios (diretamente, só, não, daí, também). 

**Resultado Esperado**: 0,081 (5/62)

**Resultado Obtido**: 0,081

**Status**: correto

**Teste 3**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano

**Contagens**: 8 advérbios, 38 palavras

**Resultado Esperado**: 0,211 (8/38)

**Resultado Obtido**: 0,211

**Status**: correto




## Desvio padrão das proporções entre advérbios e a quantidade de palavras das sentenças




**Nome da Métrica**: adverbs standard deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre advérbios e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados advérbios as palavras anotadas com as etiquetas ADV e PDEN pelo POS tagger nlpnet. Há também a etiqueta de contrações de preposições com advérbios: PREP+ADV.

**Forma de cálculo da métrica**: Calcula-se a proporção de advérbios por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os advérbios

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, com 0, 1, 0, 1 e 0 advérbios (o nlpnet não reconheceu “só” como advérbio). Proporções: 0/15 = 0; 1/12 = 0,083; 0/12 = 0; 1/15 = 0,067; 0/8 = 0

**Resultado Esperado**: 0,037

**Resultado Obtido**: 0,037

**Status**: correto




## Proporção máxima de advérbios em relação à quantidade de palavras das sentenças




**Nome da Métrica**: adverbs max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção máxima de advérbios em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados advérbios as palavras anotadas com as etiquetas ADV e PDEN pelo POS tagger nlpnet. Há também a etiqueta de contrações de preposições com advérbios: PREP+ADV.

**Forma de cálculo da métrica**: Calcula-se a proporção de advérbios por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a maior proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os advérbios

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, com 0, 1, 0, 1 e 0 advérbios (o nlpnet não reconheceu “só” como advérbio). Proporções: 0/15 = 0; 1/12 = 0,083; 0/12 = 0; 1/15 = 0,067; 0/8 = 0

**Resultado Esperado**: 0,083

**Resultado Obtido**: 0,083

**Status**: correto




## Proporção mínima de verbos em relação à quantidade de palavras das sentenças




**Nome da Métrica**: verbs min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção mínima de verbos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados verbos as palavras anotadas com a etiqueta V pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de verbos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os verbos

**Limitações da métrica**:  

**Crítica**: não há razão para os verbos auxiliares e no particípio (VAUX e PCP) não serem computados na métrica

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 2, 2, 2, 2 e 1 verbos, respectivamente. Proporções: 0,133, 0,167, 0,167, 0,133 e 0,125

**Resultado Esperado**: 0,125

**Resultado Obtido**: 0,125

**Status**: correto




## Desvio padrão das proporções entre verbos e a quantidade de palavras das sentenças




**Nome da Métrica**: verbs standard deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre verbos e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados verbos as palavras anotadas com a etiqueta V pelo POS tagger nlpnet.

**Forma de cálculo da métrica**: Calcula-se a proporção de verbos por quantidade de palavras para cada sentença. Depois, calcula-se o desvio-padrão das proporções obtidas.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os verbos

**Limitações da métrica**:  

**Crítica**: não há razão para os verbos auxiliares e no particípio (VAUX e PCP) não serem computados na métrica

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 2, 2, 2, 2 e 1 verbos, respectivamente. Proporções: 0,133, 0,167, 0,167, 0,133 e 0,125

**Resultado Esperado**: 0,018

**Resultado Obtido**: 0,018

**Status**: correto




## Proporção máxima de verbos por palavras em relação à quantidade de palavras das sentenças




**Nome da Métrica**: verbs max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção máxima de verbos em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados verbos as palavras anotadas com a etiqueta V pelo POS tagger nlpnet. Não são considerados os auxiliares e os verbos em forma de particípio (VAUX e PCP).

**Forma de cálculo da métrica**: Calcula-se a proporção de verbos por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os verbos

**Limitações da métrica**:  

**Crítica**: não há razão para os verbos auxiliares e no particípio não serem computados na métrica

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 2, 2, 2, 2 e 1 verbos, respectivamente. Proporções: 0,133, 0,167, 0,167, 0,133 e 0,125

**Resultado Esperado**: 0,167

**Resultado Obtido**: 0,167

**Status**: correto




## Proporção de types de substantivos  em relação à quantidade de tokens de  substantivos no texto 




**Nome da Métrica**: noun diversity

**Interpretação**: quanto maior métrica, maior a complexidade, pois a repetição de substantivos é uma das formas mais simples de construir cadeias de correferência.  

**Descrição da métrica**: Proporção de types de substantivos em relação à quantidade de tokens de substantivos no texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados substantivos as palavras anotadas com as etiquetas N e NPROP pelo POS tagger nlpnet

**Forma de cálculo da métrica**: divide-se a quantidade de substantivos diferentes (sem repetição) pela quantidade total de substantivos no texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Os direitos existem para que cada um de nós tenha uma vida digna e decente, ainda que nem sempre eles sejam respeitados. Como cidadão, todo ser humano já nasce com uma série de direitos: direito à vida, ao trabalho, à liberdade. Também as crianças têm direitos só para elas, assim como os consumidores, e até mesmo os animais. Ser cidadão também é bater o pé para que os direitos não sejam só leis no papel.

**Contagens**: 20 substantivos (direitos, vida, cidadão, ser, humano, série, direitos, direito, vida, trabalho, liberdade, crianças, direitos, consumidores, animais, cidadão, pé, direitos, leis, papel) 15 sem repetições

**Resultado Esperado**: 15/20 = 0,75

**Resultado Obtido**: 0,737 (o nlpnet não reconheceu “ser”, de “ser humano”, como substantivo)

**Status**: correto




## Proporção de types de adjetivos  em relação à quantidade de tokens de adjetivos no texto 




**Nome da Métrica**: adjective_diversity_ratio

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de adjetivos em relação à quantidade de tokens de adjetivos no texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados adjetivos as palavras anotadas com as etiquetas ADJ pelo POS tagger nlpnet

**Forma de cálculo da métrica**: divide-se a quantidade de adjetivos diferentes (sem repetição) pela quantidade total de adjetivos no texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Os direitos existem para que cada um de nós tenha uma vida digna e decente, ainda que nem sempre eles sejam respeitados. Como cidadão, todo ser humano já nasce com uma série de direitos: direito à vida, ao trabalho, à liberdade. Também as crianças têm direitos só para elas, assim como os consumidores, e até mesmo os animais. Ser cidadão também é bater o pé para que os direitos não sejam só leis no papel.

**Contagens**: 2 adjetivos (digna, decente) 2 sem repetições

**Resultado Esperado**: 2/2 = 1

**Resultado Obtido**: 1

**Status**: correto




## Média das proporções  de candidatos a referentes na sentença anterior em relação aos pronomes pessoais do caso reto nas sentenças




**Nome da Métrica**: adjacent_refs

**Interpretação**: quanto maior a métrica, maior a complexidade textual

**Descrição da métrica**: Média de candidatos a referente, na sentença anterior, por pronome anafórico 

**Definição dos termos que aparecem na descrição da métrica**: pronomes anafóricos são aqueles que retomam um referente que ocorreu antes no texto. No caso desta métrica, o referente do pronome anafórico é procurado na sentença adjacente anterior. Usa-se uma lista de pronomes, com suas respectivas etiquetas de gênero e número, para identificar os pronomes anafóricos.

**Forma de cálculo da métrica**: Identificam-se os pronomes de uma sentença, usando uma lista de pronomes (e não POS tagger). Para cada pronome, procuram-se, na sentença anterior, substantivos candidatos a referente que tenham o mesmo gênero (masculino ou feminino) e o mesmo número (singular ou plural). Somam-se os candidatos e divide-se o resultado pelo número de pronomes anafóricos identificados, a fim de obter a média de candidatos por pronome. Apenas os substantivos constantes do léxico DELAF são considerados.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, para identificar os substantivos e DELAF – léxico de formas do português, para identificar gênero (masculino, feminino ou comum de dois gêneros) e número (singular ou plural). São 6 as combinações possíveis para gênero e número dos substantivos no DELAF: ms, mp, fs, fp, as, ap (m=masculino, f=feminino, a=comum de dois gêneros, s=singular e p=plural).

**Limitações da métrica**: se o referente for um substantivo que não está no DELAF ou se tiver gênero e número diferente do pronome anafórico, não será identificado.

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: As principais propostas apresentadas na última convenção do partido foram feitas pelas mulheres. Elas estão engajadas na missão de reformar o estatuto até o final do ano. Mas muitos integrantes do partido não querem que ele seja reformado.

**Contagens**: 2 pronomes anafóricos: “elas” tem 2 candidatos a referente na sentença anterior (propostas, mulheres) e “ele” tem 3 candidatos a referente na sentença anterior (estatuto, final, ano).

**Resultado Esperado**: 5/2 = 2,5

**Resultado Obtido**: 2,5 

**Status**: correto




## Proporção  de types de advérbios em relação à quantidade de tokens de  advérbios no texto 




**Nome da Métrica**: adverbs_diversity_ratio

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de advérbios em relação à quantidade de tokens de advérbios no texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados advérbios as palavras anotadas com as etiquetas ADV e PREP+ADV ou PDEN pelo POS tagger nlpnet

**Forma de cálculo da métrica**: divide-se a quantidade de advérbios diferentes (sem repetição) pela quantidade total de advérbios no texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Os direitos existem para que cada um de nós tenha uma vida digna e decente, ainda que nem sempre eles sejam respeitados. Como cidadão, todo ser humano já nasce com uma série de direitos: direito à vida, ao trabalho, à liberdade. Também as crianças têm direitos só para elas, assim como os consumidores, e até mesmo os animais. Ser cidadão também é bater o pé para que os direitos não sejam só leis no papel.

**Contagens**: 10 advérbios (nem, sempre, já, também, só, até, mesmo, também, não, só) 8 sem repetições

**Resultado Esperado**: 8/10 = 0,80

**Resultado Obtido**: 0,80 

**Status**: correto




## Proporção de verbos auxiliares seguidos de particípio em relação à quantidade de sentenças do texto




**Nome da Métrica**: aux_plus_PCP_per_sentence

**Interpretação**: quanto maior a proporção de sintagmas verbais complexos (formados por mais de um verbo), maior a complexidade textual. 

**Descrição da métrica**: Proporção de verbos auxiliares seguidos de particípio em relação à quantidade de sentenças do texto.

**Definição dos termos que aparecem na descrição da métrica**: o particípio é uma das formas nominais do verbo, ao lado do infinitivo e do gerúndio. Há formas regulares e irregulares de formação do particípio e alguns verbos apresentam as duas. As formas regulares terminam em –ado e -ido. Exemplos: falado, colhido, sentido, morrido/morto, suspendido/suspenso, aceitado/aceito. Quando um verbo apresenta as duas formas, a forma regular é usada nos tempos compostos com os auxiliares “ter” e “haver; a forma irregular é usada com o auxiliar “ser” (na passiva).

**Forma de cálculo da métrica**: localizam-se todos os verbos auxiliares (<aux>) seguidos de verbo no particípio (V PCP). Esses casos são contados e constituem o numerador do cálculo. O denominador é a quantidade de sentenças do texto. Obs: Essa métrica veio do AIC como proporção de orações passivas em relação à quantidade de sentenças, porém identificamos um erro: apenas o verbo SER seguido de particípio deveria ser considerado voz passiva. Fizemos outra métrica de voz passiva e mantivemos essa métrica do AIC, apenas mudando sua nomenclatura.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: a precisão da métrica depende do desempenho do parser Palavras.

**Críticas**: 

**Projeto**: AIC

**Teste**: Os homens que tinham feito a manutenção não haviam sido remunerados. Eles serão recompensados futuramente com dias de descanso.

**Contagens**: 2 sentenças, 3 auxiliares seguidos de de particípio (tinham feito, haviam sido, serão recompensados)

**Resultado Esperado**: 1,5

**Resultado Obtido**: 1,5

**Status**: correto




## Proporção  de types de pronomes em relação à quantidade de tokens de  pronomes no texto 




**Nome da Métrica**: pronoun diversity

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de pronomes em relação à quantidade de tokens de pronomes no texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes são palavras que substituem ou qualificam os substantivos. No POS tagger nlpnet, os pronomes são representados pelas etiquetas: PROPESS, PROSUB, PROADJ, PRO-KS, PRO-KS-REL. Há também as etiquetas de contrações de preposições com pronomes: PREP+PROPESS,PREP+PRO-KS, PREP+PRO-KS-REL,PREP+PROADJ, PREP+PROSUB.

**Forma de cálculo da métrica**: divide-se a quantidade de pronomes diferentes (sem repetição) pela quantidade total de pronomes no texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: o POS tagger nlpnet não faz descontração, por isso é preciso usar as etiquetas de contrações de preposição com pronomes para capturar todos os pronomes (PREP+PROPESS,PREP+PRO-KS, PREP+PRO-KS-REL,PREP+PROADJ, PREP+PROSUB). 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O principal defeito dele é não prestar atenção aos detalhes de sua escrita. Ela é muito rica conceitualmente, porém contém aqueles tipos de erro de ortografia que ninguém mais comete. Desde que trabalha conosco, ele se nega a utilizar um editor eletrônico. Se ele o fizesse, grande parte de seus erros desapareceriam.

**Contagens**: 10 pronomes, 9 sem considerar repetições

**Resultado Esperado**: 9/10 = 0,90 

**Resultado Obtido**: 0,90

**Status**: correto




## Proporção de types de palavras de conteúdo em relação à quantidade de tokens de palavras de conteúdo no texto




**Nome da Métrica**: content_word diversity

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de palavras de conteúdo em relação à quantidade de tokens de palavras de conteúdo no texto

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios.

**Forma de cálculo da métrica**: divide-se a quantidade de palavras de conteúdo diferentes (sem repetição) pela quantidade total de palavras de conteúdo

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Robert Lustig trabalha como endocrinologista pediátrico na Universidade da Califórnia, especializado no tratamento da obesidade infantil. Em 2009, ele proferiu a palestra “Açúcar: a amarga verdade”, que teve mais de 6 milhões de visualizações no YouTube. No decorrer de uma hora e meia, Lustig defende com veemência que a frutose, um açúcar onipresente na alimentação moderna, é o “veneno” responsável pela epidemia de obesidade nos Estados Unidos.

**Contagens**: 41 palavras de conteúdo, 38 sem repetições. A contagem manual deu 40 e 37, mas descobrimos que o tagger contou um abre aspas como substantivo. Consideramos correta, pois o erro é devido à limitação da ferramenta utilizada.

**Resultado Esperado**: 38/41 = 0,927

**Resultado Obtido**: 0,927

**Status**: correto




## Proporção de types de verbos em relação à quantidade de tokens de verbos no texto




**Nome da Métrica**: verb diversity

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de verbos em relação à quantidade de tokens de verbos no texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados verbos as palavras anotadas com as etiquetas V, VAUX e PCP pelo POS tagger nlpnet

**Forma de cálculo da métrica**: divide-se a quantidade de verbos diferentes (sem repetição) pela quantidade total de verbos no texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Tem gente que tem fome o tempo todo. Fome de brincar, fome de jogar, e até fome de conhecer as coisas! Para quem tem fome de saber, preparamos esse teste rápido para deixar você com água na boca.

**Contagens**: 9 verbos, 7 sem repetições

**Resultado Esperado**: 7/9 =0,778

**Resultado Obtido**: 0,778

**Status**: correto




## Proporção mínima de pronomes em relação à quantidade de palavras das sentenças




**Nome da Métrica**: pronouns min

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção mínima de pronomes em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados pronomes as palavras anotadas com as etiquetas PROPESS, PROSUB, PROADJ, PRO-KS, PRO-KS-REL pelo POS tagger nlpnet. Há também as etiquetas de contrações de preposições com pronomes: PREP+PROPESS,PREP+PRO-KS, PREP+PRO-KS-REL,PREP+PROADJ, PREP+PROSUB.

**Forma de cálculo da métrica**: Calcula-se a proporção de pronomes por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a menor proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os pronomes 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 3, 0, 2, 1 e 0 pronomes, respectivamente. Proporções: 3/15 = 0,2; 0/12 = 0; 2/12 = 0,167; 1/15 = 0,067; 0/15 = 0

**Resultado Esperado**: 0

**Resultado Obtido**: 0

**Status**: correto




## Proporção de Pronomes Pessoais em relação à quantidade de palavras do texto




**Nome da Métrica**: personal_pronouns

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção de pronomes pessoais em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: são considerados pronomes pessoais: eu, tu, ele, ela, você, nós, vós, eles, elas, vocês.

**Forma de cálculo da métrica**: Divide-se a quantidade de pronomes pessoais pela quantidade de palavras do texto. 

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização Limitações da métrica: a métrica não reconhece a forma “a gente”, que é frequente na língua falada em substituição á forma “nós”.

**Crítica**: 

**Projeto**: Coh-Metrix-Dementia

**Teste**: Eles lotearam carros e a padaria teve um atraso de apenas meia hora na venda dos 2 mil pães.

**Contagens**: 19 palavras, 1 pronome pessoal (eles)

**Resultado Esperado**: 0,53

**Resultado Obtido**: 0,53

**Status**: correto




## Desvio padrão das proporções entre pronomes e a quantidade de palavras das sentenças




**Nome da Métrica**: pronouns standard deviation

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Desvio padrão das proporções entre pronomes e a quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados pronomes as palavras anotadas com as etiquetas PROPESS, PROSUB, PROADJ, PRO-KS, PRO-KS-REL pelo POS tagger nlpnet. Há também as etiquetas de contrações de preposições com pronomes: PREP+PROPESS,PREP+PRO-KS, PREP+PRO-KS-REL,PREP+PROADJ, PREP+PROSUB.

**Forma de cálculo da métrica**: Calcula-se a proporção de pronomes por quantidade de palavras para cada sentença. Calcula-se o desvio padrão das proporções obtidas.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os pronomes 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 3, 0, 2, 1 e 0 pronomes, respectivamente. Proporções: 3/15 = 0,2; 0/12 = 0; 2/12 = 0,167; 1/15 = 0,067; 0/15 = 0

**Resultado Esperado**: 0,083

**Resultado Obtido**: 0,083

**Status**: correto




## Proporção máxima de pronomes em relação à quantidade de palavras das sentenças




**Nome da Métrica**: pronouns max

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção máxima de pronomes em relação à quantidade de palavras das sentenças

**Definição dos termos que aparecem na descrição da métrica**: são considerados pronomes as palavras anotadas com as etiquetas PROPESS, PROSUB, PROADJ, PRO-KS, PRO-KS-REL pelo POS tagger nlpnet. Há também as etiquetas de contrações de preposições com pronomes: PREP+PROPESS,PREP+PRO-KS, PREP+PRO-KS-REL,PREP+PROADJ, PREP+PROSUB.

**Forma de cálculo da métrica**: Calcula-se a proporção de pronomes por quantidade de palavras para cada sentença. Classificam-se os resultados e identifica-se a maior proporção.

**Recursos de PLN utilizados durante o cálculo**: nltk para fazer a sentenciação e a tokenização e nlpnet para identificar os pronomes 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: No caso do Jeca Tatu, o verme que o deixou doente foi outro: o Ancylostoma. A larva desse verme vive no solo e penetra diretamente na pele. Só o contrai quem anda descalço na terra contaminada por fezes humanas. Se não se tratar, a pessoa fica fraca, sem ânimo e com a pele amarelada. Daí a doença ser também conhecida como amarelão.          

**Contagens**: 5 sentenças de 15, 12, 12, 15 e 8 palavras, e um total de 3, 0, 2, 1 e 0 pronomes, respectivamente. Proporções: 3/15 = 0,2; 0/12 = 0; 2/12 = 0,167; 1/15 = 0,067; 0/15 = 0 

**Resultado Esperado**: 0,2

**Resultado Obtido**: 0,2

**Status**: correto




## Proporção  de types de palavras funcionais em relação à quantidade de tokens de palavras funcionais no texto



**Nome da Métrica**: function_word diversity

**Interpretação**: não está clara a relação da métrica com a complexidade textual, mas supõe-se que, quanto maior métrica, maior a complexidade. 

**Descrição da métrica**: Proporção de types de palavras funcionais em relação à quantidade de tokens de palavras funcionais no texto

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras funcionais as palavras de 6 classes gramaticais: artigos (tag: ‘ART’), conjunções (tags ‘KS’ e ‘KC’), interjeições (tag: ‘IN’), numerais (tag: ‘NUM’), pronomes (tags: 'PROPESS',

'PROSUB', 'PROADJ', 'PRO-KS', 'PRO-KS-REL'), preposições (tags: 'PREP', 'PREP+PROPESS', 'PREP+ART', 'PREP+PRO-KS', 'PREP+PRO-KS-REL', 'PREP+PROADJ', 'PREP+ADV', 'PREP+PROSUB'). Incluem-se nas palavras funcionais os advérbios com função coordenativa e subordinativa (tags: 'ADV-KS', 'ADV-KS-REL).

**Forma de cálculo da métrica**: divide-se a quantidade de palavras funcionais diferentes (sem repetição) pela quantidade total de palavras funcionais.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Robert Lustig trabalha como endocrinologista pediátrico na Universidade da Califórnia, especializado no tratamento da obesidade infantil. Em 2009, ele proferiu a palestra “Açúcar: a amarga verdade”, que teve mais de 6 milhões de visualizações no YouTube. No decorrer de uma hora e meia, Lustig defende com veemência que a frutose, um açúcar onipresente na alimentação moderna, é o “veneno” responsável pela epidemia de obesidade nos Estados Unidos.

**Contagens**: 27 palavras funcionais, 18 sem repetições (o tagger reconhece meia, milhões e 2009 como substantivos)

**Resultado Esperado**: 18/27 = 0,667

**Resultado Obtido**: 0,667 

**Status**: correto 




## Proporção de Subtítulos em relação à quantidade de sentenças do texto





**Nome da Métrica**: subtitles

**Interpretação**: não é clara a relação da métrica com a complexidade textual, mas supõe-se que os subtítulos contribuam para a clareza pelo fato de delimitarem assuntos no texto.

**Descrição da métrica**: Proporção de Subtítulos em relação à quantidade de sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: subtítulos são títulos intermediários ao longo do texto

**Forma de cálculo da métrica**: contam-se os subtítulos etiquetados com <subtitle>   </subtitle> e divide-se pela quantidade de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**: 

**Crítica**: é preciso usar diversas heurísticas que capturem os subtítulos e não apenas a que encontra o formato dos subtítulos no corpus de treinamento do classificador. Deveria ser expandida para uso correto no futuro.

**Projeto**: GUTEN

**Teste 1**:

A Mudança de Consciência

Robert Lustig trabalha como endocrinologista pediátrico na Universidade da Califórnia, especializado no tratamento da obesidade infantil. Em 2009, ele proferiu a palestra “Açúcar: a amarga verdade”, que teve mais de 6 milhões de visualizações no YouTube. No decorrer de uma hora e meia, Lustig defende com veemência que a frutose, um açúcar onipresente na alimentação moderna, é o “veneno” responsável pela epidemia de obesidade nos Estados Unidos. 

A Mudança na Saúde

É possível que esse vídeo faça uma enorme diferença na mudança dos hábitos alimentares dos americanos e provoque um decréscimo dos índices de colesterol da população.

**Teste 2**:

<subtitle> A Mudança de Consciência </subtitle>

Robert Lustig trabalha como endocrinologista pediátrico na Universidade da Califórnia, especializado no tratamento da obesidade infantil. Em 2009, ele proferiu a palestra “Açúcar: a amarga verdade”, que teve mais de 6 milhões de visualizações no YouTube. No decorrer de uma hora e meia, Lustig defende com veemência que a frutose, um açúcar onipresente na alimentação moderna, é o “veneno” responsável pela epidemia de obesidade nos Estados Unidos. 

<subtitle> A Mudança na Saúde </subtitle>

É possível que esse vídeo faça uma enorme diferença na mudança dos hábitos alimentares dos americanos e provoque um decréscimo dos índices de colesterol da população.

**Contagens**: 2 subtítulos, 4 sentenças

**Resultado Esperado**: 2/4

**Resultado Obtido**: 0,5

**Status**: correto




## Desvio Padrão da quantidade de palavras por sentença




**Nome da Métrica**: sentence_length_standard_deviation

**Interpretação**: não há relação direta da métrica com a complexidade textual

**Descrição da métrica**: Desvio Padrão da quantidade de palavras por sentença

**Definição dos termos que aparecem na descrição da métrica**: desvio-padrão é o quanto as medidas variam em relação à média

**Forma de cálculo da métrica**: Calculam-se as quantidades de palavras de cada sentença e depois calcula-se o desvio-padrão entre os resultados.

**Recursos de PLN utilizados durante o cálculo**: tokenizador

**Limitações da métrica**: 

**Crítica**: Verificamos que o “abre aspas” pode ser eventualmente etiquetado como uma categoria gramatical e por isso é contado como token.

**Projeto**: GUTEN

**Teste**: O papel do código aberto é permitir a inovação localmente. A inovação é dificultada quando se demanda muito capital (seja dinheiro ou “alicerce”) para começar. As restrições insensatas que nos são impostas, chamadas “patentes” e “direitos autorais”, impedem as pessoas de construir sobre ideias geradas, e algumas grandes ideias são perdidas por nunca poderem superar a “inércia” gerada por essas restrições.

**Contagens**: 3 sentenças, com 10, 15 e 36 palavras

**Resultado Esperado**: 13,796

**Resultado Obtido**: 13,597 (na última sentença o nlpnet reconheceu 37 palavras)

**Status**: correto




## Proporção de orações que não estão no formato SVO (sujeito-verbo-objeto) em relação a todas orações do texto




**Nome da Métrica**: non_svo_ratio

**Interpretação**: quanto maior o resultado da métrica, maior a complexidade.

**Descrição da métrica**: Proporção de orações que não estão no formato SVO (sujeito-verbo-objeto) em relação a todas orações do texto

**Definição dos termos que aparecem na descrição da métrica**: a ordem SVO é a ordem canônica ou “natural” dos constituintes na língua portuguesa (ex: Ela adotou um menino). Ordens não SVO são: OSV (ex: Greve eu não farei), OVS (ex: dinheiro só ganharão os bons profissionais), VS (ex: Acabou o prazo), VSO (ex: Ouviram do Ipiranga as margens plácidas, de um povo heroico o brado retumbante), VOS (ex: Fez vinte e oito pontos a melhor aluna).

**Forma de cálculo da métrica**: 

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Ouviram as margens plácidas o brado retumbante. Acabou o prazo de análise, mas nós ainda podemos pedir prorrogação.

**Contagens**: 3 orações (ouviram..., acabou..., podemos pedir...), a primeira na ordem VSO, a segunda na ordem VS e a terceira na ordem SVO, portanto, 2 orações em ordens não SVO.

**Resultado Esperado**: 2/3 = 0,667

**Resultado Obtido**: 0,667

**Status**: correto




## Proporção de Sentenças Longas em relação a todas as sentenças do texto




**Nome da Métrica**: medium_long_sentence_ratio

**Interpretação**: não é clara a relação da métrica com o nível de complexidade textual. Em relação às sentenças curtas e médias, as longas são mais complexas, já em relação às sentenças muito longas, as longas são menos complexas.

**Descrição da métrica**: Proporção de Sentenças longas em relação a todas as sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: há 4 tamanhos de sentença: curto, médio, longo e muito longo. Os números de quantidade de palavras que separam os quatro tipos de sentenças são 11, 763 - 13,027 e 15,908. Na prática, isso significa que sentenças curtas têm 11 palavras ou menos; sentenças médias têm 12 ou 13 palavras; sentenças longas têm 14 ou 15 palavras e sentenças muito longas têm mais de 15 palavras.

**Forma de cálculo da métrica**: Calcula-se a quantidade de palavras por sentença. Contam-se as sentenças que tenham 14 ou 15 palavras e divide-se o resultado pelo total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador

**Limitações da métrica**: 

**Crítica**: Não há como uma sentença ter número quebrado de palavras, então uma sentença longa é aquela que tem 14 ou 15 palavras. O artifício de usar os números quebrados 11, 763 - 13,027 e 15,908 para separar os quatro intervalos só se justifica como forma de evitar ter que lidar com operações lógicas de “maior que” e “menor ou igual a”. Mas para isso as quantidades de palavras que delimitam os quatro intervalos de sentenças poderiam ser 11,001 - 13,001 e 15,001.

Os intervalos entre as sentenças curtas, médias, longas e muito longas é curto (duas palavras)

**Projeto**: GUTEN

**Teste**: O papel do código aberto é permitir a inovação localmente. A inovação é dificultada quando se demanda muito capital (seja dinheiro ou “alicerce”) para começar. As restrições insensatas que nos são impostas, chamadas “patentes” e “direitos autorais”, impedem as pessoas de construir sobre ideias geradas, e algumas grandes ideias são perdidas por nunca poderem superar a “inércia” gerada por essas restrições.

**Contagens**: 3 sentenças (de 10, 15 e 36 palavras, portanto, 1 pequena, 1 longa e uma muito longa)

**Resultado Esperado**: 1/3 = 0,333

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de Sentenças Muito Longas em relação a todas as sentenças do texto




**Nome da Métrica**: long_sentence_ratio

**Interpretação**: quanto maior a proporção de sentenças muito longas, maior a complexidade do texto

**Descrição da métrica**: Proporção de Sentenças muito longas em relação a todas as sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: há 4 tamanhos de sentença: curto, médio, longo e muito longo. Os números de quantidade de palavras que separam os quatro tipos de sentenças são 11, 763 - 13,027 e 15,908. Na prática, isso significa que sentenças curtas têm 11 palavras ou menos; sentenças médias têm 12 ou 13 palavras; sentenças longas têm 14 ou 15 palavras e sentenças muito longas têm mais de 15 palavras.

**Forma de cálculo da métrica**: Calcula-se a quantidade de palavras por sentença. Contam-se as sentenças que tenham mais de 15 palavras e divide-se o resultado pelo total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador

**Limitações da métrica**: 

**Crítica**: O artifício de usar os números quebrados 11, 763 - 13,027 e 15,908 para separar os quatro intervalos de tamanho de sentenças só se justifica como forma de evitar ter que lidar com operações lógicas de “maior que” e “menor ou igual a”. Mas para isso as quantidades de palavras que delimitam os quatro intervalos de sentenças poderiam ser 11,001 - 13,001 e 15,001.

Os intervalos entre as sentenças curtas, médias, longas e muito longas é curto (duas palavras)

**Projeto**: GUTEN

**Teste**: O papel do código aberto é permitir a inovação localmente. A inovação é dificultada quando se demanda muito capital (seja dinheiro ou “alicerce”) para começar. As restrições insensatas que nos são impostas, chamadas “patentes” e “direitos autorais”, impedem as pessoas de construir sobre ideias geradas, e algumas grandes ideias são perdidas por nunca poderem superar a “inércia” gerada por essas restrições.

**Contagens**: 3 sentenças (de 10, 15 e 36 palavras, portanto, 1 pequena, 1 longa e uma muito longa)

**Resultado Esperado**: 1/3 = 0,333

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de Sentenças Curtas em relação a todas as sentenças do texto




**Nome da Métrica**: short_sentence_ratio

**Interpretação**: quanto maior a proporção de sentenças curtas, menos complexo é o texto

**Descrição da métrica**: Proporção de Sentenças Curtas em relação a todas as sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: há 4 tamanhos de sentença: curto, médio, longo e muito longo. Os números de quantidade de palavras que separam os quatro tipos de sentenças são 11, 763 - 13,027 e 15,908. Na prática, isso significa que sentenças curtas têm 11 palavras ou menos; sentenças médias têm 12 ou 13 palavras; sentenças longas têm 14 ou 15 palavras e sentenças muito longas têm mais de 15 palavras.

**Forma de cálculo da métrica**: Calcula-se a quantidade de palavras por sentença. Contam-se as sentenças 11 palavras ou menos e divide-se o resultado pelo total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador

**Limitações da métrica**: 

**Crítica**: Não há como uma sentença ter número quebrado de palavras, então uma sentença curta é aquela que tem 11 palavras ou menos (ao invés de 11,763). O artifício de usar os números quebrados 11, 763 - 13,027 e 15,908 para separar os quatro intervalos só se justifica como forma de evitar ter que lidar com operações lógicas de “maior que” e “menor ou igual a”. Mas para isso as quantidades de palavras que delimitam os quatro intervalos de sentenças poderiam ser 11,001 - 13,001 e 15,001.

Os intervalos entre as sentenças curtas, médias, longas e muito longas é muito curto (duas palavras)

**Projeto**: GUTEN

**Teste**: Todo mundo usa software livre, mas não sabe disso, como expliquei anteriormente. E mais pessoas usariam software livre se não houvesse tanta pirataria de software no mundo. No Brasil, 84% dos softwares de desktops são piratas.

**Contagens**: 3 sentenças, uma das quais é curta (9 palavras).

**Resultado Esperado**: 1/3 = 0,333

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de Sentenças Médias em relação a todas as sentenças do texto





**Nome da Métrica**: medium_short_sentence_ratio

**Interpretação**: não é clara a relação da métrica com o nível de complexidade textual. Em relação às sentenças curtas, as médias são mais complexas, já em relação às sentenças longas ou muito longas, as médias são menos complexas.

**Descrição da métrica**: Proporção de Sentenças Médias  em relação a todas as sentenças do texto

**Definição dos termos que aparecem na descrição da métrica**: há 4 tamanhos de sentença: curto, médio, longo e muito longo. Os números de quantidade de palavras que separam os quatro tipos de sentenças são 11, 763 - 13,027 e 15,908. Na prática, isso significa que sentenças curtas têm 11 palavras ou menos; sentenças médias têm 12 ou 13 palavras; sentenças longas têm 14 ou 15 palavras e sentenças muito longas têm mais de 15 palavras.

**Forma de cálculo da métrica**: Calcula-se a quantidade de palavras por sentença. Contam-se as sentenças com 12 ou 13 palavras e divide-se o resultado pelo total de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador

**Limitações da métrica**: 

**Crítica**: Não há como uma sentença ter número quebrado de palavras, então uma sentença média é aquela que tem 12 ou 13 palavras. O artifício de usar os números quebrados 11, 763 - 13,027 e 15,908 para separar os quatro intervalos só se justifica como forma de evitar ter que lidar com operações lógicas de “maior que” e “menor ou igual a”. Mas para isso as quantidades de palavras que delimitam os quatro intervalos de sentenças poderiam ser 11,001 - 13,001 e 15,001.

Os intervalos entre as sentenças curtas, médias, longas e muito longas é curto (duas palavras)

**Projeto**: GUTEN

**Teste**: Todo mundo usa software livre, mas não sabe disso, como expliquei anteriormente. E mais pessoas usariam software livre se não houvesse tanta pirataria de software no mundo. No Brasil, 84% dos softwares de desktops são piratas.

**Contagens**: 3 sentenças, uma das quais é média (12 palavras).

**Resultado Esperado**: 1/3 = 0,333

**Resultado Obtido**: 0,333

**Status**: correto




## Proporção de Pronomes Relativos em relação à quantidade de pronomes do texto





**Nome da Métrica**: relative_pronouns_ratio

**Interpretação**: pronomes relativos introduzem orações subordinadas adjetivas, substantivas e adverbiais, que expandem o conteúdo de um sintagma nominal e aumentam a complexidade textual

**Descrição da métrica**: Proporção de Pronomes Relativos em relação à quantidade de pronomes do texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes relativos retomam e qualificam um nome que os antecedem. Suas formas são: que, o que, o qual, os quais, a qual, as quais, cujo, cujos, cuja, cujas, quem, quando, onde, como, quanto, quantos, quanta, quantas. Muitos deles são ambíguos funcionalmente (podem atuar como outro tipo de pronome), por isso a etiqueta <rel> é importante para capturar apenas aqueles com função relativa.

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta <rel> e divide-se o resultado pela soma de todas as ocorrências de pronomes do texto.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

embora a classe de pronomes seja imediatamente superior à  de pronomes relativos, a métrica poderia ser um índice melhor se fosse calculada por sintagma nominal.

O POS tagger usado não reconhece multipalavras, como “o=que”, por exemplo. Isso faz com que a métrica possa ser superestimada em alguns casos, mas não é um problema grave.

**Projeto**: GUTEN

**Teste**: Regressando de São Paulo, visitei o sítio de minha tia, o qual me deixou encantado. Era exatamente o que eu esperava, apesar de nunca ter imaginado que eu estaria ali.

**Contagens**: 7 pronomes (minha, o qual, me, o que, eu, que, eu), 9 contados pelo POS tagger nlpnet, dos quais 2 são pronomes relativos (o qual, o que)

**Resultado Esperado**: 2/7 = 0,285 ou 2/9 (o sistema identifica dois pronomes em “o que” e em “o qual”

**Resultado Obtido**: 0,222 

**Status**: correto




## Proporção de adjuntos adverbiais de tempo em relação a todos os adjuntos adverbiais do texto




**Nome da Métrica**: temporal_adjunct_ratio

**Interpretação**: não está clara a relação entre a métrica e a complexidade

**Descrição da métrica**: Proporção de adjuntos adverbiais de tempo em relação a todos os adjuntos adverbiais do texto

**Definição dos termos que aparecem na descrição da métrica**: adjuntos adverbiais de tempo são palavras ou expressões que informam quando a ação do verbo aconteceu (ex: ontem, de vez em quando, frequentemente, no dia 18 de novembro, etc.). Para identificá-las, utilizam-se as expressões regulares criadas por Baptista et. Al. (2008).

**Forma de cálculo da métrica**: identificam-se todos os adjuntos adverbiais (etiqueta ADVL do nlpnet). Filtram-se os adjuntos adverbiais de tempo, utilizando o léxico e as expressões regulares do rp.temporal_expressions. Divide-se a quantidade de adjuntos adverbiais de tempo pela quantidade total de adjuntos adverbiais.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger nlpnet.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Foi durante meus experimentos que eu me machuquei. Certamente cometi um erro.

**Contagens**: 2 adjuntos adverbiais, um dos quais é de tempo (durante meus experimentos)

**Resultado Esperado**: 1/2 = 0,50

**Resultado Obtido**: 0,50

**Status**: correto



## Média das proporções  de candidatos a referentes nas 5 sentenças anteriores em relação aos pronomes anafóricos das sentenças




**Nome da Métrica**: anaphoric_refs

**Interpretação**: quanto maior a métrica, maior a complexidade textual

**Descrição da métrica**: Média de candidatos a referente, em até 5 sentenças anteriores, por pronome anafórico 

**Definição dos termos que aparecem na descrição da métrica**: pronomes anafóricos são aqueles que retomam um referente que ocorreu antes no texto. No caso desta métrica, o referente do pronome anafórico é procurado em até 5 sentenças anteriores. Usa-se uma lista de pronomes, com suas respectivas etiquetas de gênero e número, para identificar os pronomes anafóricos.

**Forma de cálculo da métrica**: Identificam-se os pronomes de uma sentença, usando uma lista de pronomes (e não POS tagger). Para cada pronome, procuram-se, nas 5 sentenças anteriores, substantivos candidatos a referente que tenham o mesmo gênero (masculino ou feminino) e o mesmo número (singular ou plural). Somam-se os candidatos e divide-se o resultado pelo número de pronomes anafóricos identificados, a fim de obter a média de candidatos por pronome. Apenas os substantivos constantes do léxico DELAF são considerados.

**Recursos de PLN utilizados durante o cálculo**: DELAF – léxico de formas do português

**Limitações da métrica**: A métrica não elimina os candidatos a referentes repetidos. No exemplo do teste, por exemplo, as palavras “alunos”, “professores”, “trabalhos” e “relatórios” foram contados duas vezes para o segundo “eles”. 

**Crítica**: o ideal seria eliminar candidatos redundantes 

**Projeto**: Coh-Metrix-Port

**Teste**: Os professores recomendaram aos alunos que fizessem seus trabalhos de conclusão de curso com muita dedicação. Eles também lhes recomendaram que não deixassem os relatórios finais para serem escritos na última hora. São recomendações importantes, porque todos os anos os alunos pedem prorrogação dos prazos de entrega dos trabalhos e acabam entregando relatórios escritos às pressas e cheios de erros de português. Eles têm dificuldade em se planejar com antecedência.

**Contagens**: 4 sentenças, 3 pronomes (eles, eles, lhes), 17 candidatos: 3 para o primeiro “eles” (professores, alunos, trabalhos); 3 para o “lhes” (professores, alunos, trabalhos); 11 para o segundo “eles” (todos, anos, erros, relatórios, trabalhos, prazos, alunos, relatórios, trabalhos, alunos, professores)

**Resultado Esperado**: 15/3 = 5,667

**Resultado Obtido**: 5,667

**Status**: correto




## Média de candidatos a referente, na sentença anterior, por pronome anafórico do caso reto




**Nome da Métrica**: coreference_pronoum_ratio

**Interpretação**: quanto maior a métrica, maior a complexidade textual

**Descrição da métrica**: Média de candidatos a referente, na sentença anterior, por pronome anafórico do caso reto.

**Definição dos termos que aparecem na descrição da métrica**: pronomes anafóricos são aqueles que retomam um referente que ocorreu antes no texto. No caso desta métrica, são considerados apenas os pronomes anafóricos do caso reto: ele, ela, eles, elas. O referente do pronome anafórico é procurado na sentença adjacente anterior.

**Forma de cálculo da métrica**: Identificam-se os pronomes de caso reto. Para cada pronome, procuram-se, na sentença anterior, substantivos candidatos a referente que tenham o mesmo gênero (masculino ou feminino) e o mesmo número (singular ou plural) do pronome. Somam-se os candidatos e divide-se o resultado pelo número de pronomes anafóricos de caso reto, a fim de obter a média de candidatos por pronome. Apenas os substantivos constantes do léxico DELAF são considerados.

**Recursos de PLN utilizados durante o cálculo**: DELAF – léxico de formas do português

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: As principais propostas apresentadas na última convenção do partido foram feitas pelas mulheres. Elas estão engajadas na missão de reformar o estatuto até o final do ano. Mas muitos integrantes do partido não querem que ele seja reformado.

**Contagens**: 2 pronomes anafóricos do caso reto: “elas” tem 2 candidatos a referente na sentença anterior (propostas, mulheres) e “ele” tem 3 candidatos a referente na sentença anterior (estatuto, final, ano).

**Resultado Esperado**: 5/2 = 2,5

**Resultado Obtido**: 2,5 

**Status**: correto




## Média de candidatos a referente, na sentença anterior, por pronome demonstrativo anafórico




**Nome da Métrica**: demonstrative_pronoun_ratio

**Interpretação**: quanto mais candidatos a referentes houver para resolver a referência anafórica, maior é a complexidade textual

**Descrição da métrica**: Média de candidatos a referente, na sentença anterior, por pronome demonstrativo anafórico

**Definição dos termos que aparecem na descrição da métrica**: referência anafórica é a relação entre um pronome e o termo anterior que ele substitui. O pronome é a anáfora e o nome que ele substitui é o referente. Por exemplo, quando digo “Gosto desse livro”, podem me perguntar: “Desse qual?” A resposta é o referente do pronome anafórico “desse”: “Comprei a obra “Sapiens”, que é um best seller desde que foi lançado. Gosto desse livro.” Leitores proficientes sabem que “desse” = “a obra ‘Sapiens’”. Na sentença anterior, contudo, há três substantivos candidatos a referente do pronome “desse”: “obra”, “Sapiens’” e “best seller”. Decidir entre os candidatos pode ser uma tarefa difícil para um leitor menos proficiente e por isso a quantidade de candidatos por pronome anafórico é uma medida de complexidade textual. 

**Forma de cálculo da métrica**: localizam-se todos os pronomes demonstrativos nas sentenças, usando uma lista desses pronomes com seus respectivos número (singular ou plural) e gênero (feminino ou masculino). Na sentença anterior a cada pronome demonstrativo, procuram-se substantivos que tenham, no léxico DELAF, o mesmo número e gênero do pronome demonstrativo, ou seja, que sejam candidatos a referência anafórica desses pronomes. Contam-se os candidatos por pronome demonstrativo e depois calcula-se a média de candidatos por pronome demonstrativo.

**Recursos de PLN utilizados durante o cálculo**: DELAF

**Limitações da métrica**: se os candidatos a referente não estiverem no léxico DELAF ou se não tiverem o mesmo número e grau do pronome demonstrativo, eles não serão reconhecidos, como é visto no primeiro teste. 

**Crítica**: 

**Projeto**: GUTEN

**Teste 1**: Comprei a obra “Sapiens”, que é um best-seller desde que foi lançado. Gosto desse livro.

**Contagens**: 1 pronome demonstrativo (desse) e 3 candidatos a referentes na sentença anterior (obra, Sapiens, best-seller)

**Resultado Esperado**: 3/1 = 3

**Resultado Obtido**: 0 (“desse” é masculino singular e “obra” é feminino singular; “Sapiens” e “best seller” não estão no léxico do DELAF)

**Status**: correto, dentro das limitações da métrica

**Teste 2**: Ouvi dizer que estão tentando incluir orientação nutricional no currículo escolar. Sou totalmente defensor dessa proposta.

**Contagens**: 1 pronome demonstrativo (dessa) e 1 candidato a referentes na sentença anterior (orientação)

**Resultado Esperado**: 1/1 = 1

**Resultado Obtido**: 1 

**Status**: correto




## Proporção de sujeitos pospostos em relação a todos os sujeitos do texto






**Nome da Métrica**: postponed_subject_ratio

**Interpretação**: sujeito posposto (VS) é uma ordem de constituintes mais complexa que sujeito anteposto (SV)

**Descrição da métrica**: Proporção de sujeitos pospostos em relação a todos os sujeitos do texto

**Definição dos termos que aparecem na descrição da métrica**: sujeito posposto é o sujeito que ocorre após o verbo. 

**Forma de cálculo da métrica**: contam-se todas as etiquetas <SUBJ (sujeito após verbo principal) do texto e divide-se o resultado pela soma de todas as etiquetas SUBJ (sujeitos) do texto

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: São tomadas muitas iniciativas a fim de melhorar a situação da educação no Brasil, porém são poucas as que dão resultado.

**Contagens**: 4 orações (são tomadas, melhorar, são, dão), 3 sujeitos (muitas iniciativas, as que dão resultado, que) 2 sujeitos pospostos 

**Resultado Esperado**: 2/3 = 0,667

**Resultado Obtido**: 0,667

**Status**: correto




## Proporção de orações com advérbio antes do verbo principal em relação à quantidade de orações do texto




**Nome da Métrica**: adverbs_before_main_verb_ratio

**Interpretação**: quanto maior o resultado da métrica (o máximo é 1), maior a complexidade textual, pois representa carga de trabalho de leitura, ou seja, aquilo que se acumula na memória antes da chegada do verbo principal.

**Descrição da métrica**: Proporção de orações com advérbio antes do verbo principal em relação à quantidade de orações do texto

**Definição dos termos que aparecem na descrição da métrica**: advérbios antes de verbos principais são ocorrências que rompem a ordem canônica dos constituintes das sentenças (Sujeito, Verbo, Objeto, Advérbio).

**Forma de cálculo da métrica**: verificam-se quantas orações possuem ocorrências de adjuntos adverbiais antepostos aos verbos (@ADVL>), não importando a quantidade de advérbios antepostos. Divide-se o resultado do contador pela quantidade de orações do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Gradativamente, ele foi se acostumando às novas condições de trabalho, porém, praticamente não se conformou até hoje com a perda de status. Hoje é fácil perceber isso, no entanto, naquela época, dificilmente alguém poderia saber que ele estava sofrendo profundamente.

**Contagens**: 6 orações, 4 com advérbios antes dos verbos principais

**Resultado Esperado**: 4/6 = 0,667

**Resultado Obtido**: 0,667

**Status**: correto




## Proporção  de types de pronomes indefinidos em relação à quantidade de tokens de  pronomes indefinidos no texto 




**Nome da Métrica**: indefinite_pronouns_diversity

**Interpretação**: não é clara a relação entre a métrica e a complexidade textual, mas é provável que pronomes indefinidos tornem o texto mais complexo

**Descrição da métrica**: Proporção  de types de  pronomes indefinidos em relação à quantidade de tokens de  pronomes indefinidos no texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes indefinidos são pronomes genéricos (nada, ninguém, alguém, nenhum, algum, qualquer, etc.). Tokens são todas as ocorrências das palavras; types são todas as ocorrências das palavras sem considerar repetições. 

**Forma de cálculo da métrica**: contam-se os pronomes indefinidos no texto, usando uma lista de pronomes indefinidos. Depois contam-se apenas as ocorrências diferentes, ou seja, se houver três ocorrências de “qualquer”, conta-se apenas uma vez. Finalmente, divide-se o resultado pela quantidade de pronomes indefinidos do texto.

**Recursos de PLN utilizados durante o cálculo**: tokenizador e lista de pronomes indefinidos

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Tudo que sempre quisemos é ver nossos filhos felizes. Ninguém imagina que há situações em que nada pode ser feito para garantir isso. Por isso, é difícil alguém se conformar diante das doenças terminais que acometem crianças. Aliás, ninguém se conforma.

**Contagens**: 5 tokens de pronomes indefinidos (tudo, ninguém, nada, alguém, ninguém), 4 types (tudo, ninguém, nada, alguém)

**Resultado Esperado**: 4/5 = 0,80

**Resultado Obtido**: 0,80

**Status**: correto




## Proporção de pronomes indefinidos em relação a todos os pronomes do texto




**Nome da Métrica**: indefinite_pronoun_ratio

**Interpretação**: é provável que pronomes indefinidos contribuam para maior complexidade textual

**Descrição da métrica**: Proporção de pronomes indefinidos em relação a todos os pronomes do texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes indefinidos são pronomes genéricos (nada, ninguém, alguém, nenhum, algum, qualquer, etc.).  

**Forma de cálculo da métrica**: identificam-se todos os pronomes do texto (tags: 'PROPESS','PROSUB', 'PROADJ', 'PRO-KS', 'PRO-KS-REL' do nlpnet); contam-se as ocorrências de pronomes indefinidos, usando uma lista de pronomes indefinidos para identificá-los; depois divide-se o resultado pela quantidade total de pronomes no texto. 

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet e lista de pronomes indefinidos.

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Minha primeira tentativa fracassou, mas agora eu atingi meu objetivo e obtive tudo o que eu queria. Ninguém, além de você, me ajudou. Sua colaboração foi muito importante para mim.

**Contagens**: 12 pronomes (minha, eu, meu, tudo, o, que, eu, ninguém, você, me, sua, mim), 2 pronomes indefinidos (tudo, ninguém)

**Resultado Esperado**: 2/12 = 0,167

**Resultado Obtido**: 0,167

**Status**: correto




## Proporção do operador lógico SE em relação à quantidade de palavras do texto




**Nome da Métrica**: if_ratio

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção do Operador Lógico “SE” em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: operadores lógicos são palavras que estabelecem relações lógicas no texto, como por exemplo: ou, e, se, não.

**Forma de cálculo da métrica**: contam-se as ocorrências de “SE” no texto e depois divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Se você vier me ver esta noite, por favor traga o livro que lhe pedi.

**Contagens**: 15 palavras, 1 operador lógico SE

**Resultado Esperado**: 1/15 = 0,066

**Resultado Obtido**: 0,066

**Status**: correto




## Proporção do operador lógico OU em relação à quantidade de palavras do texto




**Nome da Métrica**: or_ratio

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção do Operador Lógico “OU” em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: operadores lógicos são palavras que estabelecem relações lógicas no texto, como por exemplo: ou, e, se, não.

**Forma de cálculo da métrica**: contam-se as ocorrências de “OU” no texto e depois divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Ou ele ou você terá que resolver esse problema.

**Contagens**: 9 palavras, 2 operadores lógicos OU

**Resultado Esperado**: 2/9 = 0,222

**Resultado Obtido**: 0,222

**Status**: correto




## Proporção do operador lógico E em relação à quantidade de palavras do texto




**Nome da Métrica**: and_ratio

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção do  Operador Lógico “E” em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: operadores lógicos são palavras que estabelecem relações lógicas no texto, como por exemplo: ou, e, se, não.

**Forma de cálculo da métrica**: contam-se as ocorrências de “E” no texto e depois divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 38 palavras, 1 operador lógico E

**Resultado Esperado**: 1/38 = 0,026

**Resultado Obtido**: 0,026

**Status**: correto




## Proporção de Operadores Lógicos em relação à quantidade de palavras do texto



**Nome da Métrica**: logic_operators

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção de Operadores Lógicos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: operadores lógicos são palavras que estabelecem relações lógicas no texto, como por exemplo: ou, e, se, não.

**Forma de cálculo da métrica**: contam-se as palavras do texto que correspondam ao léxico de operadores lógicos, depois divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 38 palavras, 4 operadores lógicos (não, nenhuma, não, e)

**Resultado Esperado**: 4/38 = 0,105

**Resultado Obtido**: 0,105

**Status**: correto




## Proporção de palavras de polaridade positiva em relação a todas palavras do texto




**Nome da Métrica**: positive_words

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção de palavras com polaridade positiva em relação a todas as palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: polaridade positiva é uma característica psicolinguística das palavras de conteúdo

**Forma de cálculo da métrica**: identificam-se todas as palavras do texto que estão na lista de palavras com polaridade positiva no dicionário do LIWC; calcula-se a quantidade dessas palavras e divide-se o resultado pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: lista de palavras positivas do dicionário LWIC

**Limitações da métrica**:

**Crítica**: como apenas palavras de conteúdo possuem polaridade, deveria haver uma pré-seleção das palavras de conteúdo antes de consultar a lista de palavras positivas. A divisão do resultado deveria ser pela quantidade de palavras de conteúdo.

**Projeto**: Coh-Metrix-Dementia

**Teste**: Embora o celular seja lento, sua bateria é muito boa.

**Contagens**: 10 palavras, 2 palavras de polaridade positiva (muito e boa), 

**Resultado Esperado**: 0,20

**Resultado Obtido**: 0,20

**Status**: correto




## Proporção de palavras de polaridade negativa em relação a todas palavras do texto





**Nome da Métrica**: negative_words

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção de palavras com polaridade negativa em relação a todas as palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: polaridade negativa é uma característica psicolinguística das palavras de conteúdo

**Forma de cálculo da métrica**: identificam-se todas as palavras do texto que estão na lista de palavras com polaridade negativa do dicionário do LIWC; calcula-se a quantidade dessas palavras e divide-se o resultado pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: lista de palavras negativas do dicionário LWIC

**Limitações da métrica**:

**Crítica**: como apenas palavras de conteúdo possuem polaridade, deveria haver uma pré-seleção das palavras de conteúdo antes de consultar a lista de palavras negativas. A divisão do resultado deveria ser pela quantidade de palavras de conteúdo.

**Projeto**: Coh-Metrix-Dementia

**Teste**: Embora o celular seja lento, sua bateria é muito boa.

**Contagens**: 10 palavras, 2 palavras de polaridade negativa (lento), 

**Resultado Esperado**: 0,10

**Resultado Obtido**: 0,10

**Status**: correto




## Quantidade Média de Hiperônimos por verbo nas sentenças



**Nome da Métrica**: hypernyms_verbs

**Interpretação**: teoricamente, quanto menos hiperônimos tem uma palavra, menos complexa ela é; portanto, quanto menor a métrica, menor a complexidade textual

**Descrição da métrica**: Quantidade média de hiperônimos por verbo do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: primeiramente os verbos do texto são lematizados. Depois cada lema é procurado na Wordnet.Br. Se o verbo é encontrado, registra-se a quantidade de hiperônimos que ele possui. Somam-se as quantidades de hiperônimos de todos os verbos do texto encontrados na Wordnet.Br e divide-se o resultado pela quantidade desses verbos. Se o verbo não está na Wordnet.Br ele não participa do cálculo, mas se ele estiver e não possuir hyperônimos, ele participa do cálculo com 0 hiperônimos.

**Recursos de PLN utilizados durante o cálculo**: léxico do DELAF para lematizar as formas verbais e Wordnet.Br para procurar hiperônimos

**Limitações da métrica**: 

**Crítica**: a métrica não deveria considerar verbos auxiliares, pois quando um verbo é auxiliar ele tem uma função na gramática (tempo, aspecto, modalidade, construção de voz passiva) e não um “sentido”. Assim, os verbos que estiverem funcionando como auxiliares não têm hiperônimos.

**Projeto**: Coh-Metrix-Port

**Teste**: Ele sonha muito quando está acordado.

**Contagens**: 2 verbos: sonhar (3 hiperônimos), acordar (0 hiperônimos)

**Resultado Esperado**: 3/2 = 1,5

**Resultado Obtido**: 1,5

**Status**: correto




## Média das frequências absolutas das palavras de conteúdo do texto




**Nome da Métrica**: cw_freq

**Interpretação**: teoricamente, quanto maior a frequência das palavras, menor a complexidade do texto

**Descrição da métrica**: Média das frequências absolutas das palavras de conteúdo do texto

**Definição dos termos que aparecem na descrição da métrica**: frequência absoluta é a quantidade de vezes que uma palavra ocorre em um corpus, portanto, varia em função do tamanho do corpus; palavras de conteúdo são substantivos, verbos, adjetivos e advérbios.

**Forma de cálculo da métrica**: identificam-se todas as palavras de conteúdo no texto. Para cada uma delas, procura-se a frequência na lista de frequências do Corpus Brasileiro. Somam-se todas as frequências e divide-se o resultado pela quantidade de palavras de conteúdo do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet e lista de frequências do Corpus Brasileiro

**Limitações da métrica**: 

**Crítica**: 

O Corpus Brasileiro possui muitos vieses devido ao desbalanceamento de suas fontes de textos, portanto, suas frequências não são um bom reflexo das frequências de palavras na língua geral.

As formas do corpus não possuem classe gramatical e somam ocorrências de classes diferentes que possuem a mesma grafia (ex: “forma” – substantivo e “forma” – 3ª pessoa do singular do presente do indicativo do verbo formar). Por isso, ao se buscar uma palavra de conteúdo na lista de frequências, nem sempre se encontra apenas a frequência da palavra na categoria gramatical almejada.

A formatação do resultado está incorreta 

**Projeto**:  Coh-Metrix-Port

**Teste**: Acessório utilizado por adolescentes, o boné é um dos itens que compõem a vestimenta idealizada pela proposta.

**Contagens**: palavras de conteúdo: acessório, utilizado, adolescentes, boné, é, itens, compõem, vestimenta, idealizada, proposta. Frequências respectivas: 1.616, 78.716, 53.937, 1.615, 5.325.656, 32.350, 17.961, 773, 1.908, 135.451.

**Resultado Esperado**: 5.649.983

**Resultado Obtido**: 564998.3

**Status**: correto




## Proporção de Conectivos em relação à quantidade de palavras do texto



**Nome da Métrica**: conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: proporção de conectivos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos são palavras que “ligam” partes do discurso, estabelecendo algum tipo de relação discursiva. O termo tem sobreposição com o termo “marcador discursivo”. 

**Forma de cálculo da métrica**: contam-se todos os conectivos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual. A lista de conectivos apresenta dois tipos de atributos: função (aditivo, causal, lógico ou temporal) e efeito no evento (conectivos positivos estendem eventos, enquanto que conectivos negativos param eventos) 

**Projeto**: Coh-Metrix-Port 

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 6 conectivos (e, e, como, e, se, e), 95 palavras

**Resultado Esperado**: 6/95 = 0,063

**Resultado Obtido**: 0,063

**Status**: correto




## Proporção de conectivos  aditivos positivos em relação à quantidade de palavras do texto




**Nome da Métrica**: add_pos_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos aditivos positivos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos aditivos positivos são, por exemplo: “bem como”, “além disso”, “em vez de”

**Forma de cálculo da métrica**: contam-se todos os conectivos aditivos positivos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 5 conectivos aditivos positivos (e, e, como, e, e), 95 palavras

**Resultado Esperado**: 5/95 = 0,053

**Resultado Obtido**: 0,053

**Status**: correto




## Proporção de conectivos  aditivos negativos em relação à quantidade de palavras do texto




**Nome da Métrica**: add_neg_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos aditivos negativos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos aditivos negativos são, por exemplo: “mas”, “porém”, “antes”, “todavia”.

**Forma de cálculo da métrica**: contam-se todos os conectivos aditivos negativos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos 

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual. Os conectivos aditivos negativos são, em sua maioria, conjunções adversativas.

**Projeto**: Coh-Metrix-Port

**Teste**: Entretanto, foram encontrados vários problemas clássicos.

**Contagens**: 1 conectivo aditivo negativo (entretanto) e 6 palavras 

**Resultado Esperado**: 1/6 = 0,16

**Resultado Obtido**: 0,16

**Status**: correto




## Proporção de conectivos  temporais positivosem relação à quantidade de palavras do texto




**Nome da Métrica**: tmp_pos_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos temporais positivos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos temporais positivos são, por exemplo: “assim”, ”outra vez”, ”imediatamente”

**Forma de cálculo da métrica**: contam-se todos os conectivos temporais positivos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: Enquanto isso, mais de 100 pessoas tentaram resolver o problema, o que finalmente começou a dar resultados.

**Contagens**: 2 conectivos temporais (enquanto, finalmente), 17 palavras

**Resultado Esperado**: 2/17 = 0,118

**Resultado Obtido**: 0,118

**Status**: correto




## Proporção de conectivos  temporais negativos em relação à quantidade de palavras do texto



**Nome da Métrica**: tmp_neg_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos temporais negativos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: só há 1 conectivo temporal negativo na lista de conectivos: “até que” 

**Forma de cálculo da métrica**: contam-se todos os conectivos temporais negativos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diversas categorias utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: O menino colou na prova até que a professora descobriu sua artimanha.

**Contagens**: 1 conectivos temporal negativo (até que), 12 palavras

**Resultado Esperado**: 1/12 = 0,083

**Resultado Obtido**: 0,083

**Status**: correto




## Proporção de conectivos  causais positivos em relação à quantidade de palavras do texto




**Nome da Métrica**: cau_pos_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos causais positivos em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos causais positivos são, por exemplo: “habilita”, “para”, “se”, “somente se”, “assim”

**Forma de cálculo da métrica**: contam-se todos os conectivos causais positivos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: O menino queria ir bem na prova. Para isso, ele resolveu colar.

**Contagens**: 1 conectivo causal positivo (para isso), 12 palavras

**Resultado Esperado**: 1/12 = 0,083

**Resultado Obtido**: 0,083

**Status**: correto




## Proporção de conectivos  causais negativos em relação à quantidade de palavras do texto



**Nome da Métrica**: cau_neg_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos causais negativos em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: há 6 conectivos causais negativos na lista de conectivos: mesmo embora, contudo, no entanto, apesar de, apesar disso, apesar disto, a menos que.

**Forma de cálculo da métrica**: contam-se todos os conectivos causais negativos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: Embora tenha colado na prova, o menino não obteve uma boa nota.

**Contagens**: 1 conectivo causal negativo (embora), 12 palavras

**Resultado Esperado**: 1/12 = 0,083

**Resultado Obtido**: 0,083

**Status**: correto




## Proporção de Conectivos Lógicos Positivos em relação à quantidade de palavras do texto



**Nome da Métrica**: log_pos_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: Proporção de conectivos lógicos positivos em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos lógicos positivos são, por exemplo: similarmente, por outro lado, de novo, somente se, assim, para este fim.

**Forma de cálculo da métrica**: contam-se todos os conectivos lógicos positivos do texto, usando uma lista de conectivos para identificá-los, e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Vários deles estão em mais de uma categoria e alguns não são conjunções nem locuções adverbiais clássicos. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: Desde que o menino começou a colar nas provas, ele não estuda mais.

**Contagens**: 1 conectivo lógico positivo (desde que), 13 palavras

**Resultado Esperado**: 1/13 = 0,076

**Resultado Obtido**: 0,076

**Status**: correto




## Proporção de Conectivos Lógicos Negativos em relação à quantidade de palavras do texto




**Nome da Métrica**: log_neg_conn_ratio

**Interpretação**: não está clara a relação entre proporção de conectivos e complexidade textual

**Descrição da métrica**: proporção de conectivos lógicos negativos em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: conectivos lógicos negativos são, por exemplo: pelo contrário, ainda, cada vez que, embora.

**Forma de cálculo da métrica**: contam-se todos os conectivos lógicos negativos do texto, usando uma lista de conectivos para identificá-los e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: lista de conectivos

**Limitações da métrica**: por usar uma lista de palavras, pode haver imprecisão, pois uma mesma palavra pode funcionar como conectivo em alguns contextos e não em outros

**Crítica**: os conectivos são palavras funcionais de diferentes categorias, utilizados para análise das funções discursivas. Não está clara sua utilidade para aferição de complexidade textual.

**Projeto**: Coh-Metrix-Port

**Teste**: O menino colou na prova, embora soubesse que poderia ser pego.

**Contagens**: 1 conectivo lógico negativo (embora), 11 palavras

**Resultado Esperado**: 1/11 = 0,090

**Resultado Obtido**: 0,090

**Status**: correto




## Proporção de Palavras Funcionais em relação à quantidade de palavras do texto




**Nome da Métrica**: function_words

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: porcentagem de palavras funcionais em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras funcionais as palavras de 6 classes gramaticais: artigos (tag: ‘ART’), conjunções (tags ‘KS’ e ‘KC’), interjeições (tag: ‘IN’), numerais (tag: ‘NUM’), pronomes (tags: 'PROPESS',

'PROSUB', 'PROADJ', 'PRO-KS', 'PRO-KS-REL'), preposições (tags: 'PREP', 'PREP+PROPESS', 'PREP+ART', 'PREP+PRO-KS', 'PREP+PRO-KS-REL', 'PREP+PROADJ', 'PREP+ADV', 'PREP+PROSUB'). Incluem-se nas palavras funcionais os advérbios com função coordenativa e subordinativa (tags: 'ADV-KS', 'ADV-KS-REL). ', 

**Forma de cálculo da métrica**: contam-se as palavras funcionais do texto e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**:  

**Crítica**: 

**Projeto**:  Coh-Metrix-Port

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta. 

**Contagens**: 69 palavras, 27 palavras funcionais

**Resultado Esperado**: 0,391

**Resultado Obtido**: 0,391

**Status**: correto




## Proporção de palavras de conteúdo em relação à quantidade de palavras do texto




**Nome da Métrica**: content_words

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: proporção de palavras de conteúdo em relação ao total de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo as palavras de 5 classes de etiquetas do tagger nlpnet: substantivos (tags N, NPROP), verbos (tags V, VAUX, PCP), adjetivos (tag ADJ), advérbios (tag ADV) e palavras denotativas (tag PDEN).

**Forma de cálculo da métrica**: contam-se as palavras de conteúdo e divide-se o resultado pela quantidade de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: a precisão da métrica depende do desempenho do tagger.

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 38 palavras, 27 palavras de conteúdo

**Resultado Esperado**: 27/38 = 0,711

**Resultado Obtido**: 0,711

**Status**: correto




## Proporção de pronomes em relação à quantidade de palavras do texto



**Nome da Métrica**: pronoun_ratio

**Interpretação**: supõe-se que, quanto maior o valor da métrica, maior a complexidade textual

**Descrição da métrica**: proporção de pronomes em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se as ocorrências de pronomes (tags: 'PROPESS',

'PROSUB', 'PROADJ', 'PRO-KS', 'PRO-KS-REL',) e divide-se pelo total de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**:  

**Crítica**: 

**Projeto**:  Coh-Metrix-Port

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 2 pronomes, 69 palavras

**Resultado Esperado**: 2/69 = 0,029

**Resultado Obtido**: 0,029

**Status**: correto




## Proporção de Adjetivos em relação à quantidade de palavras do texto




**Nome da Métrica**: adjective_ratio

**Interpretação**: supõe-se que, quanto maior o valor da métrica, maior a complexidade textual

**Descrição da métrica**: proporção de adjetivos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se as ocorrências de adjetivos (tag ‘ADJ’) e divide-se pelo total de palavras do texto

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 6 adjetivos, 95 palavras

**Resultado Esperado**: 6/95 = 0,063

**Resultado Obtido**: 0,063

**Status**: correto




## Quantidade de Palavras no texto




**Nome da Métrica**: words

**Interpretação**: quanto maior a quantidade de palavras, maior a complexidade textual

**Descrição da métrica**: quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todos os tokens (descontando as pontuações)

**Recursos de PLN utilizados durante o cálculo**: nltk toolkit

**Limitações da métrica**: a contagem depende do critério de tokenização adotado (separação das contrações, união de multiwords, união de nomes próprios)

**Crítica**: o ideal é que o classificador adote uma única forma de tokenização para contagem de palavras

**Projeto**:  Coh-Metrix-Port

**Teste**: Acessório utilizado por adolescentes, o boné é um dos itens que compõem a vestimenta idealizada pela proposta.

**Contagens**: 17 palavras

**Resultado Esperado**: 17

**Resultado Obtido**: 17

**Status**: correto




## Quantidade de Parágrafos no texto



**Nome da Métrica**: paragraphs

**Interpretação**: quanto maior o número de parágrafos, maior a complexidade textual

**Descrição da métrica**: quantidade de parágrafos do texto. 

**Definição dos termos que aparecem na descrição da métrica**: são consideradas marcas de parágrafos somente a quebra de linha e não identações.

**Forma de cálculo da métrica**: contam-se os parágrafos do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**:  Coh-Metrix-Port

**Teste**: 

Os vermes – também chamados de helmintos – são parasitos, animais que, em geral, dependem da relação com outros seres para viver.

Eles podem se hospedar no organismo de diversos animais, como bois, aves e peixes. Por isso, podemos também contraí-los comendo carnes cruas ou mal cozidas.

**Contagens**: 2 parágrafos

**Resultado Esperado**: 2

**Resultado Obtido**: 2

**Status**: correto




## Proporção de Verbos em relação à quantidade de palavras do texto



**Nome da Métrica**: verbs

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção de verbos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências de verbos (tags 'V', 'VAUX', 'PCP') no texto e divide-se pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**:  

**Crítica**: Essa métrica usa tokenização sem fazer descontrações. É preciso uniformizar essa escolha em todas as métricas

**Projeto**:  Coh-Metrix-Port

**Teste**: Acessório utilizado por adolescentes, o boné é um dos itens que compõem a vestimenta idealizada pela proposta

**Contagens**: 4 verbos, 17 palavras

**Resultado Esperado**: 0,235

**Resultado Obtido**: 0,235

**Status**: correto




## Quantidade média de sílabas por palavra no texto




**Nome da Métrica**: syllables_per_content_word

**Interpretação**: quanto maior o número de sílabas por palavras, maior a complexidade textual

**Descrição da métrica**: Número médio de sílabas por palavras de conteúdo no texto

**Definição dos termos que aparecem na descrição da métrica**: são palavras de conteúdo as palavras de 4 classes gramaticais: substantivos, verbos, adjetivos e advérbios. São consideradas palavras de conteúdo as palavras de 5 categorias de etiquetas do tagger nlpnet: substantivos (tags N, NPROP), verbos (tags V, VAUX, PCP), adjetivos (tag ADJ), advérbios (tag ADV) e palavras denotativas (tag PDEN).

**Forma de cálculo da métrica**: contam-se as sílabas das palavras de conteúdo e depois divide-se o resultado pela quantidade de palavras de conteúdo.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**:  

**Crítica**: 

**Projeto**:  Coh-Metrix-Port

**Teste**: Acessório utilizado por adolescentes, o boné é um dos itens que compõem a vestimenta idealizada pela proposta

**Contagens**: 10 palavras de conteúdo (acessório, utilizado, adolescentes, boné, itens, compõem, idealizada, vestimenta, proposta), 35 sílabas (o silabificador considera “acessório” proparoxítona)

**Resultado Esperado**: 35/10 = 3,5

**Resultado Obtido**: 3,5

**Status**: correto 




## Média de Palavras por Sentença




**Nome da Métrica**: words_per_sentence

**Interpretação**: quanto maior a métrica, maior a complexidade

**Descrição da métrica**: Número de palavras dividido pelo número de sentenças

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: divide-se o total de palavras do texto pelo número de sentenças do texto

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 95 palavras e 4 sentenças

**Resultado Esperado**: 95/4 = 23,75

**Resultado Obtido**: 23,75

**Status**: correto




## Proporção de Verbos no Pretérito Perfeito Simples do Indicativo em relação à quantidade de verbos flexionados no texto




**Nome da Métrica**: indicative_preterite_perfect_ratio

**Interpretação**: o pretérito perfeito simples do indicativo é um tempo frequente. Pode ocorrer em textos de diferentes níveis de complexidade. Não está claro qual sua relação com o nível de complexidade do texto.

**Descrição da métrica**: proporção de verbos no pretérito perfeito simples do modo indicativo, em relação ao total de verbos do texto

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta V.*PS.*IND e divide-se o resultado pelo total de verbos do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: GUTEN

**Teste 1**: 

Robert Lustig trabalha como endocrinologista pediátrico na Universidade da Califórnia, especializado no tratamento da obesidade infantil. Em 2009, ele proferiu a palestra “Açúcar: a amarga verdade”, que teve mais de 6 milhões de visualizações no YouTube. No decorrer de uma hora e meia, Lustig defende com veemência que a frutose, um açúcar onipresente na alimentação moderna, é o “veneno” responsável pela epidemia de obesidade nos Estados Unidos.

**Contagens**: 6 verbos, 3 no presente, 2 no pretérito perfeito 

**Resultado Esperado**: 2/5 = 0,40  

**Resultado Obtido**: 0,40

**Status**: correto




## Proporção de verbos no gerúndio em relação a todos os verbos do texto



**Nome da Métrica**: gerund_verbs

**Interpretação**: não é clara a relação entre a presença de verbos no particípio e nível de complexidade

**Descrição da métrica**: Proporção de verbos no particípio em relação a todos os verbos do texto.

**Definição dos termos que aparecem na descrição da métrica**: verbos no particípio possuem formas regulares e irregulares. Alguns verbos têm as duas formas, como salvar: salvado, salvo. 

**Forma de cálculo da métrica**: contam-se todos os verbos (etiqueta V do parser Palavras) e todos os verbos no particípio (etiqueta V PCP). Divide-se a quantidade de verbos no particípio pela quantidade total de verbos.

**Recursos de PLN utilizados durante o cálculo**: tagger do parser Palavras

**Limitações da métrica**: 

**Crítica**: verbos no particípio são ambíguos com adjetivos e substantivos derivados de particípio. O parser quase sempre classifica todos como verbos, o que pode levar a uma superestimativa da quantidade de particípios.

**Projeto**: AIC

**Teste**: Estamos fazendo uma inspeção preventiva em todos os sistemas de alarme que tenham sido instalados na fábrica há mais de 5 anos, visando detectar mau funcionamento.

**Contagens**: 8 verbos, 2 no gerúndio (fazendo e visando), mas o parser não reconhece “há” como verbo , então são 7 verbos reconhecidos.

**Resultado Esperado**: 2/7 = 0,286

**Resultado Obtido**: 0,286

**Status**: correto




## Proporção de verbos no infinitivo em relação a todos os verbos do texto



**Nome da Métrica**: infinitive_verbs

**Interpretação**: não é clara a relação entre a presença de verbos no infinitivo e nível de complexidade

**Descrição da métrica**: Proporção de verbos no infinitivo em relação a todos os verbos do texto.

**Definição dos termos que aparecem na descrição da métrica**: verbos no infinitivo são aqueles não flexionados, teminados em –ar, -er, -ir e –or: falar, ler, sorrir, compor.

**Forma de cálculo da métrica**: contam-se todos os verbos (etiqueta V do parser Palavras) e todos os verbos no infinitivo (etiqueta V INF). Divide-se a quantidade de verbos no infinitivo pela quantidade total de verbos.

**Recursos de PLN utilizados durante o cálculo**: tagger do parser Palavras

**Limitações da métrica**: o parser classifica todas as palavras desconhecidas ou ambíguas como verbos, desde que tenham terminação igual à dos verbos. Assim, palavras como “placar” e “[o] jantar” (refeição), são anotadas como verbos infinitivos. 

**Crítica**: 

**Projeto**: AIC

**Teste**: É importante atentar para os testes que têm sido feitos após a retirada do país da Comunidade Europeia.

**Contagens**: 5 verbos (é, atentar, têm, sido, feitos), 1 no infinitivo (atentar)

**Resultado Esperado**: 1/5 = 0,20

**Resultado Obtido**: 0,20

**Status**: correto




## Proporção de verbos no particípio em relação a todos os verbos do texto



**Nome da Métrica**: participle_verbs

**Interpretação**: não é clara a relação entre a presença de verbos no particípio e nível de complexidade

**Descrição da métrica**: Proporção de verbos no particípio em relação a todos os verbos do texto.

**Definição dos termos que aparecem na descrição da métrica**: verbos no particípio são formas não flexionadas, que podem ser regulares (teminados em –ado, -ido) ou irregulares. Ex: formado, falado, comido, tido, sido, (formas regulares), composto, morto, aberto (irregulares). Além de atuarem como verbos em formas compostas e orações reduzidas, as formas do particípio podem constituir substantivos e adjetivos (ex: aposentado, sentido, vestido, cansado).

**Forma de cálculo da métrica**: contam-se todos os verbos (etiqueta V do parser Palavras) e todos os verbos no particípio (etiqueta V PCP). Divide-se a quantidade de verbos no particípio pela quantidade total de verbos.

**Recursos de PLN utilizados durante o cálculo**: tagger do parser Palavras

**Limitações da métrica**: o parser não distingue a função do particípio (verbo, substantivo, adjetivo), exceto quando um artigo o precede (ex: o vestido). Isso pode levar a uma superestimativa dessa forma verbal.

**Crítica**: 

**Projeto**: AIC

**Teste**: É importante atentar para os testes que têm sido feitos após a retirada do país da Comunidade Europeia.

**Contagens**: 5 verbos (é, atentar, têm, sido, feitos), 2 no particípio (sido, feitos)

**Resultado Esperado**: 2/5 = 0,40

**Resultado Obtido**: 0,40

**Status**: correto




## Proporção de substantivos abstratos em relação à quantidade de palavras do texto




**Nome da Métrica**: abstract_nouns_ratio

**Interpretação**: substantivos abstratos são mais complexos que substantivos concretos, portanto, quanto maior a proporção desses substantivos, maior a complexidade.

**Descrição da métrica**: Proporção de substantivos abstratos em relação à quantidade de palavras do texto

**Definição dos termos que aparecem na descrição da métrica**: para fins desta métrica, são considerados substantivos abstratos os substantivos terminados com os sufixos -mento, -ção, -são, -agem, -mento, -ura, -ncia, -dela, -ria.

**Forma de cálculo da métrica**: filtram-se todos os substantivos e contam-se aqueles que possuem a terminação definida para a métrica. Depois divide-se o resultado pelo total de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**:  a principal limitação é de ordem conceitual. Sem um stemmer (separador de radicais), não é possível saber se a terminação é sufixo ou não. Por exemplo, -ção é sufixo em “profissionalização”, mas não é sufixo em “ração”. Além disso, a métrica parte do pressuposto de que há sufixos exclusivos de palavras abstratas, o que não é verdadeiro. Por exemplo:  sangramento, folhagem, ranhura e padaria apresentam as terminações definidas para a métrica e são palavras com alto grau de concretude. Por outro lado, há palavras abstratas derivadas de verbo que não são capturadas, como “coordenadora”, como no exemplo-teste.

**Crítica**: como se trata de um tipo de substantivo, o ideal seria calcular a proporção em relação ao total de substantivos

**Projeto**: GUTEN

**Teste**: A coordenadora de Memória da Secretaria de Cultura, Miriam Avruch, garante que metade do valor já foi paga.

**Contagens**: 3 substantivos com as terminações definidas: memória, secretaria, cultura e 18 palavras

**Resultado Esperado**: 0,167 (3/18)

**Resultado Obtido**: 0,167

**Status**: correto




## Quantidade média de sentenças por parágrafo no texto




**Nome da Métrica**: sentences_per_paragraph

**Interpretação**: não está clara a relação entre a métrica  e a complexidade textual

**Descrição da métrica**: média da quantidade de sentenças por parágrafo.

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: Divide-se o número de sentenças pelo número de parágrafos.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**: 

**Crítica**: Essa medida não tem uma relação direta com a complexidade. Se as sentenças forem pequenas, o texto é simples e se as sentenças forem longas, o texto é mais complexo. O processo de simplificação produz mais sentenças por parágrafo devido à operação de divisão de sentenças longas. Nesse caso, o parágrafo original, mais complexo, tem menos sentenças que o parágrafo simplificado.

**Projeto**: Coh-Metrix-Port

**Teste**: Se, como parece cada vez mais provável, as diretrizes nutricionais que seguimos por quarenta anos estavam profundamente equivocadas, tal erro não pode ser posto na conta dos bichos-papões das grandes empresas. Tampouco pode ser considerado um engano científico inócuo. O massacre sofrido por John Yudkin contradiz essa interpretação e sugere ter ocorrido um erro que os cientistas impuseram a si próprios – e, por consequência, a todos nós.

Tendemos a pensar que os hereges são pessoas que nadam contra a corrente, indivíduos inclinados a desafiar o conhecimento dominante. Às vezes, porém, um herege é apenas um pensador convencional que permanece olhando na mesma direção, ao passo que todos os demais passaram a olhar na direção contrária. Quando, em 1957, John Yudkin aventou pela primeira vez a possibilidade de o açúcar representar um perigo para a saúde pública, a hipótese foi levada a sério, assim como seu proponente. Ao se aposentar, catorze anos depois, tanto a teoria como seu autor haviam sido ridicularizados e marginalizados. Somente agora, postumamente, é que seu trabalho vem sendo reconduzido ao pensamento científico consolidado.

**As guinadas na avaliação do legado de Yudkin pouco têm a ver com a metodologia científica**: devem-se em grande medida ao comportamento não científico da ciência da nutrição ao longo dos anos. Essa história começou a vir à tona na última década, menos por obra de nutricionistas de peso do que por céticos em relação à ciência nutricional. Na pesquisa meticulosa que resultou no livro “The Big Fat Surprise”(A Surpresa Grande e Gorda), a jornalista Nina Teicholz investiga o postulado “gordura saturada provoca doença cardíaca”, e revela que a passagem de teoria controversa a verdade aceita não ocorreu pela comprovação, e sim graças à influência de umas poucas personalidades poderosas – e de uma delas em particular.

Teicholz também descreve como todo um establishment de importantes cientistas nutricionais, inseguro quanto à própria autoridade médica e atento a ameaças a ela, perpetrou tanto a defesa contínua e exagerada de uma alimentação com baixo teor de gordura, quanto o ataque a quem oferecia indícios ou argumentos contrários. John Yudkin foi apenas a primeira e mais célebre vítima.

Hoje, enquanto nutricionistas lutam para compreender um desastre que não previram – mas decerto podem ter deflagrado –, a ciência da nutrição passa por um doloroso período de reavaliação. Aos poucos, evita proibições relativas ao colesterol e à gordura, enquanto intensifica advertências ao uso do açúcar, sem, no entanto, recuar por completo. Seus representantes mais antigos, porém, seguem munidos de um instinto corporativo que os leva a difamar quem desafia, em alto e bom som, aquele conhecimento em ruínas. É isso que Teicholz vem experimentando nos últimos tempos.

**Contagens**: 17 sentenças e 5 parágrafos

**Resultado Esperado**: 3,4

**Resultado Obtido**: 3,4

**Status**: correto




## Quantidade Média de preposições por sentença no texto





**Nome da Métrica**: prepositions_per_sentence

**Interpretação**: não está clara a relação entre o uso de preposições e a complexidade textual 

**Descrição da métrica**: Média de preposições por sentença:

**Definição dos termos que aparecem na descrição da métrica**: preposições são palavras que pertencem a uma classe gramatical fechada (finita). São classificadas como palavras funcionais, ou seja, têm uma função na sintaxe, mas não têm conteúdo isoladamente.

**Forma de cálculo da métrica**: contam-se as ocorrências da etiqueta PRP e divide-se o resultado pelo número de sentenças do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: AIC

**Teste**: Nem é preciso argumentar contra a ineficiência do sistema prisional brasileiro. Ele foi reprovado por todas as pessoas para as quais foi solicitada uma avaliação. Nele não se pode confiar e dele não se pode esperar nada além do estímulo à violência.

**Contagens**: 8 preposições, 3 sentenças

**Resultado Esperado**: 2,66

**Resultado Obtido**: 2,66

**Status**: correto




## Proporção de preposições em relação à quantidade de orações no texto




**Nome da Métrica**: prepositions_per_clause

**Interpretação**: não está clara a relação entre o uso de preposições e a complexidade textual 

**Descrição da métrica**: Média de preposições por sentença:

**Definição dos termos que aparecem na descrição da métrica**: preposições são palavras que pertencem a uma classe gramatical fechada (finita). São classificadas como palavras funcionais, ou seja, têm uma função na sintaxe, mas não têm significado isoladamente.

**Forma de cálculo da métrica**: contam-se as ocorrências da etiqueta PRP e divide-se o resultado pelo número de orações do texto. O número de orações é obtido contando-se as ocorrências de verbos menos as ocorrências de verbos auxiliares. (V-aux).

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: AIC

**Teste**: Nem é preciso argumentar contra a ineficiência do sistema prisional brasileiro. Ele foi reprovado por todas as pessoas para as quais foi solicitada uma avaliação. Nele não se pode confiar e dele não se pode esperar nada além do estímulo à violência.

**Contagens**: 8 preposições, 6 orações

**Resultado Esperado**: 1,33

**Resultado Obtido**: 1,33

**Status**: correto




## Proporção de pronomes possessivos nas primeiras pessoas em relação à quantidade de pronomes possessivos do texto




**Nome da Métrica**: first_person_possessive_pronouns

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: proporção de pronomes possessivos de primeira pessoa em relação à quantidade total de pronomes possessivos no texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes possessivos indicam posse. Os das primeiras pessoas são: meu, meus, minha, minhas, nosso, nossos, nossa, nossas.

**Forma de cálculo da métrica**: contam-se as ocorrências das etiquetas <poss 1S> e <poss 1P>, pronomes possessivos de primeira pessoa no singular e no plural, respectivamente. Divide-se o resultado pela soma de todos os pronomes possessivos do texto (<poss 1S>, <poss 1P>, <poss 2S>, <poss 2P>, <poss 3S>, <poss 3P>)

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger

**Limitações da métrica**: 

**Crítica**: os pronomes pessoais e possessivos nas primeiras pessoas, assim como os verbos flexionados nas primeiras pessoas constituem marcas de textos em que o autor revela sua opinião. A métrica deveria juntar as três ocorrências e não apenas os pronomes possessivos.

**Projeto**: AIC

**Teste**: Minha primeira tentativa fracassou, mas agora eu atingi meu objetivo. Seu apoio foi muito importante para mim. Obrigada por sua dedicação, prova do quanto é forte nossa amizade.

**Contagens**: 3 pronomes possessivos na primeira pessoa (minha, meu, nossa), 1 pronome pessoal na primeira pessoa (eu), 1 pronome oblíquo na primeira pessoa (mim), 2 pronomes possessivos na terceira pessoa (seu, sua). 

**Resultado Esperado**: 3/5 = 0,60

**Resultado Obtido**: 0,60

**Status**: correto




## Proporção de pronomes possessivos nas segundas pessoas em relação à quantidade de pronomes possessivos do texto




**Nome da Métrica**: second_person_possessive_pronouns

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: proporção de pronomes possessivos de segunda pessoa em relação à quantidade total de pronomes possessivos no texto

**Definição dos termos que aparecem na descrição da métrica**: pronomes possessivos indicam posse. Os das segundas pessoas são: teu, teus, tua, tuas, vosso, vossos, vossa, vossas.

**Forma de cálculo da métrica**: contam-se as ocorrências das etiquetas <poss 2S> e <poss 2P>, pronomes possessivos de segunda pessoa no singular e no plural, respectivamente. Divide-se o resultado pela soma de todos os pronomes possessivos do texto (<poss 1S>, <poss 1P>, <poss 2S>, <poss 2P>, <poss 3S>, <poss 3P>)

**Recursos de PLN utilizados durante o cálculo**: parser Palavras na função de POS tagger

**Limitações da métrica**: no português brasileiro as formas de segunda pessoa foram suplantadas pelo uso de “você” e “vocês”, que usam a flexão e os pronomes possessivos de terceira pessoas. Portanto, não é possível distinguir os possessivos que se referem a “você” e “vocês” dos possessivos que se referem a “ele, ela, eles, elas”.

**Crítica**: 

**Projeto**: AIC

**Teste**: Minha primeira tentativa fracassou, mas agora eu atingi meu objetivo. Teu apoio foi muito importante para mim. Obrigada por tua dedicação, prova do quanto é forte nossa amizade.

**Contagens**: 2 pronomes possessivos na segunda pessoa (teu, tua) e 3 pronomes possessivos na primeira pessoa (minha, meu, nossa). 

**Resultado Esperado**: 2/5 = 0,40

**Resultado Obtido**: 0,40

**Status**: correto




## Proporção de pronomes pessoais nas primeiras pessoas em relação à quantidade de pronomes pessoais do texto




**Nome da Métrica**: first_person_pronouns

**Interpretação**: a primeira pessoa é marca de texto pessoal, mas não está clara sua relação com complexidade textual

**Descrição da métrica**: Proporção de pronomes pessoais nas primeiras pessoas em relação a todos os pronomes pessoais do texto.

**Definição dos termos que aparecem na descrição da métrica**: pronomes pessoais são: eu, tu, você, ele, ela, nós, vós, vocês, eles, elas. Pronomes pessoais de primeiras pessoas são: eu e nós. 

**Forma de cálculo da métrica**: contam-se as ocorrências de pronomes pessoais de primeiras pessoas e divide-se pelo total de pronomes pessoais.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Críticas**: 

1) Para identificar textos na primeira pessoa, seria necessário somar pronomes pessoais e possessivos nas primeiras pessoas e verbos conjugados nas primeiras pessoas. É muito comum a supressão dos pronomes pessoais de primeira pessoas, pois a flexão verbal já é marca suficiente de pessoa. 

2) Seria importante computar o pronome de primeira pessoa “a gente”, que no português brasileiro é comum. Esse pronome é de primeira pessoa do plural (corresponde a “nós”), mas usa flexão de terceira pessoa do singular.

**Projeto**: AIC

**Teste 1**: 

Após muitas viagens, esse é meu primeiro relato.  Estou praticamente sendo obrigado a relatar, impelido por gratidão a todos e por achar que as informações pra esse destino estão um pouco confusas. Minha tentativa é ajudar um pouco mais aqueles que buscam informações sobre essa área, El Chalten e El Calafate, e quem sabe encorajar outros viajantes! Somos um casal de mochileiros e viajamos com a economia sempre sendo uma premissa de viagem. Não temos metas restritas de gastar 1 dólar por dia nem nada muito radical, mas evitamos gastar dinheiro desnecessariamente. O orçamento é curto e exige sacrifícios, o nosso dinheiro não dá pra viajar sem nos preocuparmos com despesas. Portanto, sacrificamos alguns dedos para salvar a mão. Não fazemos questão de luxo em hospedagens nem em restaurantes e sempre que possível fazemos tudo por nossa conta.

**Contagens**: nenhum pronome pessoal, 3 pronomes possessivos na terceira pessoa e 9 verbos flexionados nas primeiras pessoas.

**Resultado Esperado**: 0,0

**Resultado Obtido**: 0,0

**Status**: correto

**Teste 2**: Eu nunca mais deixei ninguém lembrar nada de nós. Mas eles insistem em dizer que eu deveria conversar sobre nossa relação.

**Contagens**: 4 pronomes pessoais, sendo 3 de primeiras pessoas

**Resultado Esperado**: 0,75

**Resultado Obtido**: 0,75

**Status**: correto




## Proporção de pronomes pessoais nas segundas pessoas em relação à quantidade de pronomes pessoais do texto



**Nome da Métrica**: second_person_pronouns

**Interpretação**: a segunda pessoa é marca de “diálogo” com o leitor em textos jornalísticos, o que está associado com menor complexidade textual

**Descrição da métrica**: Proporção de pronomes pessoais nas segundas pessoas em relação a todos os pronomes pessoais do texto.

**Definição dos termos que aparecem na descrição da métrica**: pronomes pessoais são: eu, tu, você, ele, ela, nós, vós, vocês, eles, elas. Pronomes pessoais de segunda pessoa são: tu e vós.

**Forma de cálculo da métrica**: contam-se as ocorrências de pronomes pessoais de segunda pessoa e divide-se pelo total de pronomes pessoais.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

1) Para identificar a segunda pessoa, é preciso incluir os pronomes pessoais “você” e “vocês”, que usam a flexão verbal de terceira pessoa, mas são efetivamente segundas pessoas no discurso.

2) A métrica não está contando os pronomes pessoais “você” e “vocês” em nenhuma das pessoas, mas está computando-os no total de pronomes. 

**Projeto**: AIC

**Teste 1**: Você já percebeu como é difícil decorar todos aqueles nomes de compostos orgânicos? Aqui nós propomos uma série de dicas para você não esquecer e nem confundir os nomes.

**Contagens**: 2 pronomes pessoais na segunda pessoa (você, você) e 1 na primeira pessoa do plural (nós). 

**Resultado Esperado**: 2/3 = 0,67

**Resultado Obtido**: 0,67 

**Status**: correto




## Proporção de pronomes pessoais nas terceiras pessoas em relação à quantidade de pronomes pessoais do texto



**Nome da Métrica**: third_person_pronouns

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção de pronomes pessoais nas terceiras pessoas em relação a todos os pronomes pessoais do texto.

**Definição dos termos que aparecem na descrição da métrica**: pronomes pessoais são: eu, tu, você, ele, ela, nós, vós, vocês, eles, elas. Pronomes pessoais de terceira pessoa são: ele, ela, eles, elas.

**Forma de cálculo da métrica**: contam-se as ocorrências de pronomes pessoais de terceira pessoa e divide-se pelo total de pronomes pessoais.

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**: a forma “a gente” funciona como um pronome de primeira pessoa do plural (que conjuga o verbo na terceira pessoa do singular), mas não é reconhecida pelo POS tagger.

**Crítica**: 

**Projeto**: AIC

**Teste 1**: Você já viu um fantasma? Eu nunca vi, mas eles são tão comuns nos filmes que a gente fica imaginando se eles não existem mesmo. 

**Contagens**: 2 pronomes pessoais na terceira pessoa, 1 na primeira pessoa e 1 na segunda pessoa. 

**Resultado Esperado**: 2/4 = 0,50

**Resultado Obtido**: 0,50 

**Status**: correto




## Proporção de pronomes pessoais que indicam uma conversa com o leitor em relação à quantidade de pronomes pessoais do texto



**Nome da Métrica**: dialog_pronoun_ratio

**Interpretação**: textos que estabelecem diálogo com o leitor têm menor complexidade, portanto, quanto maior o resultado, menor a complexidade.

**Descrição da métrica**: proporção de pronomes pessoais que indicam uma conversa com o leitor em relação ao total de pronomes pessoais presentes no texto. 

**Definição dos termos que aparecem na descrição da métrica**: pronomes pessoais que indicam uma conversa com o leitor são: "eu", "tu", "você" e "vocês".

**Forma de cálculo da métrica**: contam-se as ocorrências de "eu", "tu", "você" e "vocês" e divide-se o resultado pelo total de pronomes pessoais do texto.

**Recursos de PLN utilizados durante o cálculo**: POS tagger do nlpnet

**Limitações da métrica**: 

**Crítica**: a rigor, a métrica deveria computar primeiras e segundas pessoas: eu, tu, você, a gente, vocês, nós e vós. Está faltando computar “a gente” e “vós”.

**Projeto**: GUTEN

**Teste**: Você acredita que já chegou o final do ano? O tempo voou e a gente já começa a ver o Papai Noel nos outdoors e nas vitrines. Mas eu acho que o comércio está se antecipando demais e deveria esperar dezembro para começar as propagandas de Natal.

**Contagens**: 3 pronomes pessoais que indicam diálogo com o leitor (você, a gente, eu)

**Resultado Esperado**: 3/3 = 1,00

**Resultado Obtido**: 1,00 (2/2) (como não reconhece “a gente”, não computa no numerador nem no denominador

**Status**: correto




## Proporção de palavras de conteúdo em relação à quantidade de palavras funcionais do texto



**Nome da Métrica**: content density

**Interpretação**: não está clara a relação entre a métrica e a complexidade textual

**Descrição da métrica**: Proporção média de palavras de conteúdo em relação à quantidade de palavras funcionais das sentenças

**Definição dos termos que aparecem na descrição da métrica**: Palavras de conteúdo são palavras de classe aberta (substantivos, adjetivos, verbos e advérbios). Palavras funcionais são palavras das classes fechadas (numerais, artigos, pronomes, interjeições, preposições, conjunções)

**Forma de cálculo da métrica**: somam-se as ocorrências de palavras de conteúdo de cada sentença e divide-se o resultado pela quantidade de palavras funcionais da respectiva sentença. Depois somam-se as proporções de todas as sentenças e divide-se pela quantidade de sentenças. 

**Recursos de PLN utilizados durante o cálculo**: POS tagger nlpnet

**Limitações da métrica**: a rigor, somente os advérbios terminados em –mente são palavras de conteúdo. Mas como as etiquetas não fazem essa diferença, estão sendo computados todos os advérbios. O resultado da métrica é dependente da forma de tokenização adotada (com ou sem descontração, com ou sem junção de partes de nomes próprios e multipalavras).

**Crítica**: 

A métrica faz a tokenização sem considerar descontrações. A descontração é importante para o cômputo de palavras funcionais. Se houver descontração, cada parte da contração é contada em uma categoria; porém, se não houver, uma das categorias gramaticais envolvidas ficará prejudicada.

**Projeto**: GUTEN

**Teste**: Atenção! Nós não podemos acrescentar nenhuma despesa a mais no nosso orçamento. Já não temos recursos suficientes para a manutenção das quatro escolas, por exemplo, e também precisamos valorizar o magistério - justifica a diretora do Departamento Pedagógico da SEC, Sonia Balzano.

**Contagens**: 

28 Palavras de conteúdo: [('Atenção', 'N'), ('não', 'ADV'), ('podemos', 'V'), ('acrescentar', 'V'), ('despesa', 'N'), ('a', 'ADV'), ('mais', 'ADV'), ('orçamento', 'N'), ('Já', 'ADV'), ('não', 'ADV'), ('temos', 'V'), ('recursos', 'N'), ('suficientes', 'ADJ'), ('manutenção', 'N'), ('escolas', 'N'), ('por', 'PDEN'), ('exemplo', 'PDEN'), ('também', 'PDEN'), ('precisamos', 'V'), ('valorizar', 'V'), ('magistério', 'N'), ('justifica', 'V'), ('diretora', 'N'), ('Departamento', 'N'), ('Pedagógico', 'ADJ'), ('SEC', 'NPROP'), ('Sonia', 'NPROP'), ('Balzano', 'NPROP')]

13 Palavras funcionais: [('Nós', 'PROPESS'), ('nenhuma', 'PROADJ'), ('no', 'PREP+ART'), ('nosso', 'PROADJ'), ('para', 'PREP'), ('a', 'ART'), ('das', 'PREP+ART'), ('quatro', 'NUM'), ('e', 'KC'), ('o', 'ART'), ('a', 'ART'), ('do', 'PREP+ART'), ('da', 'PREP+ART')]

**Resultado Esperado**: 28/13 = 2,15

**Resultado Obtido**: 2,15

**Status**: correto




## Proporção de types (despreza repetições de palavras) em relação à quantidade de tokens (computa repetições de palavras) no texto



**Nome da Métrica**: ttr

**Interpretação**: quanto maior o valor da métrica, mais complexo o texto

**Descrição da métrica**: Proporção de palavras sem repetições (types) em relação ao total de palavras com repetições (tokens). Não se usa lematização das palavras, ou seja, cada flexão é computada como um type diferente.

**Definição dos termos que aparecem na descrição da métrica**: Types são as palavras que ocorrem em um texto, descontando suas repetições. Tokens são todas as palavras que ocorrem em um texto, sem descontar as repetições. 

**Forma de cálculo da métrica**: contam-se todos os types e divide-se pela quantidade de tokens.

**Recursos de PLN utilizados durante o cálculo**: tokenizador nltk

**Limitações da métrica**: 

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 95 palavras, 58 das quais palavras de conteúdo, 57 types (só repete a palavra “senador”). 

**Resultado Esperado**: 78/95=0,821

**Resultado Obtido**: 0,821 (está computando todos os tokens e não só palavras de conteúdo)

**Status**: correto




## Proporção de sentidos dos verbos do texto em relação à  quantidade de verbos do texto



**Nome da Métrica**: verbs_ambiguity

**Interpretação**: não está clara a relação da métrica com a complexidade. Os verbos mais frequentes são os que possuem mais sentidos. Os verbos mais frequentes também são os primeiros a serem adquiridos e, portanto, os mais simples. Porém, nem todos os sentidos dos verbos polissêmicos são aprendidos de uma só vez. 

**Descrição da métrica**: proporção entre a quantidade de sentidos que os verbos do texto possuem no TEP e a quantidade de verbos do texto. Quanto mais sentidos tem um verbo, maior sua ambiguidade. 

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: Identificam-se os verbos e usa-se um lematizador para descobri o lema deles. Busca-se a quantidade de sentidos que o lema de cada verbo apresenta no TEP, Thesaurus Eletrônico do Português (http://www.nilc.icmc.usp.br/tep2/). Somam-se as quantidades de sentidos de todos os verbos e divide-se o total pelo número de verbos do texto.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, TEP Thesaurus Eletrônico do Português

**Limitações da métrica**: se o POS tagger ou o lematizador falharem em identificar o verbo, fica impossível buscar o número de sentidos no TEP.

**Crítica**: teoricamente, a ambiguidade é um fator que aumenta a complexidade. Utilizar a quantidade de sentidos da palavra para medir ambiguidade, porém, pode não resultar em uma boa métrica, pois as palavras mais raras (e mais complexas) são as que possuem menos sentidos. Por exemplo, o verbo “ser” tem 12 sentidos no TEP e, por isso, contribui para a obtenção de uma alta proporção de ambiguidade. Não se pode inferir, contudo, que a ocorrência do verbo “ser” aumente a complexidade do texto.

**Projeto**: Coh-Metrix-Port

**Teste**: O menino colou na prova, embora soubesse que poderia ser pego.

**Contagens**: 5 verbos (colar, saber, poder, ser, pegar) com 4, 7, 2, 12, 17 sentidos, respectivamente, no TEP.

**Resultado Esperado**: 8,4 (42/5)

**Resultado Obtido**: 6,25 (o verbo “pegar” não foi identificado)

**Status**:  correto, dependendo da corretude do PoS tagger e lematizador.




## Proporção de sentidos dos adjetivos do texto em relação à quantidade de adjetivos do texto




**Nome da Métrica**: adjectives_ambiguity

**Interpretação**: não está clara a relação da métrica com a complexidade.

**Descrição da métrica**: Ambiguidade de Adjetivos

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: Para cada adjetivo do texto soma-se o número de sentidos que ele apresenta no TEP (Maziero et. al., 2008) e divide-se o total pelo número de adjetivos do texto.

**Recursos de PLN utilizados durante o cálculo**: TEP Thesaurus Eletrônico do Português

**Limitações da métrica**: há palavras que não estão no TEP e isso compromete a confiabilidade da métrica

**Crítica**: teoricamente, a ambiguidade é um fator que aumenta a complexidade. Utilizar a quantidade de sentidos da palavra para medir ambiguidade, porém, pode não resultar em uma boa métrica, pois as palavras mais raras (e mais complexas) são as que possuem menos sentidos.

**Projeto**: Coh-Metrix-Port

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 6 adjetivos (polêmico, municipal, estadual, federal, solar, anual). Apenas o adjetivo “anual” consta do TEP, com 1 sentido

**Resultado Esperado**: 1/6

**Resultado Obtido**: 0,166

**Status**: correto




## Índice Flesch




**Nome da Métrica**: flesch

**Interpretação**: Índice de leiturabilidade de Flesch

**Descrição da métrica**: O Índice de Legibilidade de Flesch busca uma correlação entre tamanhos médios de palavras e sentenças 

**Definição dos termos que aparecem na descrição da métrica**: 

**Forma de cálculo da métrica**: 248.835 - [1.015 x (média de palavras por sentença)] - [84.6 x (Número de sílabas do texto / Número de palavras do texto)]

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Port

**Teste**: Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 3 sentenças, 69 palavras, 160 sílabas. Médias: 23 palavras por sentença; 2,31 sílabas por palavra. 

**Resultado Esperado**: 248,835 – [1,015 x (23)] – [84,6 x (2,31)] => 248,835 – [23,345 – 195,43] = 29,316

**Resultado Obtido**: 29,316

**Status**: correto




## Índice de Brunet




**Nome da Métrica**: brunet

**Interpretação**: Os valores típicos da métrica variam entre 10 e 20, sendo que uma fala mais rica produz valores menores (THOMAS et al., 2005).

**Descrição da métrica**: Estatística de Brunet é uma forma de type/token ratio que é menos sensível ao tamanho do texto. 

**Definição dos termos que aparecem na descrição da métrica**: quantidade de types considera palavras sem repetições e quantidade de tokens considera palavras com repetições.

**Forma de cálculo da métrica**: W = N ** (V ** −0.165) quantidade de types elevada à quantidade de tokens elevada à constante -0,165.

**Recursos de PLN utilizados durante o cálculo**: 

**Limitações da métrica**:  

**Crítica**: 

**Projeto**: Coh-Metrix-Dementia

**Teste**: O acessório polêmico entrou no projeto, de autoria do senador Cícero Lucena (PSDB-PB), graças a uma emenda aprovada na Comissão de Educação do Senado em outubro. Foi o senador Flávio Arns (PT-PR) quem sugeriu a inclusão da peça entre os itens do uniforme de alunos dos ensinos Fundamental e Médio nas escolas municipais, estaduais e federais. Ele defende a medida como forma de proteger crianças e adolescentes dos males provocados pelo excesso de exposição aos raios solares. Se a ideia for aprovada, os estudantes receberão dois conjuntos anuais, completados por calçado, meias, calça e camiseta.

**Contagens**: 95 tokens e 78 types

**Resultado Esperado**: 9,199

**Resultado Obtido**: 9,199

**Status**: correto




## Proporção de sentidos dos substantivos do texto em relação à  quantidade de substantivos do texto



**Nome da Métrica**: nouns_ambiguity

**Interpretação**: não está clara a relação da métrica com a complexidade.

**Descrição da métrica**: proporção de sentidos dos substantivos em relação à quantidade de substantivos 

**Definição dos termos que aparecem na descrição da métrica**: quantidade de sentidos é a soma de todos os sentidos de cada palavra no TEP Thesaurus Eletrônico do Português

**Forma de cálculo da métrica**: Para cada substantivo do texto soma-se o número de sentidos que ele apresenta no TEP (Maziero et. al., 2008) e divide-se o total pelo número de substantivos do texto.

**Recursos de PLN utilizados durante o cálculo**: TEP Thesaurus Eletrônico do Português

**Limitações da métrica**:  

**Crítica**: teoricamente, a ambiguidade é um fator que aumenta a complexidade. Utilizar a quantidade de sentidos da palavra para medir ambiguidade, porém, pode não resultar em uma boa métrica, pois as palavras mais raras (e mais complexas) são as que possuem menos sentidos.

**Projeto**: Coh-Metrix-Port

**Teste**: O menino colou na prova, embora soubesse que poderia ser pego.

**Contagens**: 2 substantivos: menino e prova, com 1 e 9 sentidos no TEP, respectivamente.

**Resultado Esperado**: 10/2 = 5

**Resultado Obtido**: 5

**Status**: correto




## Proporção de Nomes Próprios em relação à quantidade de palavras do Texto




**Nome da Métrica**: named_entity_ratio_text

**Interpretação**: não está clara a relação da métrica com a complexidade textual

**Descrição da métrica**: Proporção de Nomes Próprios em relação à quantidade de palavras do Texto

**Definição dos termos que aparecem na descrição da métrica**: nomes próprios são palavras escritas em letra maiúscula, compostos de um ou mais tokens, capturadas por meio da etiqueta morfossintática PROP do parser Palavras. A etiqueta PROP junta todos os tokens de um mesmo nome próprio em uma multipalavra.

**Forma de cálculo da métrica**: contam-se todas as ocorrências da etiqueta PROP e divide-se o resultado pela quantidade de palavras do texto.

**Recursos de PLN utilizados durante o cálculo**: parser Palavras

**Limitações da métrica**: é importante para essa métrica usar a opção de junção de palavras que compõem os nomes próprios, disponível no parser Palavras; caso contrário, corre-se o risco de contar cada token do nome próprio como uma entidade nomeada diferente.  

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O melhor amigo do João é o Jorge Campos, que trabalha na Siemens. Eles se conheceram no Palestra Itália, num dia de decisão entre Palmeiras e São Paulo.

**Contagens**: 28 palavras, 6 nomes próprios: João, Jorge Campos, Siemens, Palestra Itália, Palmeiras, São Paulo

**Resultado Esperado**: 6/29 = 0,207

**Resultado Obtido**: 0,207

**Status**: correto




## Proporção de palavras com valor de idade de aquisição entre 1 e 2,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: idade_aquisicao_1_25_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa, menor a complexidade textual

**Descrição da métrica**: Proporção de palavras de conteúdo do texto com idade de aquisição entre 1 e 2,5 em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Idade de aquisição é uma característica psicolinguística das palavras de conteúdo e representa o intervalo de idade em que a palavra foi adquirida. Os valores variam de 1 a 7 e quanto menor o valor, menor a idade de aquisição. Os valores correspondem a faixas de idade. 1 (de 0 a 2 anos); 2 (de 3 a 4 anos), 3 (de 5 a 6 anos), 4 (de 7 a 8 anos), 5 (de 9 a 10 anos), 6 (de 11 a 12 anos), 7 (13 anos ou mais).

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de idade de aquisição. Contam-se, separadamente, as palavras de conteúdo que tenham valor de idade de aquisição entre 1 e 2,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Segundo o chefe substituto do escritório regional, Guaracy Cunha, ainda há tempo para o pedido de licença.

**Contagens**: 

9 palavras de conteúdo e respectivas idades de aquisição (os 2 nomes próprios são palavras de conteúdo, mas não têm idade de aquisição, por serem nomes de pessoas): 

tempo (2,39), 
ainda (3,89), 
chefe (4,12), 
licença (4,57). 
há (5,10), 
pedido (5,26), 
escritório (5,35), 
substituto (6,00), 
regional (6,24), 

9 palavras de conteúdo identificadas e lematizadas: 'chefe', 'substituto', 'escritório', 'regional', 'ainda', 'haver', 'tempo', 'pedido', 'licença'

**Resultado Esperado**: 0,111 (1/9)

**Resultado Obtido**: 0,111

**Status**: correto




## Proporção de palavras com valor de idade de aquisição entre 2,5  e 4 em relação a todas as palavras de conteúdo do texto 



**Nome da Métrica**: idade_aquisicao_25_4_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa e na inferior, menor a complexidade textual

**Descrição da métrica**: Proporção de palavras de conteúdo do texto com valores de idade de aquisição entre 2,5 e 4, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Idade de aquisição é uma característica psicolinguística das palavras de conteúdo e representa o intervalo de idade em que a palavra foi adquirida. Os valores variam de 1 a 7 e quanto menor o valor, menor a idade de aquisição. Os valores correspondem a faixas de idade. 1 (de 0 a 2 anos); 2 (de 3 a 4 anos), 3 (de 5 a 6 anos), 4 (de 7 a 8 anos), 5 (de 9 a 10 anos), 6 (de 11 a 12 anos), 7 (13 anos ou mais).

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de idade de aquisição. Contam-se, separadamente, as palavras de conteúdo que tenham valor de idade de aquisição entre 2,5 e 4. Depois divide-se o resultado pela quantidade total de palavras de conteúdo presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Segundo o chefe substituto do escritório regional, Guaracy Cunha, ainda há tempo para o pedido de licença.

**Contagens**: 

9 palavras de conteúdo e respectivas idades de aquisição (os 2 nomes próprios são palavras de conteúdo, mas não têm idade de aquisição, por serem nomes de pessoas): 

tempo (2,39),
ainda (3,89), 
chefe (4,12), 
licença (4,57). 
há (5,10), 
pedido (5,26), 
escritório (5,35), 
substituto (6,00), 
regional (6,24), 

9 palavras de conteúdo identificadas e lematizadas: 'chefe', 'substituto', 'escritório', 'regional', 'ainda', 'haver', 'tempo', 'pedido', 'licença'

1 palavra no intervalo entre 2,5 e 4,0 (ainda)

**Resultado Esperado**: 0,111 (1/9)

**Resultado Obtido**: 0,111

**Status**: correto




## Proporção de palavras com valor de idade de aquisição entre 4 e 5,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: idade_aquisicao_4_55_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa e na superior, maior a complexidade textual.

**Descrição da métrica**: proporção de palavras com valor de idade de aquisição entre 4 e 5,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Idade de aquisição é uma característica psicolinguística das palavras de conteúdo e representa o intervalo de idade em que a palavra foi adquirida. Os valores variam de 1 a 7 e quanto menor o valor, menor a idade de aquisição. Os valores correspondem a faixas de idade. 1 (de 0 a 2 anos); 2 (de 3 a 4 anos), 3 (de 5 a 6 anos), 4 (de 7 a 8 anos), 5 (de 9 a 10 anos), 6 (de 11 a 12 anos), 7 (13 anos ou mais).

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de idade de aquisição. Contam-se, separadamente, as palavras de conteúdo que tenham valor de idade de aquisição entre 4 e 5,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Segundo o chefe substituto do escritório regional, Guaracy Cunha, ainda há tempo para o pedido de licença.

**Contagens**: 

9 palavras de conteúdo e respectivas idades de aquisição (os 2 nomes próprios são palavras de conteúdo, mas não têm idade de aquisição, por serem nomes de pessoas): 

tempo (2,39), 
ainda (3,89), 
chefe (4,12), 
licença (4,57). 
há (5,10), 
pedido (5,26), 
escritório (5,35),
substituto (6,00), 
regional (6,24), 

9 palavras de conteúdo identificadas e lematizadas: 'chefe', 'substituto', 'escritório', 'regional', 'ainda', 'haver', 'tempo', 'pedido', 'licença'

5 palavras no intervalo de 4,00 a 5,50

**Resultado Esperado**: 0,556 (5/9)

**Resultado Obtido**: 0,556

**Status**: correto




## Proporção de palavras com valor de idade de aquisição entre 5,5 e 7  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: idade_aquisicao_55_7_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa, maior a complexidade textual Descrição da métrica: proporção de palavras com valor de idade de aquisição entre 5,5 e 7, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Idade de aquisição é uma característica psicolinguística das palavras de conteúdo e representa o intervalo de idade em que a palavra foi adquirida. Os valores variam de 1 a 7 e quanto menor o valor, menor a idade de aquisição. Os valores correspondem a faixas de idade. 1 (de 0 a 2 anos); 2 (de 3 a 4 anos), 3 (de 5 a 6 anos), 4 (de 7 a 8 anos), 5 (de 9 a 10 anos), 6 (de 11 a 12 anos), 7 (13 anos ou mais).

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de idade de aquisição. Contam-se, separadamente, as palavras de conteúdo que tenham valor de idade de aquisição entre 5,5 e 7. Depois divide-se o resultado pela quantidade total de palavras de conteúdo presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Segundo o chefe substituto do escritório regional, Guaracy Cunha, ainda há tempo para o pedido de licença.

**Contagens**: 

9 palavras de conteúdo e respectivas idades de aquisição (os 2 nomes próprios são palavras de conteúdo, mas não têm idade de aquisição, por serem nomes de pessoas): 

tempo (2,39), 
ainda (3,89), 
chefe (4,12), 
licença (4,57). 
há (5,10), 
pedido (5,26), 
escritório (5,35), 
substituto (6,00), 
regional (6,24), 

9 palavras de conteúdo identificadas e lematizadas: 'chefe', 'substituto', 'escritório', 'regional', 'ainda', 'haver', 'tempo', 'pedido', 'licença'

2 palavras no intervalo de 5,5 e 7 de idade de aquisição (substituto e regional)

**Resultado Esperado**: 0,222 (2/9)

**Resultado Obtido**: 0,222

**Status**: correto




## Proporção de palavras com valor de familiaridade entre 1 e 2,5  em relação a todas as palavras de conteúdo do texto 



**Nome da Métrica**: familiaridade_1_25_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa, maior a complexidade textual

**Descrição da métrica**: Proporção de palavras de conteúdo com valores de familiaridade entre 1 a 2,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Familiaridade é uma característica psicolinguística das palavras de conteúdo e representa o quanto os falantes da língua conhecem e usam uma palavra em suas vidas cotidianas. Os valores variam de 1 a 7 e quanto maior o valor, maior a familiaridade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de familiaridade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de familiaridade entre 1 e 2,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Desde que a canonização foi confirmada pelo Vaticano, o movimento no Mosteiro da Luz tem aumentado -- e o interesse da imprensa também.

**Contagens**: 

12 palavras de conteúdo, com os seguintes valores de familiaridade: 

Canonização 2,48; Mosteiro 3,04; Vaticano 3,45; Confirmada 4,38; Movimento 4,84; Luz 5,57; Aumentar 4,89; Imprensa 4,90; Interesse 5,31; Também 5,44; Ser 5,50; Ter 5,81

9 palavras de conteúdo reconhecidas e lematizadas pelo programa: ['canonização', 'ir', 'confirmado', 'movimento', 'ter', 'aumentado', 'interesse', 'imprensa', 'também'] O programa não reconheceu os Nomes Próprios (Vaticano, Mosteiro, Luz) como palavras de conteúdo. O verbo “foi” (que é uma forma ambígua) foi lematizado incorretamente para “ir” e não para “ser”.

7 palavras encontradas no repositório psicolinguístico (os particípios “confirmado” e “aumentado” foram lematizado como adjetivos e por isso não foram encontrados no repositório; eles só seriam encontrados se fossem lematizados como verbos: confirmar” e “aumentar”). 

1 palavra com familiaridade de 1 a 2,5 (canonização)

**Resultado Esperado**: 0,083 (1/12)

**Resultado Obtido**: 0,143 (1/7)

**Status**: correto, considerando as limitações do tagger e da estratégia de lematização




## Proporção de palavras com valor de familiaridade entre 2,5  e 4 em relação a todas as palavras de conteúdo do texto 



**Nome da Métrica**: familiaridade_25_4_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa e na inferior, maior a complexidade textual

**Descrição da métrica**: Proporção de palavras de conteúdo com familiaridade entre 2,5 e 4, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Familiaridade é uma característica psicolinguística das palavras de conteúdo e significa o quanto a palavra pode ser traduzida por uma imagem na opinião dos falantes da língua. Os valores variam de 1 a 7 e quanto maior o valor, maior a familiaridade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de familiaridade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de familiaridade entre 2,5 e 4. Depois divide-se o resultado pela quantidade total de palavras de conteúdodo texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Desde que a canonização foi confirmada pelo Vaticano, o movimento no Mosteiro da Luz tem aumentado -- e o interesse da imprensa também.

**Contagens**: 

12 palavras de conteúdo, com os seguintes valores de familiaridade: 

Canonização 2,48; Mosteiro 3,04; Vaticano 3,45; Confirmada 4,38; Movimento 4,84; Luz  5,57; Aumentar 4,89; Imprensa 4,90; Interesse 5,31; Também 5,44; Ser 5,50; Ter 5,81

9 palavras de conteúdo reconhecidas e lematizadas pelo programa: ['canonização', 'ir', 'confirmado', 'movimento', 'ter', 'aumentado', 'interesse', 'imprensa', 'também'] O programa não reconheceu os Nomes Próprios (Vaticano, Mosteiro, Luz) como palavras de conteúdo. O verbo “foi” (que é uma forma ambígua) foi lematizado incorretamente para “ir” e não para “ser”.

7 palavras encontradas no repositório psicolinguístico (os particípios “confirmado” e “aumentado” foram lematizado como adjetivos e por isso não foram encontrados no repositório; eles só seriam encontrados se fossem lematizados como verbos: confirmar” e “aumentar”). 

2 palavras com familiaridade de 2,5 a 4,0: 2 (mosteiro, vaticano)

**Resultado Esperado**: 0,167 (2/12)

**Resultado Obtido**: 0,0

**Status**: correto, considerando as limitações do tagger e da estratégia de lematização




## Proporção de palavras com valor de familiaridade entre 4 e 5,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: familiaridade_4_55_ratio

**Interpretação**: quanto maior a proporção de palavras nessa faixa e na superior, menor a complexidade textual.

**Descrição da métrica**: proporção de palavras com valor de familiaridade entre 4 a 5,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Familiaridade é uma característica psicolinguística das palavras de conteúdo e representa o quanto os falantes da língua conhecem e usam uma palavra em suas vidas cotidianas. Os valores variam de 1 a 7 e quanto maior o valor, maior a familiaridade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de familiaridade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de familiaridade entre 4 e 5,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Desde que a canonização foi confirmada pelo Vaticano, o movimento no Mosteiro da Luz tem aumentado -- e o interesse da imprensa também.

**Contagens**: 

12 palavras de conteúdo, com os seguintes valores de familiaridade: 

Canonização 2,48; Mosteiro 3,04; Vaticano 3,45; Confirmada 4,38; Movimento 4,84; Luz 5,57; Aumentar 4,89; Imprensa 4,90; Interesse 5,31; Também 5,44; Ser 5,50; Ter 5,81

9 palavras de conteúdo reconhecidas e lematizadas pelo programa: ['canonização', 'ir', 'confirmado', 'movimento', 'ter', 'aumentado', 'interesse', 'imprensa', 'também']

O programa não reconheceu os Nomes Próprios (Vaticano, Mosteiro, Luz) como palavras de conteúdo. O verbo “foi” (que é uma forma ambígua) foi lematizado incorretamente para “ir” e não para “ser”.

7 palavras encontradas no repositório psicolinguístico (os particípios “confirmado” e “aumentado” foram lematizado como adjetivos e por isso não foram encontrados no repositório; eles só seriam encontrados se fossem lematizados como verbos: confirmar” e “aumentar”). 

6 palavras com familiaridade de 4,0 a 5,5 (confirmar, movimento, aumentar, interesse, imprensa, também) 

**Resultado esperado**: 0,50 (6/12)

**Resultado obtido**: 0,5710 (4/7)

**Status**: correto, considerando as limitações do tagger e da estratégia de lematização




## Proporção de palavras com valor de familiaridade entre 5,5 e 7  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: familiaridade_55_7_ratio

**Interpretação**: quanto maior for o resultado, maior é a familiaridade e menor a complexidade textual

**Descrição da métrica**: proporção de palavras com valor de familiaridade entre 5,5 e 7, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Familiaridade é uma característica psicolinguística das palavras de conteúdo e representa o quanto os falantes da língua conhecem e usam uma palavra em suas vidas cotidianas. Os valores variam de 1 a 7 e quanto maior o valor, maior a familiaridade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de familiaridade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de familiaridade entre 5,5 e 7. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Desde que a canonização foi confirmada pelo Vaticano, o movimento no Mosteiro da Luz tem aumentado -- e o interesse da imprensa também.

**Contagens**: 

12 palavras de conteúdo, com os seguintes valores de familiaridade: 

Canonização 2,48; Mosteiro 3,04; Vaticano 3,45; Confirmada 4,38; Movimento 4,84; Luz  5,57; Aumentar 4,89; Imprensa 4,90; Interesse 5,31; Também 5,44; Ser 5,50; Ter 5,81

9 palavras de conteúdo reconhecidas e lematizadas pelo programa: ['canonização', 'ir', 'confirmado', 'movimento', 'ter', 'aumentado', 'interesse', 'imprensa', 'também'] O programa não reconheceu os Nomes Próprios (Vaticano, Mosteiro, Luz) como palavras de conteúdo. O verbo “foi” (que é uma forma ambígua) foi lematizado incorretamente para “ir” e não para “ser”.

7 palavras encontradas no repositório psicolinguístico (os particípios “confirmado” e “aumentado” foram lematizado como adjetivos e por isso não foram encontrados no repositório; eles só seriam encontrados se fossem lematizados como verbos: confirmar” e “aumentar”). 

3 palavras com familiaridade de 5,5 a 7,00 (ser, luz, ter) 

**Resultado esperado**: 0,25 (3/12)

**Resultado Obtido**: 0,286 (2/7)

**Status**: correto, considerando as limitações do tagger e da estratégia de lematização




## Proporção de palavras com valor de imageabilidade entre 1 e 2,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: imageabilidade_1_25_ratio

**Interpretação**: quanto maior o valor de imageabilidade, menor a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa, maior a complexidade.

**Descrição da métrica**: Proporção de palavras de conteúdo do texto com imageabilidade entre 1 e 2,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Imageabilidade é uma característica psicolinguística das palavras de conteúdo e significa o quanto a palavra pode ser traduzida por uma imagem na opinião dos falantes da língua. Os valores variam de 1 a 7 e quanto maior o valor, maior a imageabilidade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de imageabilidade. Contam-se, separadamente, as palavras de conteúdo do texto que tenham valor de imageabilidade entre 1 e 2,5.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Pescadores tentarão retirar o maior número de peixes da espécie, que pode atingir 20 centímetros de comprimento e um quilo.

**Contagens**:

12 palavras  de conteúdo, com seus respectivos valores de imageabilidade:

maior 3.48
número 4.15
tentar 4.18
atingir 4.21
retirar 4.24
comprimento 4.64
centímetro 4.77
espécie 4.87
podar 4.89
quilo 5.32 
pescador 5.55
peixe 6.00

12 palavras reconhecidas (com suas respectivas etiquetas morfossintáticas): 'Pescadores', 'NPROP'; 'tentarão', 'V'; 'retirar', 'V'; 'maior', 'ADJ'; 'número', 'N'; 'peixes', 'N'; 'espécie', 'N'; 'pode', 'V'; 'atingir', 'V'; 'centímetros', 'N'; 'comprimento', 'N'; 'quilo', 'N'.

11 palavras lematizadas: ['tentar', 'retirar', 'maior', 'número', 'peixe', 'espécie', 'podar', 'atingir', 'centímetro', 'comprimento', 'quilo']. 

A palavra “Pescador” foi anotada como NPROP e por isso não foi lematizada.

11 palavras encontradas no repositório psicolinguístico (todas, menos “Pescadores”)

nenhuma palavra com imageabilidade entre 1 e 2,5

**Resultado Esperado**: 0

**Resultado Obtido**: 0

**Status**: correto




## Proporção de palavras com valor de imageabilidade entre 2,5  e 4 em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: imageabilidade_25_4_ratio

**Interpretação**: quanto maior o valor de imageabilidade, menor a complexidade textual. Portanto, quanto maior o percentual de palavras nessa faixa e na inferior, maior a complexidade.

**Descrição da métrica**: Proporção de palavras de conteúdo do texto com imageabilidade entre 2,5 e 4, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. Imageabilidade é uma característica psicolinguística das palavras de conteúdo e significa o quanto a palavra pode ser traduzida por uma imagem na opinião dos falantes da língua. Os valores variam de 1 a 7 e quanto maior o valor, maior a imageabilidade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de imageabilidade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de imageabilidade entre 2,5 e 4. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos.

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Pescadores tentarão retirar o maior número de peixes da espécie, que pode atingir 20 centímetros de comprimento e um quilo.

**Contagens**:

12 palavras  de conteúdo, com seus respectivos valores de imageabilidade:

maior 3.48
número 4.15
tentar 4.18
atingir 4.21
retirar 4.24
comprimento 4.64
centímetro 4.77
espécie 4.87
podar 4.89
quilo 5.32 
pescador 5.55
peixe 6.00

12 palavras reconhecidas (com suas respectivas etiquetas morfossintáticas): 'Pescadores', 'NPROP'; 'tentarão', 'V'; 'retirar', 'V'; 'maior', 'ADJ'; 'número', 'N'; 'peixes', 'N'; 'espécie', 'N'; 'pode', 'V'; 'atingir', 'V'; 'centímetros', 'N'; 'comprimento', 'N'; 'quilo', 'N'.

11 palavras lematizadas: ['tentar', 'retirar', 'maior', 'número', 'peixe', 'espécie', 'podar', 'atingir', 'centímetro', 'comprimento', 'quilo']. 

A palavra “Pescador” foi anotada como NPROP e não foi lematizada)

11 palavras encontradas no repositório psicolinguístico

1 palavra com imageabilidade entre 2,5 e 4.0 (maior)

**Resultado Esperado**: 0,083 (1/12)

**Resultado Obtido**: 0, 091 (1/11)

**Status**: correto, considerando as limitações do tagger




## Proporção de palavras com valor de imageabilidade entre 4 e 5,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: imageabilidade_4_55_ratio

**Interpretação**: quanto maior o valor de imageabilidade, menor a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa e na superior, menor a complexidade textual.

**Descrição da métrica**: proporção de palavras com valor de imageabilidade entre 4 e 5,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Imageabilidade é uma característica psicolinguística das palavras de conteúdo e significa o quanto a palavra pode ser traduzida por uma imagem na opinião dos falantes da língua. Os valores variam de 1 a 7 e quanto maior o valor, maior a imageabilidade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de imageabilidade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de imageabilidade entre 4 e 5,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico 

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. Ele foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade levantados, junto a usuários da língua por psicolinguistas e psicólogos. 

**Projeto**: GUTEN

**Teste**: Pescadores tentarão retirar o maior número de peixes da espécie, que pode atingir 20 centímetros de comprimento e um quilo.

**Contagens**:

12 palavras  de conteúdo, com seus respectivos valores de imageabilidade:

maior 3.48
número 4.15
tentar 4.18
atingir 4.21
retirar 4.24
comprimento 4.64
centímetro 4.77
espécie 4.87
podar 4.89
quilo 5.32 
pescador 5.55
peixe 6.00

12 palavras reconhecidas (com suas respectivas etiquetas morfossintáticas): 'Pescadores', 'NPROP'; 'tentarão', 'V'; 'retirar', 'V'; 'maior', 'ADJ'; 'número', 'N'; 'peixes', 'N'; 'espécie', 'N'; 'pode', 'V'; 'atingir', 'V'; 'centímetros', 'N'; 'comprimento', 'N'; 'quilo', 'N'.

11 palavras lematizadas: ['tentar', 'retirar', 'maior', 'número', 'peixe', 'espécie', 'podar', 'atingir', 'centímetro', 'comprimento', 'quilo']. A palavra “Pescador” foi anotada como NPROP e não foi lematizada)

11 palavras encontradas no repositório psicolinguístico

**Resultado Esperado**: 0,818 (9/12)

**Resultado Obtido**: 0,9 (9/11)

**Status**: correto, considerando a limitação do tagger



## Proporção de palavras com valor de imageabilidade entre 5,5 e 7  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: imageabilidade_55_7_ratio

**Interpretação**: quanto maior o valor de imageabilidade, menor a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa, menor a complexidade.

**Descrição da métrica**: proporção de palavras com alto valor de imageabilidade (5,5 a 7) em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Imageabilidade é uma característica psicolinguística das palavras de conteúdo e significa o quanto a palavra pode ser traduzida por uma imagem na opinião dos falantes da língua. Os valores variam de 1 a 7 e quanto maior o valor, maior a imageabilidade.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de imageabilidade. Contam-se, separadamente, as palavras de conteúdo que tenham valor de imageabilidade entre 5,5 e 7. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico 

**Limitações da métrica**: depende do desempenho do nlpnet. O repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. Ele foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: Pescadores tentarão retirar o maior número de peixes da espécie, que pode atingir 20 centímetros de comprimento e um quilo.

**Contagens**:

12 palavras  de conteúdo, com seus respectivos valores de imageabilidade:

maior 3.48
número 4.15
tentar 4.18
atingir 4.21
retirar 4.24
comprimento 4.64
centímetro 4.77
espécie 4.87
podar 4.89
quilo 5.32 
pescador 5.55
peixe 6.00

12 palavras reconhecidas (com suas respectivas etiquetas morfossintáticas): 'Pescadores', 'NPROP'; 'tentarão', 'V'; 'retirar', 'V'; 'maior', 'ADJ'; 'número', 'N'; 'peixes', 'N'; 'espécie', 'N'; 'pode', 'V'; 'atingir', 'V'; 'centímetros', 'N'; 'comprimento', 'N'; 'quilo', 'N'.

11 palavras lematizadas: ['tentar', 'retirar', 'maior', 'número', 'peixe', 'espécie', 'podar', 'atingir', 'centímetro', 'comprimento', 'quilo']. A palavra “Pescador” foi anotada como NPROP e não foi lematizada)

11 palavras encontradas no repositório psicolinguístico, 2 entre 5,5 e 7,00

**Resultado Esperado**: 0,167, (2/12)

**Resultado Obtido**: 0,091, (1/11)

**Status**: correto, considerando a limitação do tagger




## Proporção de palavras com valor de concretude entre 1 e 2,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: concretude_1_25_ratio

**Interpretação**: quanto menor a concretude, maior a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa, maior a complexidade.

**Descrição da métrica**: proporção de palavras com valor de concretude entre 1 a 2,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Os valores de concretude variam de 1 a 7 e quanto maior o valor, mais alta a concretude. Palavras com alto valor de concretude são palavras concretas e palavras com baixo valor de concretude são palavras abstratas.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de concretude no repositório. Contam-se, separadamente, as palavras de conteúdo que tenham valor de concretude entre 1 e 2,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: o repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O aumento de casos frustrou expectativas e fez as autoridades reverem estratégias.

**Contagens**: 

8 palavras de conteúdo, com seus respectivos valores de concretude:

frustrar 2.50
expectativa 2.82
rever 3.09
aumento 3.35
caso 3.95
autoridade 3.50
estratégia 3.86
fazer 3.88

8 palavras de conteúdo identificadas: ('aumento', 'N'), ('casos', 'N'), ('frustrou', 'V'), ('expectativas', 'N'), ('fez', 'V'), ('autoridades', 'N'), ('reverem', 'V'), ('estratégias', 'N')

8 palavras lematizadas: ['aumento', 'caso', 'frustrar', 'expectativa', 'fazer', 'autoridade', 'rever', 'estratégia']

**Resultado Esperado**: 0,125 (1/8)

**Resultado Obtido**: 0,125

**Status**: correto




## Proporção de palavras com valor de concretude entre 2,5  e 4 em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: concretude_25_4_ratio

**Interpretação**: quanto menor a concretude, maior a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa e na inferior, maior a complexidade.

**Descrição da métrica**: proporção de palavras com valores de concretude entre 2,5 e 4, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Os valores de concretude variam de 1 a 7 e quanto maior o valor, mais alta a concretude. Palavras com alto valor de concretude são palavras concretas e palavras com baixo valor de concretude são palavras abstratas.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de concretude no repositório. Contam-se, separadamente, as palavras de conteúdo que tenham valor de concretude entre 2,5 e 4. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: o repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O aumento de casos frustrou expectativas e fez as autoridades reverem estratégias.

**Contagens**: 

8 palavras de conteúdo, com seus respectivos valores de concretude:

frustrar 2.50
expectativa 2.82
rever 3.09
aumento 3.35
caso 3.95
autoridade 3.50
estratégia 3.86
fazer 3.88

8 palavras de conteúdo identificadas: ('aumento', 'N'), ('casos', 'N'), ('frustrou', 'V'), ('expectativas', 'N'), ('fez', 'V'), ('autoridades', 'N'), ('reverem', 'V'), ('estratégias', 'N')

8 palavras lematizadas: ['aumento', 'caso', 'frustrar', 'expectativa', 'fazer', 'autoridade', 'rever', 'estratégia']

7 palavras no intervalo entre 2,5 e 4,00 de concretude

**Resultado Esperado**: 0,875 (9/8)

**Resultado Obtido**: 0,875 (9/8)

**Status**: correto




## Proporção de palavras com valor de concretude entre 4 e 5,5  em relação a todas as palavras de conteúdo do texto 




**Nome da Métrica**: concretude_4_55_ratio

**Interpretação**: quanto menor a concretude, maior a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa e na superior, menor a complexidade.

**Descrição da métrica**: proporção de palavras com valor de concretude de médio para entre 4 e 5,5, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Os valores de concretude variam de 1 a 7 e quanto maior o valor, mais alta a concretude. Palavras com alto valor de concretude são palavras concretas e palavras com baixo valor de concretude são palavras abstratas.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de concretude no repositório. Contam-se, separadamente, as palavras de conteúdo que tenham valor de concretude entre 4 e 5,5. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: o repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O aumento de casos frustrou expectativas e fez as autoridades reverem estratégias.

**Contagens**: 

8 palavras de conteúdo, com seus respectivos valores de concretude:

frustrar 2.50
expectativa 2.82
rever 3.09
aumento 3.35
caso 3.95
autoridade 3.50
estratégia 3.86
fazer 3.88

8 palavras de conteúdo identificadas: ('aumento', 'N'), ('casos', 'N'), ('frustrou', 'V'), ('expectativas', 'N'), ('fez', 'V'), ('autoridades', 'N'), ('reverem', 'V'), ('estratégias', 'N')

8 palavras lematizadas: ['aumento', 'caso', 'frustrar', 'expectativa', 'fazer', 'autoridade', 'rever', 'estratégia']

Nenhuma palavra no intervalo de 4,00 a 5,50 de concretude

**Resultado Esperado**: 0,0

**Resultado Obtido**: 0,0

**Status**: correto




## Proporção de palavras com valor de concretude entre 5,5 e 7  em relação a todas as palavras de conteúdo do texto 



**Nome da Métrica**: concretude_55_7_ratio

**Interpretação**: quanto menor a concretude, maior a complexidade textual. Portanto, quanto maior a proporção de palavras nessa faixa, menor a complexidade.

**Descrição da métrica**: proporção de palavras com valor de concretude entre 5,5 e 7, em relação a todas as palavras de conteúdo do texto presentes no repositório psicolinguístico

**Definição dos termos que aparecem na descrição da métrica**: são consideradas palavras de conteúdo: substantivos, verbos, adjetivos e advérbios. O repositório psicolinguístico é um recurso lexical com valores para 4 características psicolinguísticas das palavras: concretude, familiaridade, idade de aquisição e imageabilidade. Os valores de concretude variam de 1 a 7 e quanto maior o valor, mais alta a concretude. Palavras com alto valor de concretude são palavras concretas e palavras com baixo valor de concretude são palavras abstratas.

**Forma de cálculo da métrica**: Identificam-se as palavras de conteúdo do texto. Em seguida, lematizam-se essas palavras, usando o DELAF, e procuram-se seus respectivos valores de concretude no repositório. Contam-se, separadamente, as palavras de conteúdo que tenham valor de concretude entre 5,5 e 7. Depois divide-se o resultado pela quantidade total de palavras de conteúdo do texto presentes no repositório psicolinguístico.

**Recursos de PLN utilizados durante o cálculo**: nlpnet, DELAF e repositório psicolinguístico Limitações da métrica: o repositório psicolinguístico tem 26.874 palavras e pode não conter todas as palavras procuradas. O repositório psicolinguístico foi construído automaticamente (e por isso, sujeito a vieses), usando como semente listas de palavras com seus respectivos valores de concretude, familiaridade, idade de aquisição e imageabilidade, levantados junto a usuários da língua por psicolinguistas e psicólogos. 

**Crítica**: 

**Projeto**: GUTEN

**Teste**: O aumento de casos frustrou expectativas e fez as autoridades reverem estratégias.

**Contagens**: 

8 palavras de conteúdo, com seus respectivos valores de concretude:

frustrar 2.50
expectativa 2.82
rever 3.09
aumento 3.35
caso 3.95
autoridade 3.50
estratégia 3.86
fazer 3.88

8 palavras de conteúdo identificadas: ('aumento', 'N'), ('casos', 'N'), ('frustrou', 'V'), ('expectativas', 'N'), ('fez', 'V'), ('autoridades', 'N'), ('reverem', 'V'), ('estratégias', 'N')

8 palavras lematizadas: ['aumento', 'caso', 'frustrar', 'expectativa', 'fazer', 'autoridade', 'rever', 'estratégia']

Nenhuma palavra no intervalo de 5,50 a 7,00 de concretude

**Resultado Esperado**: 0,0

**Resultado Obtido**: 0,0

**Status**: correto




## Fórmula de Complexidade Sintática de Yngve




**Nome da Métrica**: yngve

**Interpretação**: Quanto maior o valor, maior a complexidade do texto

**Descrição da métrica**: A complexidade de Yngve baseia-se na premissa de que as árvores sintáticas das sentenças da língua inglesa tendem a se ramificar para a direita, e que desvios em relação a esse padrão correspondem a uma maior complexidade na linguagem. Dessa forma, a complexidade de Yngve procura medir o quanto uma árvore sintática se desvia desse padrão de ramificação. Se a forma de calcular a pontuação de cada nó envolver uma pilha, isto é, a partir de uma pilha utilizada em uma derivação de cima para baixo, da esquerda para a direita, o escore de uma palavra é dado pelo número de elementos que ainda permanecem na pilha quando a palavra é finalmente derivada. Alguns trabalhos da literatura, relacionaram o tamanho da pilha necessário para processar uma sentença à sua demanda de memória operacional, apesar de ele medir diretamente apenas o desvio de uma ramificação à direita.

**Definição dos termos que aparecem na descrição da métrica**:

**Forma de cálculo da métrica**: Usando a árvore sintática de constituinte, atribuímos um peso para cada nó não-terminal da árvore, da seguinte maneira:

1. Para cada nó, atribuir peso 0 ao seu filho mais à direita, 1 ao segundo filho mais a direita, e assim por diante até chegar ao filho mais a esquerda. Dessa forma, os filhos serão numerados com peso 0, 1, 2, ... , da direita para a esquerda.

2. Em seguida, calcula-se a pontuação de cada palavra, dada pela soma dos pesos dos não-terminais existentes no caminho entre a raiz e a palavra.

3. Uma vez calculada a pontuação das palavras, a complexidade da sentença é calculada como a média dos valores encontrados.

**Recursos de PLN utilizados durante o cálculo**: parser sintático LX-Parser e tokenizador NLTK

**Limitações da métrica**: a métrica depende da precisão do parser e do tokenizador.

**Crítica**: Se o parser errar na construção da árvore, necessariamente isso afetará a métrica.

Quanto maior o tamanho e a complexidade da sentença, maior a probabilidade de o parser apresentar erros na construção da árvore de dependências.

**Projeto**: Coh-Metrix-Dementia

**Teste**: Os brasileiros esperam resultados concretos.

**Resultado Obtido**: 1,667

**Status**: dada uma árvore de constituintes construída, o cálculo foi conferido e está correto




## Fórmula de Complexidade Sintática de Frazier




**Nome da Métrica**: frazier

**Interpretação**: Quanto maior o valor, maior a complexidade do texto

**Descrição da métrica**: Frazier propôs uma abordagem bottom-up para o cálculo da complexidade sintática de uma sentença, que parte da palavra e sobe na árvore sintática até encontrar um nó que não seja o filho mais à esquerda de seu pai. Cada nó na árvore recebe uma pontuação 1, e nós filhos de nós do tipo sentença, 1.5. A pontuação de cada palavra é dada pela soma das pontuações dos nós pertencentes a seu ramo.

**Definição dos termos que aparecem na descrição da métrica**:

**Forma de cálculo da métrica**: Para calcular a complexidade de uma sentença, é preciso que se tenha sua árvore sintática. Por exemplo: considere a oração em inglês "She found a cat with a red tail.". Suponha que cada nó tenha um peso. Um peso marcado com [x] indica fim de ramo. 
Nesse exemplo, para a derivação da palavra "She", o nó imediatamente acima teria uma etiqueta morfossintática PRP (pronome). Esse nó é incluído na contagem, pois é o filho mais à esquerda de NP, recebendo pontuação 1; PRP é filho de NP, que é o filho mais à esquerda de seu pai, e como seu pai é um nó do tipo sentença, recebe pontuação 1.5; portanto, a pontuação de "She" é 1 + 1.5 = 2.5. Para o cálculo da pontuação de "found", seu nó pai VBD (verbo direto) é incluído no cálculo, pois é o filho mais à esquerda de VP, recebendo pontuação 1; porém, o pai de VBD, VP, não é incluído, pois não é o filho mais à esquerda de S; portanto, a derivação para, e a pontuação de "found" é 1. No caso de "cat", nem mesmo seu nó pai NN é incluído, pois não é o filho mais à esquerda de NP, recebendo pontuação 0.

Frazier propôs dividir a sentença em trigramas para fazer o cálculo. Para calcular a complexidade da sentença, calcula-se a soma das pontuações das palavras em cada trigrama, usando o máximo dessas somas numa varredura da esquerda pra direita. A complexidade de um texto é a média da complexidade de Frazier para cada sentença.

**Recursos de PLN utilizados durante o cálculo**: parser sintático LX-Parser e tokenizador NLTK
**Limitações da métrica**: a métrica depende da precisão do parser e do tokenizador.

**Crítica**: Se o parser errar na construção da árvore, necessariamente isso afetará a métrica.
Quanto maior o tamanho e a complexidade da sentença, maior a probabilidade de o parser apresentar erros na construção da árvore de dependências.

**Projeto**: Coh-Metrix-Dementia

**Teste**: Os brasileiros esperam resultados concretos.

**Resultado Obtido**: 5,0

**Status**: dada uma árvore de constituintes construída, o cálculo foi conferido e está correto




## Distância na árvore de dependências



**Nome da Métrica**: dep_distance

**Interpretação**: Quanto maiores as distâncias de dependência, maior a complexidade do texto

**Descrição da métrica**: A distância de dependência utiliza uma árvore de dependências para realizar o cálculo. A cada relação de dependência está associada uma distância entre as palavras na superfícies textual.

Estudos da literatura mostram que essas distâncias entre palavras nas relações de dependência são diretamente proporcionais ao tempo de processamento em tarefas de compreensão de sentenças; grandes distâncias entre palavras relacionadas geram overhead de memória.

**Definição dos termos que aparecem na descrição da métrica**:

**Forma de cálculo da métrica**: A métrica é calculada como a soma das distâncias associadas às relações de dependências. O valor final para um texto é a média dos valores de complexidade para cada sentença.

**Recursos de PLN utilizados durante o cálculo**: parser de dependências MaltParser, tokenizador NLTK

**Limitações da métrica**: a precisão da métrica depende do desempenho do tokenizador e do parser

**Crítica**: Se o parser errar na construção da árvore, necessariamente isso afetará a métrica.
Quanto maior o tamanho e a complexidade da sentença, maior a probabilidade de o parser apresentar erros na construção da árvore de dependências.

**Projeto**: Coh-Metrix-Dementia

**Teste 1**: Ela encontrou um gato com um rabo vermelho.

**Resultado Obtido**: 9,0

**Status**: dada uma árvore de dependências construída, o cálculo foi conferido e está correto

