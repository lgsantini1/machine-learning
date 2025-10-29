# Tech Challenge I - Classificação de ECG

Este repositório reúne os artefatos produzidos para o Tech Challenge da pós-graduação I. O objetivo é construir um sistema de apoio ao diagnóstico capaz de classificar exames de eletrocardiograma (ECG) como **saudáveis** ou **potencialmente não saudáveis**, priorizando a identificação de pacientes que necessitam de atenção.

## 📂 Estrutura do Projeto

| Arquivo | Descrição |
| --- | --- |
| `TechChalenge_ECG.ipynb` | Notebook principal com todo o pipeline de preparação, modelagem e avaliação.
| `Readme.md` | Este documento.

## 🧠 Visão Geral da Solução

1. **Integração de dados**: combinação de quatro arquivos (`12sl_features.csv`, `ptbxl_database.csv`, `ptbxl_statements.csv`, `scp_statements.csv`) para formar o dataset tabular utilizado no treinamento.
2. **Criação da label binária**: um ECG é rotulado como `Doente` se qualquer diagnóstico associado ao exame não for `NORM`; caso contrário recebe o rótulo `Saudável`.
3. **Modelagem**: comparação entre `DecisionTreeClassifier` (baseline) e `RandomForestClassifier`.
4. **Métricas principais**: a Random Forest alcançou **87% de acurácia** e **87% de recall** para a classe `Doente`, reduzindo o risco de falsos negativos.
5. **Interpretação**: análise da matriz de confusão e da importância das *features*, destacando atributos relacionados à morfologia da onda T.

## 🚀 Como Executar

1. Faça o download dos arquivos de dados mencionados acima e armazene-os em uma pasta acessível. No notebook, atualize a variável `path` para apontar para esse diretório.
2. Abra o notebook `TechChalenge_ECG.ipynb` no Google Colab ou em um ambiente local com Jupyter Notebook.
3. Execute as células sequencialmente. Caso utilize o Colab, será necessário montar o Google Drive para acessar os arquivos CSV.

> ℹ️ O notebook foi desenvolvido para rodar no Google Colab; algumas células utilizam APIs do Colab (ex.: `google.colab.drive`). Caso execute localmente, adapte essa etapa conforme o seu ambiente.

## ✅ Principais Resultados

- **Acurácia**: 0,87
- **Recall (classe Doente)**: 0,87
- **Precisão (classe Doente)**: 0,86
- **F1-Score (classe Doente)**: 0,87

Esses resultados indicam que o modelo possui boa capacidade de generalização e prioriza a identificação de pacientes com potenciais anormalidades.

## 📌 Próximos Passos Sugeridos

- Utilizar o *ECG Deli*, ferramenta open source para extração de métricas a partir de sinais brutos, possibilitando replicar o pipeline em diferentes instituições.
- Realizar *tuning* de hiperparâmetros (ex.: `GridSearchCV`, `RandomizedSearchCV`) para refinar o desempenho da Random Forest.
- Experimentar modelos baseados em *Gradient Boosting* (XGBoost, LightGBM, CatBoost).
- Evoluir para uma classificação multi-classe, identificando tipos específicos de anormalidades.

## 👥 Autores

- Luis Gustavo Santini
- Ivna Cavalcante Barros Meireles
- Joalisson dos Santos Borges
- Diego Santos Via
- Marina Souza Lucas

## 📄 Licença

Este projeto está disponível apenas para fins educacionais no contexto do Tech Challenge I. Verifique com a equipe responsável antes de utilizá-lo em outros contextos.
