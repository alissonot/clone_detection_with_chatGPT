# An Empirical Comparison of an LLM and PyTeRor for Identifying Test Clones in Python Test Suites

Este repositório contém o pacote de replicação do estudo empírico que
compara uma abordagem baseada em modelo de linguagem de grande escala
(LLM) com o PyTeRor na identificação de classes de clones do Tipo 2
passíveis de parametrização em suítes de testes Python baseadas em
`pytest`.

O pacote inclui:

- o notebook utilizado nas análises;
- as saídas originais das três execuções da LLM;
- a saída produzida pelo PyTeRor;
- as amostras utilizadas na inspeção manual;
- os arquivos intermediários e resultados derivados;
- os scripts utilizados no cálculo das métricas e na comparação das
  classes de clones.

## Objetivo do estudo

O objetivo deste estudo é avaliar a capacidade de uma LLM de
identificar, em funções de teste Python, classes candidatas de clones sintaticamente próximas que representem oportunidades válidas de parametrização, comparando os resultados obtidos com os de uma ferramenta especializada (PyTeRor).

As seguintes questões de pesquisa foram avaliadas:

- **RQ1:** Qual a proporção de classes candidatas identificadas pela LLM que constitui oportunidades válidas de parametrização?
- **RQ2:** Como o número de classes candidatas identificadas pela LLM se compara ao número de classes identificadas pelo PyTeRor?
- **RQ3:** Qual o grau de concordância entre os agrupamentos de funções produzidos pela LLM e pelo PyTeRor?

## Projetos avaliados

O estudo utilizou quatro projetos Python de código aberto que também foram
empregados na avaliação original do PyTeRor.

| Projeto | Propósito | Commit analisado |
|---|---|---|
| `requests` | Biblioteca cliente para requisições HTTP | `a58d7f2ffb4d00b46dca2d70a3932a0b37e22fac` |
| `parso` | Parser Python com suporte à recuperação de erros | `279fd6903ec9575f233067f3fc7b47f6fd6705d0` |
| `jedi` | Biblioteca de análise estática voltada a recursos de IDEs | `a4574a50d01e88316ddf554419cae64f547a7d70` |
| `astroid` | Representação de AST e inferência estática utilizada pelo Pylint | `7a3b482b9673243d2ccc895672eb1e452f5daa82` |

## Estrutura do repositório

```text
notebook_experimento/
    Contém o notebook principal com o processamento dos dados,
    amostragem, cálculos estatísticos e geração dos resultados.

arquivos_gerados_no_experimento/llm/
    Contém as saídas originais das três execuções independentes da LLM.

arquivos_gerados_no_experimento/pyteror/
    Contém a saída produzida pelo PyTeRor nos quatro projetos.

arquivos_gerados_no_experimento/manual/
    Contém as amostras selecionadas e os resultados da inspeção manual.

arquivos_gerados_no_experimento/resultados/
    Contém arquivos produzidos durante a normalização e comparação dos
    resultados.

arquivos_gerados_no_experimento/tabelas/
    Contém tabelas derivadas das análises.

arquivos_gerados_no_experimento/figuras/
    Contém figuras utilizadas ou produzidas durante o estudo.
