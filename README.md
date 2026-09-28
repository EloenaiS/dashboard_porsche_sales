
Dashboard executiva desenvolvida para análise de vendas de veículos Porsche, com foco em **receita, volume de vendas, modelos, localização geográfica e comportamento de pagamento**.

🔗 **Dashboard publicada:**  
https://eloenais.github.io/dashboard_porsche_sales/

> Projeto desenvolvido como exercício de Business Intelligence, combinando tratamento de dados, definição de perguntas de negócio, análise exploratória e geração de uma interface analítica em HTML.

---

## 🎯 Objetivo do projeto

O objetivo da dashboard é transformar uma base de vendas em informações que possam apoiar decisões comerciais.

Em vez de simplesmente apresentar números, o projeto foi estruturado a partir de três perguntas de negócio:

1. **Quais modelos geram mais receita e quais apresentam maior ticket médio?**
2. **Como as vendas e a receita se distribuem entre Estados e Cidades?**
3. **Qual é a preferência de método de pagamento e como ela se relaciona com o ano do veículo e a faixa de preço?**

A ideia é sair do "quanto vendemos?" e chegar ao **"o que esses dados podem nos dizer sobre o negócio?"**.

---

# 📊 Perguntas de negócio

## 1. Qual modelo gera mais receita e qual entrega o maior ticket médio?

### Por que essa pergunta importa?

Ela permite identificar diferentes comportamentos dentro do portfólio:

- modelos que funcionam como **carros-chefe**, combinando maior volume e receita;
- modelos de **alto valor e menor volume**, que podem representar nichos específicos;
- diferenças entre volume de vendas e valor médio por venda.

Um modelo pode vender mais unidades sem necessariamente possuir o maior ticket médio. Essa distinção é importante para evitar que volume seja confundido com valor.

### Ação de negócio

Os resultados podem apoiar decisões como:

- ajuste de estoque;
- definição de foco de marketing;
- estratégias comerciais por modelo;
- direcionamento de incentivos para a equipe de vendas;
- identificação de modelos de maior valor agregado.

---

## 2. Como as vendas e a receita total se distribuem entre Estados e Cidades?

### Por que essa pergunta importa?

A análise geográfica ajuda a identificar mercados com maior concentração de vendas e receita, permitindo observar diferenças entre localidades.

Ela pode revelar:

- mercados mais maduros;
- regiões com maior concentração de receita;
- cidades com maior volume;
- possíveis mercados em expansão.

### Ação de negócio

Essas informações podem apoiar decisões relacionadas a:

- abertura de novas concessionárias;
- expansão de pontos de atendimento técnico;
- realização de eventos e experiências da marca;
- priorização de investimentos comerciais e regionais.

---

## 3. Qual é a preferência de método de pagamento e como ela se relaciona com o ano do veículo e a faixa de preço?

### Por que essa pergunta importa?

O método de pagamento pode ajudar a compreender o **perfil financeiro das compras**.

Além disso, veículos de diferentes anos e faixas de preço podem apresentar comportamentos de pagamento distintos. Cruzar essas variáveis permite observar padrões que não aparecem quando cada informação é analisada isoladamente.

### Ação de negócio

Os resultados podem apoiar decisões como:

- negociação de melhores condições com parceiros financeiros;
- criação de campanhas promocionais direcionadas;
- definição de condições de financiamento;
- identificação de faixas de preço com maior utilização de cada método de pagamento.

---

# 🧹 Tratamento da base de dados

Antes de utilizar a base na construção da dashboard, foram removidas informações brutas e potencialmente sigilosas.

### Dados removidos

Foram retiradas informações pessoais e outros dados sensíveis da base original, mantendo apenas as informações necessárias para a análise.

Os campos utilizados no projeto estão em formato **sanitizado**, preservando a estrutura necessária para a construção da análise sem expor dados pessoais.

### Padronização

Também foi necessário realizar tratamento de tipos de dados.

As seguintes colunas foram convertidas/formata­das para valores numéricos:

- `ModelYearSanitized`
- `SalesPriceSanitized`
- `VehicleMileageSanitized`

Esse tratamento foi importante porque valores numéricos armazenados como texto podem provocar erros ou comportamentos inesperados durante os cálculos e filtros da dashboard.

O objetivo foi garantir que:

- anos fossem tratados como números;
- preços pudessem ser utilizados em somas, médias e agrupamentos;
- quilometragem pudesse ser utilizada em análises quantitativas.

---

# 🤖 Uso de IA no desenvolvimento

## Prompt inicial

A dashboard foi construída a partir de um prompt orientado às necessidades de negócio:

> **"Utilizando o recurso Canvas, renderize uma dashboard em HTML ao lado.**
>
> **Indicadores de topo**
> - Receita total
> - Total de vendas
> - Modelo líder (carro que mais vendeu)
> - Ano dominante
>
> **Filtros**
> - Porsche Model
> - City
> - Model Year
> - Pay Method
>
> **Perguntas de negócio e KPIs**
> - Qual modelo gera mais receita e qual entrega o maior ticket médio?
> - Como as vendas e a receita total se distribuem entre Estados e Cidades?
> - Qual a preferência de método de pagamento (Financiamento, À vista, Pix/Transferência) cruzada com o ano do veículo ou faixa de preço?
>
> **UI/UX**
>
> Utilizar como referência visual o site oficial da Porsche Brasil:
> https://www.porsche.com/brazil/pt/"

## 🔄 Evolução até a versão final

O prompt foi refinado durante o desenvolvimento para transformar a dashboard de uma simples visualização de dados em uma interface mais orientada à análise executiva.

### Cabeçalho

Inicialmente:

**Sales Intelligence**

*Performance comercial · base sanitizada*

Foi alterado para:

**Performance comercial**

*Dashboard executivo para identificar quais modelos lideram por cidade, receita, ticket médio e comportamento de pagamento.*

A mudança tornou mais explícito o objetivo da dashboard.

### Visualização

Um dos gráficos também foi alterado para um **gráfico de pizza**, aplicado ao mix de métodos de pagamento, pois a leitura de participação percentual é mais natural nesse contexto.

### Experiência analítica

Os filtros foram mantidos como elementos centrais da dashboard, fazendo com que os KPIs e visualizações sejam recalculados de acordo com a seleção do usuário.

Assim, a dashboard funciona como uma ferramenta exploratória, e não apenas como um relatório estático.

---

# 🧠 ChatGPT, Canvas ou agente?

O projeto foi desenvolvido utilizando **ChatGPT**, mas a implementação final foi feita diretamente em **HTML, CSS e JavaScript**.

O recurso Canvas solicitado inicialmente estava indisponível neste ambiente como ferramenta de execução. Por isso, a solução foi adaptada para gerar diretamente um arquivo HTML funcional.

Na prática, o resultado preservou o objetivo original:

- interface interativa;
- filtros funcionais;
- KPIs dinâmicos;
- gráficos;
- análise por modelo;
- análise geográfica;
- análise de métodos de pagamento;
- layout responsivo.

A escolha pelo HTML também trouxe uma vantagem: o resultado final pôde ser publicado diretamente no **GitHub Pages**, tornando a dashboard acessível por uma URL pública.

---

# 🎨 UI/UX

A identidade visual foi inspirada na linguagem visual da Porsche Brasil, priorizando:

- fundo escuro;
- alto contraste;
- vermelho como cor de destaque;
- tipografia limpa;
- grandes números para KPIs;
- bordas discretas;
- organização modular;
- bastante espaço visual;
- aparência premium e minimalista.

A intenção não foi reproduzir o site da Porsche, mas utilizá-lo como **referência de direção estética**.

---

# 🔎 Evidência de funcionamento dos filtros

O exemplo abaixo demonstra a dashboard após a aplicação do filtro **Porsche Model → Cayenne Coupe**.

O filtro altera os indicadores e visualizações para refletir somente os registros selecionados.

![Dashboard com filtro aplicado](assets/dashboard-filtros.png)

Neste exemplo, a seleção resulta em:

- **4 vendas**
- **R$ 436.250 de receita**
- **Cayenne Coupe como modelo líder**
- atualização da distribuição geográfica;
- atualização do ticket médio;
- atualização dos demais componentes dependentes do conjunto filtrado.

Isso demonstra que os filtros não são apenas elementos visuais: eles modificam efetivamente o conjunto de dados utilizado pelos indicadores.

---

# 🛠️ Tecnologias utilizadas

- **HTML5**
- **CSS3**
- **JavaScript**
- **Python / Pandas** — preparação e inspeção da base
- **GitHub Pages** — publicação
- **ChatGPT** — apoio na análise, estruturação e desenvolvimento da solução

---

# 📁 Estrutura do projeto

```text
dashboard_porsche_sales/
│
├── index.html
├── assets/
│   └── dashboard-filtros.png
└── README.md
```

---

# 🚀 Publicação

A dashboard está hospedada através do GitHub Pages:

**https://eloenais.github.io/dashboard_porsche_sales/**

---

# 📌 Considerações

Este projeto tem finalidade **educacional e demonstrativa**.

A base utilizada foi previamente sanitizada e não representa uma exposição de dados pessoais ou sigilosos.

Os insights apresentados devem ser interpretados dentro do contexto e das limitações da base utilizada. Uma aplicação real de BI poderia incorporar outras dimensões, como margem, custo, estoque, vendedor, região comercial, período da venda e histórico temporal.

---

## 👤 Autor

**Eloenai da Silva Cardoso**

Projeto desenvolvido como estudo prático de **Business Intelligence, análise de dados e visualização de informações**.
"""
