# Documento de Visão

1. ## **Introdução**

Este documento fornece uma visão abrangente do produto a ser desenvolvido, trazendo a ideia geral e o propósito do mesmo. Descreve o problema a ser resolvido, uma possível solução e as principais funcionalidades do produto, visando estabelecer expectativas e reduzir os riscos do projeto.

### 1.1. **_Escopo e Alinhamento Estratégico_**

Desenvolver 4 microsserviços, sendo eles:
- Interface de Usuário (frontend da aplicação);
- Microsservicço de Usuário (gerenciar dados do usuário);
- Microsserviço de Ações (gerenciar dados das ações);
- Microsservicço de Carteira (gerenciar dados da carteira).

O objetivo é fornecer aos usuários uma visão simplificada de sua carteira de investimentos e trazer insights sobre as ações por meio de uma interface interativa, auxiliando-os na tomada de decisões.

2. ## **Análise de Contexto**

### 2.1 **_Detalhamento da Necessidade_**

#### 2.1.1 **_Descrição do Problema_**

Atualmente, muitas plataformas de investimento disponíveis no mercado não são tão úteis para os investidores iniciantes, dificultando o acesso a informações relevantes e ferramentas de análise. A falta de recursos acessíveis e explicativos torna a tomada de decisão mais desafiadora para esse público-alvo.

#### 2.1.2 **_Impacto_**

Investidores iniciantes enfrentam barreiras significativas ao tentar entrar no mercado de investimentos devido à falta de acesso a ferramentas educacionais, análises acessíveis e dados autoexplicativos.

#### 2.1.3 **_Solução de Sucesso_**

- **Plataforma Gratuita:** A solução proposta visa oferecer uma plataforma de investimento totalmente gratuita.
- **Métricas e Indicadores Explicativos:** A plataforma fornecerá diversas métricas e indicadores de forma clara e explicativa, permitindo que os usuários iniciantes compreendam facilmente o contexto e tomem decisões embasadas.

### 2.2 **_Alternativas_**

#### 2.2.1 **_StatusInvest_**

Pontos Positivos:
- Ampla variedade de informações sobre diferentes ativos financeiros.
- Análises especializadas oferecidas por especialistas em finanças.
- Interface intuitiva e fácil de usar.
- Possibilidade de personalização da carteira de investimentos.
- Diversas ferramentas de análise disponíveis.
- Abundância de dados e informações detalhadas sobre o desempenho dos ativos.

Pontos Negativos:
- Falta de personalização personalizada de acordo com o perfil do usuário.
- Restrição de recursos avançados para usuários gratuitos.
- Ausência de um aplicativo móvel.
- Possíveis inadequações nas recomendações de investimento.
- Dificuldades de navegação devido à quantidade de informações.

#### 2.2.2 **_TradeMap_**

Pontos Positivos:
- Plataforma consolidada e relevante no segmento de investimentos.
- Oferece análises em tempo real de diversos ativos financeiros.
- Facilita o acompanhamento do mercado financeiro através de gráficos, interações com especialistas e notícias atualizadas.
- Possui módulos abrangentes, incluindo consolidação de carteira, análise de fundos, renda fixa e variável, e atualizações periódicas sobre o mercado.
- Conta com mais de 2 milhões de usuários cadastrados e 400 mil visitas mensais.
- Operado pela subsidiária da Valemobi, empresa de soluções tecnológicas para o mercado financeiro, buscando tornar os investimentos mais simples e acessíveis.

Pontos Negativos:
- A versão gratuita oferece funcionalidades limitadas em comparação com os planos pagos.
- Possíveis limitações nas análises e comparações de carteiras na versão gratuita.
- Ausência de especialistas dedicados para avaliar as carteiras dos usuários na versão gratuita.
- Alguns serviços e ferramentas disponíveis apenas nos planos pagos.
- Dependência de parcerias com corretoras para transações no mercado de ações.
- Limitações na personalização e profundidade das análises na versão gratuita.

3. ## **Partes Interessadas**

### 3.1 **_Equipe_**

| Unidade       | Responsável | Envolvimento com o projeto |
|---------------|-------------|----------------------------|
| Documentações | João Victor Batista, Lucas Felipe, Lucas Gomes, Luiz Henrique, Victor Lima, Yan | alto |
| Frontend      | João Victor Batista, Luiz Henrique, Victor Lima | alto |
| Backend       | Lucas Felipe, Lucas Gomes, Yan | alto |

### 3.2 **_Usuários_**

| Tipo de usuário | Representante(s) | Descrição | Responsabilidades | 
| --------------- | ---------------- | --------- | ----------------- |
| Comum | Mateus, Fátima | Jovens, curiosos, ambiciosos e interessados por investimento | Simular uma carteira sem ter perdas reais; Entender métrica e indicadores com significados nas ações; Investir com base nas explicações e simulações das carteiras


### 3.3 **_Necessidades das Partes Interessadas ou Usuários_**

#### 3.3.1 **_Simular uma carteira sem ter perdas reais_**

| Parte(s) Interessada(s) | Motivadores | Situação atual | Solução ideal | 
| --------------- | ---------------- | --------- | ----------------- |
| Investidores iniciantes | Mitigar Riscos Financeiros | Utilização de Ferramentas Manuais, Limitações de Análise | Plataforma intuitiva onde os usuários possam simular investimentos, inserir informações sobre ações e carteiras, e visualizar relatórios detalhados

#### 3.3.2 **_Mostrar métrica e indicadores com significados nas ações_**

| Parte(s) Interessada(s) | Motivadores | Situação atual | Solução ideal | 
| --------------- | ---------------- | --------- | ----------------- |
| Investidores iniciantes | Tomada de Decisão Informada | Dificuldade na Interpretação de Métricas | Facilitar a comparação de métricas e indicadores por meio de textos explicativos para a linguagem do investidor iniciante

## Histórico de versão

| Atividade                          | Responsável   | Data       |
|------------------------------------|---------------|------------|
| Criação do documento | João Victor | 14/04/2024 |
| Adição dos tópicos 1, 2 e 3 | Lucas Gomes | 14/04/2024 |