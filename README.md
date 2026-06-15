# Trabalho_Modelos_IA

Disciplina de Inteligência Artificial - Professor Munif - 
Unicesumar 2026 

1. Identificação da Equipe 
Arthur Antonio Rabelo de Souza - RA: 23003805-2 
Felipe Saueressig Mello - RA: 23167656-2

2. Resumo do Projeto 
Contextualização e Problema 
No mercado financeiro atual, a análise de risco de crédito é crucial para a 
saúde das instituições bancárias. O problema investigado consiste em prever o 
risco de inadimplência (loan default) de clientes que solicitam empréstimos, 
além de estimar a taxa de juros ideal baseada no perfil de risco.

Hipótese da Equipe 
A hipótese do grupo é de que o modelo Random Forest apresentará 
resultados superiores ao KNN em ambas as frentes (classificação e 
regressão). Isso se deve à capacidade do Random Forest de lidar de forma 
robusta com dados desbalanceados (comuns em inadimplência) e de criar 
regras de decisão não lineares complexas sem sofrer tanto com a dispersão 
multidimensional. 

3. Descrição do Dataset 
Nome: Credit Risk Dataset (laotse/credit-risk-dataset) obtido via API do Kaggle. 
Quantidade de Registros: ~32.000 amostras simuladas de bureau de crédito. 
Principais Atributos: Idade, renda anual, tempo de emprego, valor do 
empréstimo, intenção do empréstimo, nota de risco do banco e histórico prévio 
de inadimplência. 
Variáveis Alvo: `alvo_inadimplente` (0 para adimplente, 1 para inadimplente) na 
abordagem de Classificação. `taxa_juros` (valor numérico contínuo) na 
abordagem de Regressão. 
Tratamento de Dados: Os valores ausentes nas colunas de taxa de juros e 
tempo de emprego foram preenchidos utilizando a mediana dos dados. 
Variáveis categóricas textuais foram convertidas para numéricas através de 
One-Hot Encoding. Os dados foram divididos na proporção de 80% para treino 
e 20% para teste.

4. Métodos de IA Utilizados 
Parte 1 da Disciplina: K-Nearest Neighbors (KNN) aplicado para Classificação e 
Regressão (com normalização `StandardScaler`). 
Parte 2 da Disciplina: Random Forest (Classifier e Regressor) utilizando 
conjuntos de árvores de decisão emparelhadas.

5. Avaliação e Comparação dos Modelos 
5.1 Frente de Classificação (Prever Inadimplência)
<img width="1000" height="723" alt="Matriz de Confusão" src="https://github.com/user-attachments/assets/bb363ba8-c01a-47fb-adfe-8ccbc85f9c4f" />
Resultados Estatísticos: 
O modelo Random Forest obteve melhor desempenho geral, identificando de 
forma mais assertiva a classe de risco (Inadimplentes), apresentando métricas 
de precisão e revocação mais equilibradas. 
O KNN apresentou dificuldades devido ao desbalanceamento natural da base 
de dados.

5.2 Frente de Regressão (Prever Taxa de Juros)
<img width="726" height="555" alt="Métricas de Regressão" src="https://github.com/user-attachments/assets/fe47334c-f145-4fcf-a00f-e0b136701abe" />
Resultados Obtidos: 
Random Forest Regressor: RMSE de 1.3279% | R² Score de 0.8190 
KNN Regressão: RMSE de 1.4482% | R² Score de 0.7848

6. Conclusão 
A análise crítica confirmou a nossa hipótese inicial. O algoritmo Random Forest 
sobressaiu-se em ambos os cenários de testes. Na classificação, mitigou os 
impactos do desbalanceamento dos dados. Na regressão, conseguiu explicar 
81,90% da variabilidade da taxa de juros (R²), contra 78,48% do KNN. Conclui
se que arquiteturas baseadas em árvores de decisão em comitê (*ensembles*) 
são mais recomendadas para cenários complexos de análise de crédito do que 
abordagens baseadas estritamente em proximidade geométrica (KNN).

7. Como Executar o Projeto 
O projeto foi desenvolvido inteiramente em um Notebook do Google Colab. Não 
é necessário instalar nada em sua máquina local para testá-lo. 
Passo a Passo: 
1. Abra o arquivo `TrabalhoFinal_Munif.ipynb` presente neste repositório. 
2. No topo da página (pelo GitHub), você verá um botão escrito "Open in 
Colab" (Abrir no Colab). Clique nele. 
3. No menu superior do Colab, clique em Ambiente de execução -> Executar 
tudo. 
4. O download da base de dados será feito de forma 100% automática através 
da API do Kaggle já configurada no código. 
5. EXTRA: Caso queira ver o dataset na íntegra, o link é esse: 
https://www.kaggle.com/datasets/laotse/credit-risk-dataset
