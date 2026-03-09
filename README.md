[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/UdjIJbqz)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23036765&assignment_repo_type=AssignmentRepo)
# am-labs
Aprendizado de Máquina 2026.1- Rodrigo Torres Marques Rodrigues 

# Questão 1:
O meu objetivo foi preparar os dados garantindo que eu mantivesse a proporção original das classes (espécies de flores) tanto no conjunto de treino quanto no de teste. Eu fiz isso para evitar que o meu modelo aprendesse com dados desbalanceados ou fosse testado em uma realidade que não representa o dataset completo.

# Questão 2: 
Nesta etapa, eu apliquei um algoritmo de Árvore de Decisão, que cria regras lógicas baseadas nas características das flores para classificá-las. Ao calcular a acurácia em ambos os conjuntos, eu verifiquei não apenas se o meu modelo aprendeu bem (treino), mas principalmente se ele consegue generalizar para dados novos que nunca viu antes (teste).

# Questão 3: 
Nesta etapa, o meu objetivo foi transformar o modelo matemático em algo visual e compreensível. Utilizei a função plot_tree para enxergar a lógica de decisão do meu algoritmo:

Atributo na Raiz: Identifiquei a raiz como o primeiro nó (no topo). Observei como o algoritmo escolheu o atributo que melhor separou os meus dados logo de início.

Profundidade: Analisei o caminho mais longo entre a raiz e uma folha. Notei que uma profundidade muito alta poderia indicar que o meu modelo decorou os dados (overfitting), enquanto uma profundidade baixa indicaria que ele estava simples demais.

Ao observar o gráfico que gerei, consegui responder exatamente qual característica da flor considerei mais importante para a primeira divisão e quantos níveis de decisão precisei criar.

# Questão 4: 
Nesta atividade, foquei em entender como o parâmetro max_depth controla a complexidade do meu modelo. Ao limitar a profundidade, eu impedi que a minha árvore criasse regras específicas demais para os meus dados de treino.

Subajuste (Underfitting): Percebi que com max_depth muito baixo, a minha árvore ficava simples demais e apresentava acurácia baixa em ambos os conjuntos.

Ajuste Ideal: Encontrei o ponto onde a minha acurácia de teste foi máxima.

Sobreajuste (Overfitting): Notei que com max_depth alto ou None, a minha acurácia de treino chegava a 100%, mas a de teste caía, pois o meu modelo "decorava" o ruído em vez de aprender o padrão.

Minha Tabela de Resultados:
Gerei uma tabela que me permitiu comparar visualmente o crescimento do número de folhas e da profundidade real em relação ao desempenho, ajudando-me a escolher o melhor modelo.

# Questão 5:
Nesta atividade, eu explorei como diferentes funções matemáticas decidem onde "cortar" os meus dados. Utilizei o Gini e a Entropia para medir a desordem dos dados em cada nó.

Gini: Utilize o padrão do scikit-learn, que tendeu a ser mais rápido para isolar a classe mais frequente.

Entropia: Testei este critério baseado na teoria da informação, que resultou em árvores ligeiramente mais equilibradas.

Minha Comparação de Resultados:
Observei que, no dataset Iris, a diferença na acurácia final entre os dois critérios foi mínima. Foquei em notar se a estrutura da minha árvore mudava, preferindo o critério que chegava ao mesmo resultado com uma árvore mais curta.

# Questão 6: 
Diferente do max_depth, utilizei o min_samples_leaf para controlar o crescimento da minha árvore por baixo. Eu impedi que o meu modelo criasse ramos muito específicos para lidar com poucas amostras isoladas.

Meu Impacto na Generalização: Notei que valores muito baixos permitiam que a minha árvore crescesse até isolar cada dado (overfitting), enquanto valores muito altos a forçavam a ser genérica demais (underfitting).

Minha Interpretação: Defini o meu "melhor modelo" como aquele que manteve uma acurácia alta no teste mesmo restringindo o número de folhas, indicando que criei regras robustas baseadas em grupos significativos.