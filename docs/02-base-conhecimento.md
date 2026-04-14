## Base de Conhecimento

### Dados Utilizados

| Arquivo | Formato | Para que serve no Finny |
|---------|---------|---------------------|
| `data/historico_atendimento.csv` | CSV | Contextualizar interações anteriores e entender dúvidas recorrentes |
| `data/perfil_investidor.json` | JSON | Definir perfil financeiro do usuário e personalizar orientações |
| `data/produtos_financeiros.json` | JSON | Fornecer contexto sobre opções financeiras e educação básica |
| `data/transacoes.csv` | CSV | Analisar padrão de gastos do usuário e identificar comportamentos financeiros |


---

### Adaptações nos Dados

Foram utilizados arquivos estruturados na pasta data contendo informações simuladas do usuário, como histórico de transações, perfil financeiro e interações anteriores.
Os dados foram mantidos em formato simples (CSV e JSON) para facilitar o processamento pelo modelo local via Ollama, garantindo leveza, clareza e eficiência.
Além disso, os dados foram organizados de forma modular, permitindo fácil manutenção e futuras expansões do sistema.

---

### Estratégia de Integração

#### Como os dados são carregados?

Os arquivos CSV e JSON são carregados a partir da pasta data no início da execução da aplicação e armazenados em memória.
Esses dados são estruturados e preparados para serem utilizados como contexto nas interações com o agente.

#### Como os dados são usados no prompt?

Os dados do usuário são inseridos dinamicamente no contexto do prompt a cada interação.
O agente utiliza essas informações para:

- entender o perfil financeiro do usuário
- analisar padrões de gastos
- contextualizar respostas com base em interações anteriores
- gerar sugestões e insights personalizados

As respostas são sempre limitadas às informações disponíveis, evitando suposições ou inferências incorretas.

---

### Exemplo de Contexto Montado


```
Dados do Usuário:
- Nome: João
- Perfil: Moderado
- Objetivo: Melhorar controle financeiro

Resumo de comportamento:
- Categoria com maior gasto: Alimentação
- Frequência alta de gastos com serviços recorrentes

Últimas transações:
- 01/03: Supermercado - R$ 350
- 02/03: Streaming - R$ 55
- 03/03: Transporte - R$ 40

Histórico de dúvidas:
- "Como economizar no dia a dia?"
- "Vale a pena investir com pouco dinheiro?"

Sugestão inicial:
- Reduzir gastos com alimentação fora de casa
- Avaliar assinaturas recorrentes
...
```
