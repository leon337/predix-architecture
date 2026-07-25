# Relatório de Auditoria — <FONTE>

**Execução:** `<AUDRUN-FONTE-AAAA-MM-DD-NNN>`  
**Contrato aplicado:** `AUDIT-CONTRACT-001`  
**Versão do contrato:** `1.1.0`  
**Quality Gate:** `QUALITY-GATE-001`  
**Versão do relatório:** `1.1.0`  
**Data e hora de início:** `<AAAA-MM-DD HH:MM TZ>`  
**Data e hora de conclusão:** `<AAAA-MM-DD HH:MM TZ>`  
**Snapshot da fonte:** `<AAAA-MM-DD HH:MM TZ | SHA | ID | OUTRA REFERÊNCIA>`  
**Auditor:** `<AGENTE/CHAT>`  
**Modo:** Somente leitura nas fontes auditadas  
**Status:** Em elaboração | Em revisão | Em revisão crítica | Remediado | Pronto para consolidação  
**Veredito:** PENDING | PASS | PASS_WITH_NOTES | FAIL | BLOCKED

## 1. Resumo executivo

Descreva de forma objetiva:

- quantidade de recursos encontrados;
- nível de cobertura confirmado;
- principais riscos;
- principais inconsistências;
- principais oportunidades de consolidação ou reutilização;
- limitações relevantes;
- veredito final.

## 2. Escopo analisado

### Incluído

- <ITEM>

### Não incluído

- <ITEM>

### Recorte temporal e profundidade

<DESCRIÇÃO>

### Consultas, filtros ou mecanismos utilizados

| Identificador | Consulta, filtro ou ação de leitura | Objetivo | Resultado resumido |
|---|---|---|---|
| QRY-001 |  |  |  |

## 3. Cobertura e paginação

**Cobertura declarada:** COMPLETA_CONFIRMADA | PARCIAL_DECLARADA | AMOSTRAL | INDETERMINADA

| Recurso | Total informado pela fonte | Total percorrido | Páginas/lotes | Paginação encerrada? | Observação |
|---|---:|---:|---:|---|---|
|  |  |  |  | Sim |  |

Nunca declarar cobertura completa sem confirmar o encerramento da paginação ou do mecanismo equivalente.

## 4. Limitações e acessos ausentes

| Item | Limitação | Impacto na auditoria | Ação necessária | Estado |
|---|---|---|---|---|
| 1 |  |  |  | ABERTO |

## 5. Inventário dos recursos encontrados

| Identificador estável | Nome | Tipo | Estado observado | Projeto relacionado | Última atividade observada | Evidência |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## 6. Relações entre projetos e plataformas

| Origem | Destino | Tipo de relação | Evidência | Confiança | Estado da relação |
|---|---|---|---|---|---|
|  |  |  |  |  | CONFIRMADA | INFERIDA | DESCONHECIDA |

## 7. Achados críticos e altos

### <AUD-FONTE-AAAA-NNN> — <TÍTULO>

- **Execução de auditoria:**
- **Fonte:**
- **Projeto ou recurso:**
- **Categoria:**
- **Tipo de afirmação:** FATO | INFERÊNCIA | HIPÓTESE | DESCONHECIDO | RECOMENDAÇÃO
- **Descrição:**
- **Evidência:**
- **Impacto:**
- **Severidade:** CRÍTICA | ALTA
- **Confiança:** ALTA | MÉDIA | BAIXA
- **Recomendação:**
- **Dependências:**
- **Estado:** ABERTO
- **Responsável sugerido:**
- **Data e hora da observação:**
- **Última verificação:**
- **Achados relacionados:**

## 8. Demais achados

### <AUD-FONTE-AAAA-NNN> — <TÍTULO>

- **Execução de auditoria:**
- **Fonte:**
- **Projeto ou recurso:**
- **Categoria:**
- **Tipo de afirmação:** FATO | INFERÊNCIA | HIPÓTESE | DESCONHECIDO | RECOMENDAÇÃO
- **Descrição:**
- **Evidência:**
- **Impacto:**
- **Severidade:** MÉDIA | BAIXA | INFORMATIVA
- **Confiança:** ALTA | MÉDIA | BAIXA
- **Recomendação:**
- **Dependências:**
- **Estado:** ABERTO
- **Responsável sugerido:**
- **Data e hora da observação:**
- **Última verificação:**
- **Achados relacionados:**

## 9. Recursos órfãos ou sem associação identificada

| Recurso | Fonte | Situação | Evidência | Confiança | Próxima verificação sugerida |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## 10. Candidatos a engines ou componentes reutilizáveis

Classificações permitidas:

- `INTERNO`;
- `CANDIDATO_A_ENGINE`;
- `PRONTO_PARA_EXTRAÇÃO`;
- `ENGINE_EXTRAÍDO`.

| Componente | Local atual | Possíveis consumidores | Maturidade | Classificação | Evidência |
|---|---|---|---|---|---|
|  |  |  |  | CANDIDATO_A_ENGINE |  |

## 11. Recomendações priorizadas

| Prioridade | Recomendação | Motivo | Dependências | Risco de execução | Aprovação necessária |
|---:|---|---|---|---|---|
| 1 |  |  |  |  | Sim |

## 12. Informações desconhecidas

| Pergunta | Classificação | Por que não foi possível confirmar | Fonte necessária | Impacto da incerteza |
|---|---|---|---|---|
|  | NÃO_VERIFICÁVEL |  |  |  |

Classificações permitidas:

- `NÃO_ENCONTRADO_NO_ESCOPO_CONSULTADO`;
- `CONFIRMADO_INEXISTENTE`;
- `NÃO_VERIFICÁVEL`.

## 13. Anexo de evidências

| Evidência | Tipo | Local, ID, SHA ou referência | Coletada em | Consulta associada | Limitações | Achados relacionados |
|---|---|---|---|---|---|---|
| EVD-FONTE-AAAA-001 |  |  |  | QRY-001 |  |  |

Não registrar valores de tokens, chaves, senhas, strings de conexão ou variáveis sensíveis.

## 14. Correlação e duplicidades

| Achado canônico | Achado relacionado | Relação | Justificativa | Ação na consolidação |
|---|---|---|---|---|
|  |  | DUPLICADO |  | Não contabilizar duas vezes |

## 15. Falhas e interrupções da auditoria

| Data e hora | Falha | Tentativas | Impacto | Estado | Próxima ação necessária |
|---|---|---:|---|---|---|
|  |  |  |  | RESOLVIDA |  |

## 16. Inventário estruturado

**Arquivo:** `<portfolio/fonte.yaml | portfolio/fonte.json>`  
**Schema version:** `<VERSÃO>`  
**Validação:** PASS | FAIL | NÃO_EXECUTADA  
**Observações:** <TEXTO>

## 17. Revisão

### Verificações executadas

- [ ] Escopo declarado.
- [ ] Cobertura e paginação declaradas.
- [ ] Limitações registradas.
- [ ] Fatos, inferências, hipóteses, desconhecidos e recomendações separados.
- [ ] Evidências possuem referências e data de coleta.
- [ ] Segredos e dados sensíveis não foram expostos.
- [ ] Inventário estruturado está coerente com o relatório.
- [ ] IDs de achados e evidências são únicos.
- [ ] Nenhuma alteração operacional foi executada.

### Achados da revisão

| ID | Severidade | Descrição | Estado |
|---|---|---|---|
| REV-001 |  |  | ABERTO |

## 18. Revisão crítica

A revisão crítica deve desafiar as conclusões e procurar omissões, falsos positivos, falsos negativos, cobertura incompleta, inferências apresentadas como fatos e recomendações sem evidência.

| ID | Severidade | Questionamento crítico | Evidência | Estado |
|---|---|---|---|---|
| RC-001 |  |  |  | ABERTO |

## 19. Remediação e reverificação

| Achado de origem | Remediação executada | Artefato afetado | Evidência da correção | Resultado da reverificação |
|---|---|---|---|---|
|  |  |  |  | PASS |

## 20. Declaração do auditor

> Declaro que esta auditoria foi executada em modo somente leitura nas fontes auditadas. Os fatos, inferências, hipóteses, desconhecidos e recomendações foram identificados separadamente. Nenhuma alteração operacional foi realizada durante a coleta das evidências. A cobertura, as limitações e o recorte temporal foram declarados, e o relatório passou pelo Quality Gate aplicável.

## 21. Veredito final

**Veredito:** PASS | PASS_WITH_NOTES | FAIL | BLOCKED  
**Achados bloqueantes pendentes:** <QUANTIDADE>  
**Achados altos pendentes:** <QUANTIDADE>  
**Pronto para consolidação:** SIM | NÃO  
**Justificativa:** <TEXTO>