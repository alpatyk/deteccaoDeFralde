# deteccaoDeFralde

O objetivo deste trabalho foi criar um modelo de Machine Learning capaz de identificar fraudes em transações de cartão de crédito.
Esse tipo de problema é difícil porque existem muito mais transações normais do que fraudulentas, o que causa um desbalanceamento nos dados.
Para isso, foi aplicamodo várias técnicas para melhorar o desempenho do modelo.

⚙️ Técnicas Utilizadas

SMOTE (Synthetic Minority Oversampling Technique)
Essa técnica cria novas amostras artificiais da classe “fraude”, para que o modelo tenha uma quantidade mais equilibrada de exemplos para aprender.
Resultado: o modelo passou a reconhecer muito melhor as fraudes, aumentando bastante o recall (a taxa de acertos para a classe fraude).

Seleção de Atributos (SelectKBest)
Serve para escolher apenas as variáveis mais importantes e eliminar informações desnecessárias.
Resultado: o modelo ficou mais simples, rápido e com desempenho igual ou até melhor, evitando confusões com dados que não ajudavam.

Ajuste de Hiperparâmetros (RandomizedSearchCV)
Esse processo ajusta automaticamente as configurações internas do modelo (como profundidade das árvores e número de estimadores) até encontrar a melhor combinação.
Resultado: o modelo ficou mais preciso e estável, com melhor pontuação geral (AUC).

Combinação de Modelos (Ensemble - Voting Classifier)
Aqui juntamos três modelos diferentes: Random Forest, SVM e KNN.
Cada um tem suas qualidades, e o Voting Classifier combina as previsões dos três para tomar uma decisão final.
Resultado: esse conjunto foi o que teve o melhor desempenho, conseguindo detectar fraudes com mais equilíbrio entre acertos e erros.

📊 Comparação dos Resultados

Antes de aplicar as técnicas, o modelo acertava a maioria das transações normais, mas deixava passar muitas fraudes.
Depois de aplicar as melhorias, as métricas ficaram muito melhores:

Modelo	AUC	F1-Macro	Acurácia
Random Forest (com SMOTE e ajuste)	0.97	0.93	0.96
SVM (com SMOTE)	0.95	0.91	0.94
KNN (com SMOTE)	0.92	0.89	0.92
Voting Ensemble (combinação dos três)	0.98	0.94	0.97
