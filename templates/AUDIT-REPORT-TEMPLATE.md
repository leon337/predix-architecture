# Relatório de Auditoria — <FONTE>

**Execução:** `<AUDRUN-FONTE-AAAA-MM-DD-NNN>`  
**Contrato aplicado:** `AUDIT-CONTRACT-001`  
**Versão do contrato:** `1.1.0`  
**Quality Gate:** `QUALITY-GATE-001`  
**Versão do relatório:** `1.1.1`  
**Início:** `<AAAA-MM-DD HH:MM TZ>`  
**Conclusão:** `<AAAA-MM-DD HH:MM TZ>`  
**Snapshot da fonte:** `<DATA/HORA | SHA | ID | OUTRA REFERÊNCIA>`  
**Auditor:** `<AGENTE/CHAT>`  
**Modo:** Somente leitura nas fontes auditadas  
**Status:** Em elaboração | Em revisão | Em revisão crítica | Remediado | Pronto para consolidação  
**Veredito:** PENDING | PASS | PASS_WITH_NOTES | FAIL | BLOCKED

## 1. Resumo executivo

Registrar:

- quantidade de recursos encontrados;
- cobertura confirmada;
- riscos e inconsistências principais;
- oportunidades de consolidação ou reutilização;
- limitações relevantes;
- veredito final.

## 2. Escopo analisado

### Incluído

- <ITEM>

### Não incluído

- <ITEM>

### Recorte temporal e profundidade

<DESCRIÇÃO>

### Consultas, filtros ou ações de leitura

| ID | Consulta, filtro ou ação | Objetivo | Resultado resumido |
|---|---|---|---|
| QRY-001 |  |  |  |

## 3. Cobertura e paginação

**Cobertura:** COMPLETA_CONFIRMADA | PARCIAL_DECLARADA | AMOSTRAL | INDETERMINADA

| Recurso | Total informado | Total percorrido | Páginas/lotes | Paginação encerrada? | Observação |
|---|---:|---:|---:|---|---|
|  |  |  |  | Sim |  |

Nunca declarar cobertura completa sem confirmar o encerramento da paginação ou mecanismo equivalente.

## 4. Limitações e acessos ausentes

| Item | Limitação | Impacto | Ação necessária | Estado |
|---|---|---|---|---|
| 1 |  |  |  | ABERTO |

## 5. Inventário dos recursos

| ID estável | Nome | Tipo | Estado observado | Projeto relacionado | Última atividade | Evidência |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## 6. Relações entre projetos e plataformas

Estados permitidos: `CONFIRMADA`, `INFERIDA` ou `DESCONHECIDA`.

| Origem | Destino | Tipo de relação | Evidência | Confiança | Estado da relação |
|---|---|---|---|---|---|
|  |  |  |  |  | CONFIRMADA |

## 7. Achados críticos e altos

### <AUD-FONTE-AAAA-NNN> — <TÍTULO>

- **Execução:**
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
- **Observado em:**
- **Última verificação:**
- **Achados relacionados:**

## 8. Demais achados

### <AUD-FONTE-AAAA-NNN> — <TÍTULO>

- **Execução:**
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
- **Observado em:**
- **Última verificação:**
- **Achados relacionados:**

## 9. Recursos órfãos

| Recurso | Fonte | Situação | Evidência | Confiança | Próxima verificação |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## 10. Candidatos a engines ou componentes reutilizáveis

Classificações permitidas: `INTERNO`, `CANDIDATO_A_ENGINE`, `PRONTO_PARA_EXTRAÇÃO`, `ENGINE_EXTRAÍDO`.

| Componente | Local atual | Possíveis consumidores | Maturidade | Classificação | Evidência |
|---|---|---|---|---|---|
|  |  |  |  | CANDIDATO_A_ENGINE |  |

## 11. Recomendações priorizadas

| Prioridade | Recomendação | Motivo | Dependências | Risco de execução | Aprovação necessária |
|---:|---|---|---|---|---|
| 1 |  |  |  |  | Sim |

## 12. Informações desconhecidas

Classificações permitidas: `NÃO_ENCONTRADO_NO_ESCOPO_CONSULTADO`, `CONFIRMADO_INEXISTENTE`, `NÃO_VERIFICÁVEL`.

| Pergunta | Classificação | Motivo da incerteza | Fonte necessária | Impacto |
|---|---|---|---|---|
|  | NÃO_VERIFICÁVEL |  |  |  |

## 13. Evidências

| Evidência | Tipo | Local, ID, SHA ou referência | Coletada em | Consulta | Limitações | Achados relacionados |
|---|---|---|---|---|---|---|
| EVD-FONTE-AAAA-001 |  |  |  | QRY-001 |  |  |

Não registrar tokens, chaves, senhas, strings de conexão ou valores de variáveis sensíveis.

## 14. Correlação e duplicidades

| Achado canônico | Achado relacionado | Relação | Justificativa | Ação na consolidação |
|---|---|---|---|---|
|  |  | DUPLICADO |  | Não contabilizar duas vezes |

## 15. Falhas e interrupções

| Data e hora | Falha | Tentativas | Impacto | Estado | Próxima ação |
|---|---|---:|---|---|---|
|  |  |  |  | RESOLVIDA |  |

## 16. Inventário estruturado

**Arquivo:** `<portfolio/fonte.yaml | portfolio/fonte.json>`  
**Schema version:** `<VERSÃO>`  
**Validação:** PASS | FAIL | NÃO_EXECUTADA  
**Observações:** <TEXTO>

## 17. Revisão

- [ ] Escopo declarado.
- [ ] Cobertura e paginação declaradas.
- [ ] Limitações registradas.
- [ ] Tipos de afirmação separados.
- [ ] Evidências possuem referência e data.
- [ ] Segredos não foram expostos.
- [ ] Inventário estruturado está coerente.
- [ ] IDs são únicos.
- [ ] Nenhuma alteração operacional foi executada.

| ID | Severidade | Descrição | Estado |
|---|---|---|---|
| REV-001 |  |  | ABERTO |

## 18. Revisão crítica

Questionar omissões, falsos positivos, falsos negativos, cobertura incompleta, inferências tratadas como fatos e recomendações sem evidência.

| ID | Severidade | Questionamento crítico | Evidência | Estado |
|---|---|---|---|---|
| RC-001 |  |  |  | ABERTO |

## 19. Remediação e reverificação

| Achado de origem | Remediação | Artefato afetado | Evidência da correção | Reverificação |
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