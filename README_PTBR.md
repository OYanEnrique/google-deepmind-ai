# 🚀 Google DeepMind: AI Research Foundations

<div align="center">
  <img src="https://storage.googleapis.com/dm-educational/assets/ai_foundations/GDM-Labs-banner-image-C1-white-bg.png" alt="Google DeepMind AI Foundations Banner" width="100%">
  <br><br>
  <p>
    <b>Uma jornada épica pelas bases matemáticas e práticas da Inteligência Artificial Generativa moderna.</b>
  </p>
  <p>
    🇬🇧 <a href="./README.md">English Version (Versão em Inglês)</a>
  </p>
</div>

---

## 🗺️ A Jornada: AI Research Foundations
Este repositório documenta minhas pesquisas práticas e explorações ao longo do currículo **Google DeepMind: AI Research Foundations**. Este programa de nível universitário mergulha profundamente nos mecanismos internos dos Grandes Modelos de Linguagem (LLMs), partindo da probabilidade básica até a construção, treinamento e otimização de arquiteturas neurais complexas.

* **Link da Trilha:** [Google DeepMind: AI Research Foundations](https://www.skills.google/paths/3135)
* **Repositório do GitHub:** [OYanEnrique/google-deepmind-ai](https://github.com/OYanEnrique/google-deepmind-ai)
* **Autor:** [@OYanEnrique](https://github.com/OYanEnrique)

---

## 📖 Capítulo 1: A Magia da Próxima Palavra
*Como as máquinas geram texto? Começamos simulando a intuição central dos modelos de linguagem: prever a próxima palavra com base no contexto.*

```
[Prompt] "Jide was hungry so she went looking for..." ---> [Distribuição de Probabilidade] ---> [Amostragem] ---> "food"
```

### Laboratórios e Descobertas
* [**`01-Google-Deepmind.ipynb`**](./notebooks/01-Google-Deepmind.ipynb) — **Criando Distribuições de Probabilidade**
  * **A Missão:** Entrar no papel de uma IA. Diante do prompt *"Jide was hungry so she went looking for..."*, atribuímos manualmente pesos de probabilidade a palavras candidatas e as amostramos usando `random.choices`.
  * **A Descoberta:** Aprendi que a geração de texto é fundamentalmente estocástica. Ao alterar o contexto (ex: de *hungry* para *thirsty*), observamos como o "modelo mental" do modelo altera os pesos de probabilidade das palavras candidatas.
* [**`02-Google-Deepmind.ipynb`**](./notebooks/02-Google-Deepmind.ipynb) — **Modelos N-Gram**
  * **A Missão:** Em vez de adivinhar probabilidades, automatizamos o processo contando ocorrências de palavras em um corpus de texto, construindo modelos Bigram e Trigram.
  * **A Descoberta:** Descobri a mecânica do PNL estatístico clássico. Modelos N-Gram calculam probabilidades olhando para trás apenas as últimas $N-1$ palavras. Embora rápidos, eles não conseguem capturar contextos de longo prazo devido a essa janela limitada.
* [**`03-Google-Deepmind.ipynb`**](./notebooks/03-Google-Deepmind.ipynb) — **N-Grams vs. Transformers**
  * **A Missão:** Colocar um modelo clássico N-Gram contra um modelo Transformer de última geração na tarefa de completação de texto.
  * **A Descoberta:** Uma percepção marcante do poder do "mecanismo de atenção". Os Transformers não olham apenas para as últimas palavras; eles capturam dependências semânticas ao longo de toda a frase, evitando as repetições sem sentido comuns dos N-Grams.
* [**`04-Google-Deepmind.ipynb`**](./notebooks/04-Google-Deepmind.ipynb) — **Preparando o Dataset para um SLM**
  * **A Missão:** Construir um pipeline de dados completo para limpar, formatar e estruturar textos brutos em conjuntos de dados de treinamento para um Modelo de Linguagem Pequeno (SLM).
  * **A Descoberta:** A constatação de que "lixo entra, lixo sai" é uma realidade. Dominei a limpeza de textos, formatação de listas de tokens e construção de pares entrada-alvo eficientes para o treinamento autorregressivo.

---

## 📖 Capítulo 2: A Linguagem das Máquinas
*Para processar a linguagem, os computadores não podem usar caracteres ou palavras brutas. Devemos converter o texto humano em vetores matemáticos que capturam o significado.*

```
"Texto" ---> [Pré-processamento] ---> [Tokenização BPE] ---> [Camada de Embedding] ---> Espaço Vetorial (0.15, -0.82, ...)
```

### Laboratórios e Descobertas
* [**`05-Google-Deepmind.ipynb`**](./notebooks/05-Google-Deepmind.ipynb) — **Pré-processamento de Texto**
  * **A Missão:** Limpar dados de texto bruto removendo ruídos, normalizando letras maiúsculas/minúsculas, tratando caracteres especiais e convertendo o texto para um formato uniforme.
  * **A Descoberta:** Aprendi a higienizar o texto para reduzir o tamanho do vocabulário sem perder o significado semântico, estabelecendo as bases para uma tokenização eficiente.
* [**`06-Google-Deepmind.ipynb`**](./notebooks/06-Google-Deepmind.ipynb) — **Tokenização de Subpalavras**
  * **A Missão:** Explorar o meio-termo ideal entre representações ao nível de caractere e de palavra: as subpalavras.
  * **A Descoberta:** Compreendi como a tokenização de subpalavras lida de forma elegante com palavras "Fora do Vocabulário" (OOV). Ao quebrar palavras desconhecidas em subpalavras conhecidas, evitamos travamentos do modelo e mantemos o vocabulário sob controle.
* [**`07-Google-Deepmind.ipynb`**](./notebooks/07-Google-Deepmind.ipynb) — **Tokenização de Caractere vs. Palavra**
  * **A Missão:** Comparar a tokenização por caractere (sequências gigantescas, vocabulário minúsculo) com a tokenização por palavra (sequências curtas, vocabulário massivo).
  * **A Descoberta:** Visualize os tradeoffs: modelos de caracteres exigem processamento massivo para aprender palavras simples; modelos de palavras falham ao encontrar termos novos. Essa comparação solidificou o porquê de subpalavras serem o padrão da indústria.
* [**`08-Google-Deepmind.ipynb`**](./notebooks/08-Google-Deepmind.ipynb) — **Implementando um Tokenizador BPE**
  * **A Missão:** Construir um tokenizador Byte-Pair Encoding (BPE) do zero.
  * **A Descoberta:** Implementei o algoritmo principal que alimenta modelos como o GPT. Começando com caracteres individuais e fundindo repetidamente os pares de tokens mais frequentes, vi como um vocabulário personalizado cresce de forma adaptativa com base nas estatísticas do texto.
* [**`09-Google-Deepmind.ipynb`**](./notebooks/09-Google-Deepmind.ipynb) — **Experimentando com Embeddings**
  * **A Missão:** Traduzir tokens discretos em espaços vetoriais contínuos.
  * **A Descoberta:** Vivenciei a geometria da linguagem. Aprendi como relações semânticas (como sinônimos ou analogias) traduzem-se em distância geométrica (similaridade de cosseno) e como modelos agrupam conceitos relacionados em um espaço multidimensional.
* [**`10-Google-Deepmind.ipynb`**](./notebooks/10-Google-Deepmind.ipynb) — **Treinando um SLM com Tokenizador BPE**
  * **A Missão:** Integrar o tokenizador BPE construído do zero com um Small Language Model (SLM) e treiná-lo com dados de texto.
  * **A Descoberta:** Fechei o ciclo entre a tokenização e o treinamento. Observei como a qualidade das representações de tokens impacta diretamente a estabilidade e a coerência do texto gerado pelo modelo.

---

## 📖 Capítulo 3: Moldando o Cérebro Artificial
*Afastamo-nos das estatísticas puras e entramos no mundo do Deep Learning. Como projetamos redes que aprendem com o erro e ajustam seus próprios parâmetros?*

```
Entradas ---> [Pesos e Biases] ---> [Função de Ativação] ---> Cálculo da Perda ---> [Retropropagação] ---> Atualização
```

### Laboratórios e Descobertas
* [**`11-Google-Deepmind.ipynb`**](./notebooks/11-Google-Deepmind.ipynb) — **Sinal vs. Ruído**
  * **A Missão:** Determinar como uma função matemática pode traçar uma linha (fronteira de decisão) para classificar pontos de dados em grupos distintos.
  * **A Descoberta:** Compreendi o conceito de classificação linear e por que identificar padrões matemáticos limpos é crucial para filtrar o ruído caótico de fundo.
* [**`12-Google-Deepmind.ipynb`**](./notebooks/12-Google-Deepmind.ipynb) — **Redes Neurais de Camada Única**
  * **A Missão:** Implementar um classificador básico de neurônio único (Perceptron) para tomar decisões binárias.
  * **A Descoberta:** Dominei a forma como os pesos escalam as características (features) e como o viés (bias) desloca a fronteira de decisão, mapeando as entradas diretamente para previsões.
* [**`13-Google-Deepmind.ipynb`**](./notebooks/13-Google-Deepmind.ipynb) — **Separando Dados Complexos**
  * **A Missão:** Desafiar uma rede linear de camada única com conjuntos de dados não linearmente separáveis (como o problema XOR).
  * **A Descoberta:** Vivenciei o "limite linear". Entendi por que redes simples falham em padrões complexos, provando a necessidade absoluta de camadas ocultas e funções de ativação não lineares.
* [**`14-Google-Deepmind.ipynb`**](./notebooks/14-Google-Deepmind.ipynb) — **Projetando um MLP**
  * **A Missão:** Arquitetar um Perceptron Multicamadas (MLP) a partir do zero.
  * **A Descoberta:** Empilhando camadas de entrada, ocultas com ativações (como ReLU) e saída, entendi como as redes neurais distorcem o espaço vetorial para traçar fronteiras de decisão complexas e curvas.
* [**`15-Google-Deepmind.ipynb`**](./notebooks/15-Google-Deepmind.ipynb) — **Ajuste de Hiperparâmetros**
  * **A Missão:** Sintonizar taxas de aprendizado (learning rates), tamanhos de lote (batch size), épocas e tamanhos de camadas para otimizar velocidade e precisão.
  * **A Descoberta:** Percebi que o aprendizado profundo é tanto uma arte quanto uma ciência. Observei como taxas de aprendizado excessivas geram divergência e taxas muito baixas estagnam o modelo.
* [**`16-Google-Deepmind.ipynb`**](./notebooks/16-Google-Deepmind.ipynb) — **Mitigando Overfitting**
  * **A Missão:** Treinar um modelo que não apenas decore o conjunto de treinamento, mas que generalize para dados de testes nunca vistos.
  * **A Descoberta:** Explorei a relação viés-variância (bias-variance trade-off) e apliquei técnicas de regularização (como decaimento de peso, dropout e parada precoce/early stopping) para impedir que o modelo memorizasse ruídos.
* [**`17-Google-Deepmind.ipynb`**](./notebooks/17-Google-Deepmind.ipynb) — **Gradientes e Retropropagação**
  * **A Missão:** Desvendar a engrenagem fundamental da IA: os gradientes e a regra da cadeia.
  * **A Descoberta:** Calculei gradientes manualmente para compreender como a perda (loss) retropropaga pela rede, ajustando os pesos por meio do Gradiente Descendente.
* [**`18-Google-Deepmind.ipynb`**](./notebooks/18-Google-Deepmind.ipynb) — **Treinando com Keras**
  * **A Missão:** Transição da matemática manual de baixo nível para a construção em alto nível usando Keras.
  * **A Descoberta:** Construí, compilei e treinei modelos de deep learning de forma ágil e eficiente, utilizando ferramentas padrão do setor para automatizar definições de modelos, otimização de perdas e fluxos de avaliação.

---

## 📖 Capítulo 4: Descobrindo a Arquitetura Transformer
*Como os transformers processam a informação? Mergulhamos nos componentes principais da arquitetura transformer: atenção, configurações multi-head, mascaramento, embeddings posicionais e escalabilidade de parâmetros.*

```
Tokens de Entrada ---> [Embeddings + Codificação Posicional] ---> [Atenção Multi-Head Mascarada] ---> [LayerNorm & MLP] ---> Previsões do Próximo Token
```

### Laboratórios e Descobertas
* [**`19-Google-Deepmind.ipynb`**](./notebooks/19-Google-Deepmind.ipynb) — **Visualizando Pesos de Atenção**
  * **A Missão:** Entrar no funcionamento interno de um transformer. Visualizamos como o mecanismo de atenção do modelo Gemma-1B distribui pesos sobre diferentes tokens de um prompt para prever a próxima palavra.
  * **A Descoberta:** Observei como a atenção muda entre as diferentes camadas do modelo e como ela consegue capturar dependências de longo alcance, atravessando a barreira das sentenças para buscar contexto do início do texto.
* [**`20-Google-Deepmind.ipynb`**](./notebooks/20-Google-Deepmind.ipynb) — **Implementando a Equação de Atenção**
  * **A Missão:** Entender a fundo a matemática do mecanismo de atenção, implementando do zero os cálculos de query, key e value ($Q, K, V$) usando JAX.
  * **A Descoberta:** Implementei a equação de atenção produto-escalar escalonada (scaled dot-product attention) fundamental, utilizando as matrizes de projeção do Gemma-1B para computar pesos de atenção personalizados e gerar embeddings contextuais.
* [**`21-Google-Deepmind.ipynb`**](./notebooks/21-Google-Deepmind.ipynb) — **Implementando Atenção Multi-Head Mascarada**
  * **A Missão:** Construir um mecanismo de atenção multi-head mascarada completo, aplicando mascaramento causal e processamento em paralelo para múltiplas cabeças.
  * **A Descoberta:** Compreendi como várias cabeças de atenção focam em diferentes partes do texto simultaneamente e por que o mascaramento causal é indispensável no treinamento autorregressivo para evitar que o modelo "trapaceie" olhando para os tokens futuros.
* [**`22-Google-Deepmind.ipynb`**](./notebooks/22-Google-Deepmind.ipynb) — **Embeddings Posicionais**
  * **A Missão:** Investigar a propriedade de invariância de ordem da autoatenção pura, demonstrando como alterar a ordem das palavras sem informações posicionais resulta na exata mesma saída.
  * **A Descoberta:** Uma percepção clara do porquê de as codificações posicionais serem obrigatórias. Sem elas, o transformer trata sentenças como um "saco de palavras" (bag of words), sendo incapaz de diferenciar *"o tigre perseguiu o leão"* de *"o leão perseguiu o tigre"*.
* [**`23-Google-Deepmind.ipynb`**](./notebooks/23-Google-Deepmind.ipynb) — **Parâmetros Treináveis no Modelo Transformer**
  * **A Missão:** Analisar a implementação modular de um transformer completo em Keras e JAX, escrevendo funções para calcular a quantidade exata de parâmetros de cada bloco constituivo.
  * **A Descoberta:** Dominei a dinâmica de escala de parâmetros dos transformers. Ao dissecar os componentes de LayerNorm, Embeddings, Atenção e MLP, aprendi como os hiperparâmetros e o tamanho do vocabulário escalam matematicamente o total de parâmetros treináveis.

---

## 🔮 A Missão Continua...

A jornada está longe do fim. A pasta de notebooks contém atualmente os laboratórios até o Curso 4. À medida que eu avançar nos módulos restantes da trilha, novos notebooks e conquistas serão consolidados aqui:

* [ ] **Google DeepMind: 05 Fine-Tune Your Model**
* [ ] **Google DeepMind: 07 Accelerate Your Model**

<div align="center">

<br>

**Autor do Projeto:** [Yan Enrique (OYanEnrique)](https://github.com/OYanEnrique)  
*(Cientista de Dados | Machine Learning Engineer)*

</div>

---

## 📝 Licença

Este projeto está sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
