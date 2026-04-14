## Avaliação e Métricas

### Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

A avaliação do Finny foi realizada por meio de testes estruturados, simulando interações reais com base nos dados da pasta data, além de validações manuais das respostas geradas.
Os testes consideram o perfil de um cliente fictício (João Silva), garantindo que as respostas estejam alinhadas ao contexto fornecido.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu corretamente com base nos dados | Perguntar gastos e receber valores coerentes |
| **Segurança** | O agente evita inventar informações | Perguntar algo fora do contexto e ele admitir |
| **Coerência** | A resposta faz sentido para o perfil do usuário | Sugerir investimento adequado ao perfil moderado |


---

### Exemplos de Cenários de Teste

#### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Soma dos valores da categoria "alimentação" no `transacoes.csv`
- **Resultado:** [x] Correto  [ ] Incorreto

#### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Sugestão compatível com perfil moderado e objetivo de reserva (ex: Tesouro Selic ou CDB)
- **Resultado:** [x] Correto  [ ] Incorreto

#### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** O agente informa que só trata de finanças
- **Resultado:** [x] Correto  [ ] Incorreto

#### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o produto XYZ?"
- **Resposta esperada:** O agente admite que não possui essa informação
- **Resultado:** [x] Correto  [ ] Incorreto

---

### Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- O agente manteve respostas coerentes com o perfil do usuário
- Não houve geração de informações inexistentes (boa segurança)
- As respostas foram claras e acessíveis
- O uso de dados estruturados melhorou a qualidade das análises
- O comportamento seguiu corretamente as regras do prompt

**O que pode melhorar:**
- Melhorar a precisão na soma de categorias específicas
- Tornar os insights mais detalhados (ex: comparações mensais)
- Adicionar memória de curto prazo entre interações
- Criar respostas mais personalizadas com base no histórico de atendimento

---

### Métricas Avançadas (Opcional)

Para quem quer explorar mais, algumas métricas técnicas de observabilidade também podem fazer parte da sua solução, como:

- Tempo de resposta (latência do modelo local)
- Consumo de recursos da máquina
- Logs de interações para análise de comportamento
- Taxa de erros ou respostas inconclusivas

Ferramentas como LangWatch e LangFuse podem ser integradas futuramente para observabilidade mais avançada.

Ferramentas especializadas em LLMs, como [LangWatch](https://langwatch.ai/) e [LangFuse](https://langfuse.com/), são exemplos que podem ajudar nesse monitoramento. Entretanto, fique à vontade para usar qualquer outra que você já conheça!
