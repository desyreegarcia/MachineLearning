# Trabalho Acadêmico Machine Learning

DESYREE N. GARCIA BATISTA.
RU:  986134
Prof. Rodrigo da S. do Nascimento
Prof. Osmar Dias Jr.

Descrição do Trabalho Acadêmico da disciplina de Machine Learning um dos temas abaixo
1 - Sistema de Classificação com Machine Learning

O objetivo foi desenvolver um modelo capaz de prever uma categoria (0 para Sol ou 1 para Chuva) em Curitiba, utilizando dados históricos do INMET de 2025 para treinar e 2026 para testar.

Desempenho Geral
Todos os modelos apresentaram uma Acurácia próxima a 89%. Parece um resultado excelente, mas a análise detalhada mostrou o "fenômeno do desbalanceamento": como Curitiba teve muito mais dias de sol do que de chuva na base de dados de 2025, os modelos aprenderam a prever "Sol" com facilidade, mas tiveram dificuldade em detecta a chuva.

Comparativo de Modelos
Random Forest: Foi o modelo mais equilibrado. Ele obteve a maior acurácia e o melhor F1-Score, conseguindo detectar quase o dobro de chuvas que os outros modelos sem dar tantos alarmes falsos.
Regressão Logística: Mostrou-se um modelo muito sólido e simples para prever tempo firme, sendo o mais "seguro" quando o assunto é confirmar que não vai chover.
KNN: Teve um bom desempenho geral, mas sofreu para identificar chuvas isoladas, pois os "vizinhos" de dias chuvosos em Curitiba muitas vezes se parecem com dias nublados.
Árvore de Decisão: Criou regras claras e fáceis de entender, mas sozinha não foi tão precisa quanto a Random Forest.

Conclusão Crítica
A maior lição desta etapa foi que Acurácia não é tudo. O sistema é um excelente "confirmador de tempo bom", mas ainda é conservador para prever chuva. Para um sistema real de Defesa Civil, por exemplo, precisaríamos aplicar técnicas de balanceamento de dados para que o modelo fosse mais sensível aos dias chuvosos.
 
2 - Sistema de Predição com Machine Learning (Regressão)

O objetivo desta etapa foi desenvolver um modelo capaz de prever um valor numérico exato (a temperatura em °C) para Curitiba, baseando-se em variáveis como umidade, pressão atmosférica e radiação solar.

Desempenho e Métricas
Foram testamos quatro algoritmos (Regressão Linear, Árvore de Decisão, Random Forest e SVR) para encontrar o que melhor se adaptava ao clima da região.
O Modelo SVR apresentou o melhor desempenho geral, alcançou um MAE de 1.78°C. Isso significa que as previsões do sistema são altamente confiáveis, errando, em média, menos de 2 graus em relação à temperatura real registrada pelas estações do INMET.
Com um coeficiente de determinação de 0.63, o modelo provou que consegue explicar a maior parte das variações térmicas apenas com os três sensores utilizados.

Análise de Variáveis
A análise exploratória (EDA) foi fundamental para o sucesso do modelo pois foi confirmado que Umidade e Radiação são os fatores mais decisivos: dias com alta radiação e baixa umidade resultam invariavelmente em picos de temperatura.
O Pré-processamento (StandardScaler) foi essencial para o SVR, garantindo que a Radiação (que chega a 4000) não "esmagasse" a Pressão (que fica em torno de 900) nos cálculos matemáticos.

Conclusão do Projeto
O sistema de regressão demonstrou ser uma ferramenta poderosa para o planejamento urbano. Embora o clima de Curitiba seja conhecido por mudanças bruscas, o modelo conseguiu captar a tendência de aquecimento e resfriamento com precisão técnica superior aos modelos lineares simples.
 
Links úteis:
Base de dados Fonte: https://portal.inmet.gov.br/dadoshistoricos
GitHub: https://github.com/desyreegarcia/MachineLearning.git
