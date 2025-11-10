# 📈 Análise de Outliers em Vendas de Filiais (Método IQR com Excel)

Este repositório documenta um projeto de Análise de Dados focado na identificação e visualização de valores atípicos (Outliers) nos dados de vendas de três filiais.

O projeto foi desenvolvido como parte do curso **"Ciência de Dados para Negócios usando Excel"** do Professor **Fernando Amaral** na **Udemy**.

## 🎯 Objetivo do Projeto

Analisar a distribuição dos dados de vendas para as Filiais A, B e C, utilizando o **método estatístico do Intervalo Interquartil (IQR)** para identificar outliers e, posteriormente, visualizá-los e propor o tratamento adequado.

## 🛠️ Tecnologias e Ferramentas

* **Microsoft Excel:** Utilizado para todos os cálculos estatísticos, análise e visualização (Formatação Condicional).
* **Estatística Descritiva:** Média, Mediana, Desvio Padrão, Variância, Quartis (Q1, Q3), IQR.

## 📁 Estrutura do Repositório

* `dados_vendas.xlsx` (Simulação): Planilha que contém os dados brutos de vendas e os cálculos realizados.
* `Image_Calculos.png`: Captura de tela mostrando os cálculos de estatísticas descritivas e os limites de Outliers.
* `Image_Visualizacao.png`: Captura de tela mostrando a aplicação da Formatação Condicional para destaque dos Outliers.
* `README.md`: Este documento com o passo a passo da análise.

## 📋 Passo a Passo da Análise

### 1. Preparação e Estatísticas Descritivas

O primeiro passo foi obter uma visão geral dos dados de vendas de cada filial.

| Métrica | Filial A | Filial B | Filial C |
| :--- | :--- | :--- | :--- |
| **Média** | 2.274,35 | 10.357,28 | 9.966,71 |
| **Mediana** | 1.030,84 | 9.999,61 | 9.945,57 |
| **Desvio Padrão** | 17.714,65 | 5.231,12 | 964,75 |

**Conclusão:** A alta diferença entre Média e Mediana da Filial A já sugeria a presença de valores extremos (outliers).

### 2. Cálculo dos Limites de Outliers (Método IQR)

O método IQR foi aplicado para definir, de forma robusta, os limites que separam os dados "normais" dos atípicos.

$$
IQR = Q3 - Q1
$$
$$
Limite Superior = Q3 + 1.5 \times IQR
$$
$$
Limite Inferior = Q1 - 1.5 \times IQR
$$

| Filial | Q1 | Q3 | IQR | Outlier Superior | Outlier Inferior |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **A** | 871,52 | 1.150,25 | 278,72 | **1.568,33** | **453,44** |
| **C** | 9.294,57 | 10.557,88 | 1.263,31 | **12.453,64** | **7.999,61** |

*(Nota: Os limites da Filial B também foram calculados, mas não indicaram outliers, tornando a filial B um baseline para dados estáveis).*

### 3. Visualização e Confirmação no Excel

A **Formatação Condicional** foi utilizada para destacar visualmente os valores que violaram os limites superior e inferior.

* **Filial A (Outlier Superior):** Um valor de **252.154,00** foi destacado, ultrapassando drasticamente o limite de $1.568,33$.
* **Filial C (Outlier Superior):** Um valor de **12.472,14** foi destacado, ligeiramente acima do limite de $12.453,64$.

[Incluir aqui a imagem da Formatação Condicional para referência (Image_Visualizacao.png)]

### 4. Conclusão e Tratamento Proposto

Os outliers foram identificados, e o próximo passo crucial é o **Tratamento de Outliers** para não distorcer as análises preditivas:

1.  **Investigação da Fonte:** O outlier da Filial A é extremamente alto e deve ser investigado como um provável **erro de digitação (Data Entry Error)**.
2.  **Ação (Filial A):** Se for erro, o valor deve ser **corrigido ou removido** para garantir a integridade da média.
3.  **Ação (Filial C):** Como é um outlier menos extremo, a análise deve ser feita com cautela: se o valor for legítimo, pode-se optar por **substituí-lo pela Mediana** em modelos que são sensíveis a esses valores extremos.

## 🧑‍💻 Autor

Bruno Cesar da Silva Garcia - Aluno de Ciência de dados e Desenvolvedor em Análise de Dados

---
