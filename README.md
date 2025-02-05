# Modelo SIRDV para Simulação da COVID-19 em Pernambuco

Modelo SIRDV para simulação da COVID-19 em Pernambuco utilizando modelos epidemiológicos, que fazem uso de sistemas de Equações Ordinárias Diferenciais, ou do inglês, ODE's (Ordinary Diferential Equations). Com esses modelos, é possível fazer uma simulação de como uma epidemia irá se comportar com base em diversos parâmetros.

## Descrição do Projeto

Este projeto tem como objetivo simular o comportamento da COVID-19 no estado de Pernambuco, Brasil, utilizando um modelo epidemiológico SIRDV (Suscetíveis, Infectados, Recuperados, Óbitos, Vacinados). O modelo é baseado em um sistema de equações diferenciais ordinárias (ODEs) que descrevem a dinâmica da epidemia, considerando a taxa de vacinação e a eficácia das vacinas utilizadas na região.

## Autores

- Leônidas Dantas de Castro Netto (ldcn)
- Matheus Júlio Boncsidai de Oliveira (mjbo)
- Victória Luquet Tewari (vllst)

CIn-UFPE, Recife

## Resumo dos Algoritmos Implementados

1.  **Análise Exploratória de Dados (AED):**
    - Carregamento e visualização dos dados gerais da COVID-19 em Pernambuco (confirmados, óbitos, recuperados, etc.).
    - Carregamento e visualização dos dados de vacinação (número de doses aplicadas).
    - Criação de histogramas para visualizar a distribuição de casos confirmados, óbitos e doses de vacina.
    - Cálculo de estatísticas descritivas para as doses de vacina (média, desvio padrão, etc.).
2.  **Modelo SIRDV:**
    - Implementação do sistema de equações diferenciais que descreve o modelo SIRDV.
    - Definição dos parâmetros do modelo:
      - Taxa de transmissão ($\beta$)
      - Taxa de recuperação ($\gamma$)
      - Taxa de mortalidade ($\mu$)
      - Taxa de vacinação ($\alpha$)
      - Eficácia da vacina ($\eta$)
    - Utilização da função `odeint` do SciPy para resolver numericamente o sistema de ODEs.
    - Plotagem dos resultados da simulação, mostrando a evolução das classes S, I, R, D e V ao longo do tempo.
3.  **Taxa de Morte Ajustada:**
    - A taxa de morte foi utilizada dinamicamente no código, tendo em vista que a mesma é mutável com o tempo.
    - Usando a biblioteca "odeint", conseguimos passar como argumento no nosso modelo uma função que simula uma taxa que se altera no tempo, diferente de uma taxa fixa passada como variável.

## Pré-requisitos

Para executar este projeto, você precisará ter o Python 3 instalado, juntamente com as seguintes bibliotecas:

- pandas
- numpy
- scipy
- matplotlib
- seaborn

Você pode instalar as bibliotecas utilizando o `pip`:

```bash
pip install pandas numpy scipy matplotlib seaborn
```

## Como Rodar

1.  **Certifique-se de ter os dados necessários:**

    Os arquivos CSV com os dados gerais (`Dados_Gerais.csv`) e de vacinação (`NumeroVacinados_1.csv`) devem estar presentes no diretório raiz do projeto. Esses arquivos devem ser baixados dos links fornecidos na seção de referências do notebook.

2.  **Execute o Notebook:**

    Abra o arquivo `Modelo SIRDV para simulação da COVID-19 em Pernambuco.ipynb` utilizando o Jupyter Notebook ou Google Colab:

    ```bash
    jupyter notebook "Modelo SIRDV para simulação da COVID-19 em Pernambuco.ipynb"
    ```

    ou

    1.  Acesse o Google Colab ([colab.research.google.com](https://colab.research.google.com/)).
    2.  Faça o upload do arquivo `Modelo SIRDV para simulação da COVID-19 em Pernambuco.ipynb`.

3.  **Execute as Células:**

    Execute as células do notebook sequencialmente. Certifique-se de que todas as bibliotecas foram importadas corretamente e que os dados estão sendo carregados sem erros. A última célula gerará o gráfico da simulação SIRDV.

## Estrutura de Arquivos

- `Modelo SIRDV para simulação da COVID-19 em Pernambuco.ipynb`: Notebook Jupyter com o código completo do projeto.
- `Dados_Gerais.csv`: Arquivo CSV com os dados gerais da COVID-19 em Pernambuco.
- `NumeroVacinados_1.csv`: Arquivo CSV com os dados de vacinação em Pernambuco.
- `README.md`: Este arquivo.

## Fontes de Dados

Os dados utilizados neste projeto foram obtidos das seguintes fontes:

- **Dados Gerais:** [https://dados.seplag.pe.gov.br/apps/corona.html](https://dados.seplag.pe.gov.br/apps/corona.html)
- **Número de Vacinas:** [https://app.powerbi.com/view?r=eyJrIjoiNmI1NDcyYTUtYTlhMS00ZWFlLWE4MTYtOGQzM2RkMzgyOTAxIiwidCI6ImQ1ZTU0MGZmLTkzNzAtNGNhMi04YmVmLWQwMzcyMWQxM2MwNSJ9&pageName=ReportSectiondc8ac2b66d0753222000](https://app.powerbi.com/view?r=eyJrIjoiNmI1NDcyYTUtYTlhMS00ZWFlLWE4MTYtOGQzM2RkMzgyOTAxIiwidCI6ImQ1ZTU0MGZmLTkzNzAtNGNhMi04YmVmLWQwMzcyMWQxM2MwNSJ9&pageName=ReportSectiondc8ac2b66d0753222000)

## Observações

- Os resultados da simulação são sensíveis aos valores dos parâmetros do modelo. É importante ajustar os parâmetros com base em dados e evidências mais recentes.
- Este projeto é uma simulação simplificada da dinâmica da COVID-19 e não deve ser utilizado para tomadas de decisão críticas sem a devida validação e análise por especialistas.
