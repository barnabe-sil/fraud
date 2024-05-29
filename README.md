# FRAUDE

## O que é fraude?

## Como previnir?

### Pontos de análise

#### Onboarding
#### Transacional
#### Monitoramento externo

### Regras duras

### Modelos

# MÉTRICAS DE PIPELINE DE RISCO

Objetivo: Descrever de forma clara os principais conceitos utilizados para avaliação de modelos de classificacao para prevenção/detecção a fraude.

![image](https://github.com/barnabe-sil/fraud/assets/58343187/7e463514-0324-46c9-9a51-03a065db1511)

Matriz de Confusão: A "Matriz de Confusão" é como um relatório de desempenho para nossas previsões. Ela é chamada de matriz porque se parece com uma tabela que separa nossas previsões em quatro categorias. Para simplificar, vamos supor que nosso modelo esteja tentando prever se uma transação é uma fraude, mas poderíamos estar avaliando qualquer outro tipo de evento. Abaixo, faremos uma “tradução” simplista de como cada variável resposta pode ser interpretada:
- Verdadeiro positivo (TP): Esses são os casos em que nosso modelo acertou em cheio! Ele previu que a transação era uma fraude, e bingo! Realmente era uma fraude.
- Falso positivo (FP): Esses são os "oops!" do nosso modelo. Ele levantou um alarme falso, dizendo "É uma fraude!", mas na verdade, a transação era normal.
- Verdadeiro negativo (TN): Mais uma vitória para o nosso modelo! Ele previu que a transação não era uma fraude e, na verdade, estava correta.
- Falso negativo (FN): Aqui é onde o nosso modelo deixa passar. Ele disse: "Tudo bem por aqui, nenhuma fraude!" Mas a transação era, de fato, fraudulenta.

Métricas: Agora, usando essas quatro categorias, podemos calcular algumas medidas úteis para entender o desempenho do nosso modelo:
- Cobertura (Recall / Sensibilidade): É basicamente a proporção de fraudes reais que nosso modelo conseguiu identificar. Calculamos isso dividindo os verdadeiros positivos (fraudes que o modelo acertou) pelo total de fraudes reais, que é a soma dos verdadeiros positivos e dos falsos negativos (fraudes que o modelo perdeu). 
cobertura = TP / (TP + FN)
- Precisão: Esta medida nos diz o quão confiáveis são os alertas de fraude do nosso modelo. Calculamos isso dividindo os verdadeiros positivos (fraudes que o modelo acertou) pelo total de alertas de fraude que o modelo deu, ou seja, a soma dos verdadeiros positivos e dos falsos positivos (alertas de fraude que eram alarmes falsos). 
 precisao = TP / (TP + FP)
- Taxa de falso positivo (Fall-out / False Positive Rate): Este é o número de falsos alarmes que nosso modelo dá. Calculamos isso dividindo os falsos positivos (alertas de fraude que eram alarmes falsos) pelo total de transações não fraudulentas, que é a soma dos falsos positivos e dos verdadeiros negativos (transações que o modelo acertou ao dizer que não eram fraudes). 
FP / (FP + TN)
- Acurácia: Esta é uma visão geral do desempenho do nosso modelo. Calculamos isso somando os verdadeiros positivos (fraudes que o modelo acertou) e os verdadeiros negativos (transações que o modelo acertou ao dizer que não eram fraudes), e dividindo pelo total de transações. 
acuracia= (TP + TN) / (TP + TN + FP + FN).
- F1 Score: Esta é uma maneira de equilibrar a precisão e o recall. Calculamos isso multiplicando a precisão e o recall por 2, somando os resultados e depois dividindo a soma pela soma da precisão e do recall novamente. Em resumo: 
f1_score = 2 * (Precisão * Cobertura) / (Precisão + Cobertura)
