
# 📄 Estudo de Caso: O Desafio Logístico da Pharma Nordeste

## 1. Contexto do Negócio

A **Pharma Nordeste** é uma rede de farmácias em expansão, operando 108 unidades distribuídas entre capitais e cidades do interior. A empresa enfrenta uma "crise de crescimento": embora o faturamento esteja ativo, a operação logística está ineficiente.

A diretoria percebeu que, enquanto algumas filiais no interior descartam produtos vencidos, grandes unidades nas capitais sofrem com a falta de medicamentos essenciais. Além disso, o transporte de produtos sensíveis (insulinas e vacinas) tem gerado prejuízos desconhecidos.

**O Cenário de Dados:**
A empresa passou por uma migração de sistemas recente, portanto, **só estão disponíveis dados confiáveis referentes ao 2º Semestre de 2025 (Julho a Dezembro)**. O desafio é utilizar esse curto período histórico para tomar decisões imediatas de correção de rota para o início de 2026.

---

## 2. O Problema Central

**"Como otimizar a cadeia de suprimentos para garantir que o medicamento certo esteja na loja certa, na quantidade adequada e em perfeitas condições, minimizando perdas operacionais?"**

---

## 3. Perguntas de Negócio (Desafios a Resolver)

Abaixo estão os 5 pilares estratégicos que a diretoria precisa responder através dos dados disponíveis:

### Pilar A: Eficiência de Alocação e Estoque (Transshipment)

*A empresa suspeita que a distribuição atual é baseada em "empurrar" produtos (Push) e não na demanda real (Pull).*

1. **Desequilíbrio Geográfico:** Existe uma disparidade sistemática entre o volume de remessas enviadas e o volume de vendas efetivadas quando comparamos Lojas de Capital versus Lojas de Interior? Estamos estocando excessivamente o interior com produtos de baixo giro?
2. **Identificação de Oportunidade de Transferência:** É possível identificar "pares de lojas" onde a Loja A possui excesso de estoque de um SKU crítico (com risco de vencer) enquanto a Loja B, na mesma região, sofre ruptura (falta) desse mesmo item, justificando uma transferência lateral entre filiais?
3. **Cobertura de Estoque:** Considerando a média de vendas do último semestre, quais categorias de produtos (Isentos, Controlados, Higiene) possuem uma cobertura de estoque perigosamente baixa (risco de falta em < 15 dias) ou excessivamente alta (dinheiro parado > 90 dias)?

### Pilar B: Qualidade Logística e Perdas

*O transporte no Nordeste enfrenta desafios de temperatura e distância. A empresa precisa estancar o prejuízo.*

4. **Matriz de Perdas Operacionais:** Qual é o impacto financeiro real das avarias logísticas e qual a causa raiz predominante (Temperatura, Transporte ou Vencimento)? Esse prejuízo está concentrado em rotas específicas ou em tipos de produtos específicos (ex: Vacinas)?
5. **Performance da Cadeia de Frio:** Existe uma correlação entre o tempo de entrega (remessas) e o índice de avaria por temperatura em produtos refrigerados? As lojas do interior sofrem desproporcionalmente com esse problema?

### Pilar C: Capacidade e Infraestrutura

*Há relatos de gerentes recusando recebimento de mercadoria por falta de espaço físico.*

6. **Saturação de Capacidade:** O volume de estoque enviado para as farmácias é compatível com o perfil físico da loja (m² e capacidade de geladeira)? Existem lojas operando acima da capacidade de armazenamento de controlados, gerando riscos de segurança ou recusa de recebimento?
7. **Adequação do Mix de Produtos:** O sortimento de produtos (SKUs) enviados para lojas com perfil "Aeroporto" ou "Shopping" está condizente com o perfil de venda rápido e espaço limitado, ou estamos enviando itens de "bairro" que ocupam espaço desnecessário?

### Pilar D: Gestão de Validade (Shelf-Life)

*O risco de "bomba relógio" de produtos vencendo nas prateleiras.*

8. **Risco de Obsolescência:** Com base nos lotes atuais e suas datas de validade, qual é o valor financeiro em risco de vencimento para os próximos 3 meses? Esse risco está concentrado em algum fabricante ou categoria específica?
9. **Giro vs. Validade:** Estamos recebendo lotes com validade curta ("short shelf-life") para produtos que têm giro lento? Como cruzar a data de entrada do lote com a velocidade de venda para prever a perda antes que ela aconteça?

### Pilar E: Planejamento de Demanda (Curto Prazo)

*Preparação para o próximo ciclo com base nos dados recentes.*

10. **Sazonalidade e Reposição Imediata:** Analisando a curva de vendas de Julho a Dezembro, quais medicamentos apresentaram picos de demanda que não foram acompanhados pela reposição de remessas? Como ajustar o pedido de compra para evitar que isso se repita no início do próximo ano?

---

### Resumo Técnico para o Analista de Dados

Para responder a essas perguntas, você precisará cruzar as seguintes fontes:

* **Vendas e Estoque:** Para calcular o giro e a cobertura.
* **Capacidade e Distribuição:** Para verificar se o estoque cabe na loja.
* **Remessas e Ocorrências:** Para medir a eficiência do transporte e as perdas.
* **Lotes e Validade:** Para prever perdas financeiras futuras.
