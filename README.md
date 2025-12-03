Este projeto explora o tradeoff entre precisão e diversidade em sistemas de recomendação na forma de um notebook.

Implementação e comparação de duas estratégias de **Re-Ranking** para mitigar viés de popularidade e aumentar a descoberta de novos itens, utilizando o algoritmo **SVD** como base. Utilização do RMSE e Item coverage como métricas.

Este projeto foi feito para a disciplina SCC0284 / SCC5966 - Sistemas de Recomendação ICMC-USP

O público-alvo são estudantes e profissionais da área de Sistemas de Recomendação. Há um formulário no final da página para avaliação do projeto.

## Funcionalidades

O projeto utiliza o dataset **MovieLens 100k** e implementa as seguintes etapas:

1.  **Modelo Baseline (SVD):**

      * Treinamento de um algoritmo de Fatoração de Matrizes (Singular Value Decomposition) usando a biblioteca `Surprise`.
      * Cálculo das métricas base de RMSE (Erro) e Item Coverage (Cobertura de Catálogo).

2.  **Estratégia 1: Penalização por Popularidade (Popularity Penalty):**

      * Aplica uma penalidade na pontuação final de itens muito populares.
      * Analisa o impacto variando o parâmetro $\alpha$.

3.  **Estratégia 2: MMR (Maximal Marginal Relevance):**

      * Reordena a lista de recomendações buscando equilibrar a relevância do item com a sua "novidade" em relação aos itens já selecionados para o usuário.
      * Analisa o impacto variando o parâmetro $\lambda$.

## Métricas

  * RMSE (Root Mean Squared Error)
  * Item Coverage (Diversidade)

## Instruções de instalação


1. Clonar ou Baixar o Projeto
2. Instalar Dependências:

```bash
# Criação do ambiente virtual (Opcional)
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate

# Instalação das bibliotecas
pip install pandas numpy matplotlib seaborn scikit-learn scikit-surprise jupyter
```

## Como Rodar

1.  Abra o terminal na pasta do projeto.
2.  Inicie o Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
3.  Abra o arquivo `.ipynb` pelo jupyter.
4.  Execute todas as células sequencialmente.
5.  Alternativamente, use o Google Collab.

## Resultados

Ao final da execução, você verá dois gráficos demonstrando que:

1.  **Penalização por Popularidade:** Tende a aumentar a diversidade de forma segura, com baixo impacto negativo no RMSE.
2.  **MMR:** É extremamente agressivo no aumento da diversidade (podendo atingir \~70% de cobertura do catálogo), mas causa uma degradação maior na precisão das notas (aumento do RMSE).

## Avaliação do projeto

Por favor, avalie o projeto por meio deste [formulário](https://forms.gle/VGwdsntLCKRFBFnY8)

