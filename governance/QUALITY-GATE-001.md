# QUALITY-GATE-001 — Fluxo Obrigatório de Qualidade

**Status:** Ativo  
**Versão:** 1.0.0  
**Aplicação:** Todo trabalho executado no ecossistema Predix  
**Responsável pela diretriz:** Leo

## 1. Objetivo

Estabelecer um fluxo permanente para que tarefas não sejam consideradas concluídas imediatamente após a execução. Toda entrega deve passar por revisão, revisão crítica, remediação e verificação final, sem exigir que o usuário retorne apenas para solicitar essas etapas.

## 2. Fluxo obrigatório

```text
EXECUTAR
   ↓
REVISAR
   ↓
REVISAR CRITICAMENTE
   ↓
REMEDIAR ACHADOS
   ↓
VERIFICAR A REMEDIAÇÃO
   ↓
CONCLUIR OU BLOQUEAR COM EVIDÊNCIA
```

Nenhuma tarefa deverá ser declarada concluída antes de atravessar todas as etapas aplicáveis.

## 3. Etapa de execução

A execução deve:

- respeitar o escopo aprovado;
- preservar restrições e decisões anteriores;
- produzir evidências verificáveis;
- evitar alterações não solicitadas;
- registrar arquivos, commits, tarefas ou recursos afetados.

## 4. Revisão

A revisão confirma se a entrega:

- cumpre o objetivo solicitado;
- está completa;
- segue o padrão documental e técnico aplicável;
- não contém erros aparentes;
- preserva compatibilidade com decisões anteriores;
- possui evidências suficientes.

## 5. Revisão crítica

A revisão crítica deve adotar postura adversarial e procurar:

- premissas frágeis ou não comprovadas;
- contradições;
- omissões;
- riscos de segurança, perda de dados ou regressão;
- falhas de recuperação;
- acoplamento desnecessário;
- duplicação;
- estados de erro não tratados;
- conclusões sem evidência;
- divergência entre documentação e execução.

Quando houver outro agente revisor disponível, a revisão crítica deve ser independente. Quando isso não for possível, deve ser executada como uma segunda passagem separada, usando critérios explícitos e sem presumir que a primeira revisão estava correta.

## 6. Remediação automática

Achados encontrados durante revisão ou revisão crítica devem ser corrigidos automaticamente quando:

- a correção permanece dentro do escopo aprovado;
- não é destrutiva nem irreversível;
- não altera produção, dados reais, custos, permissões ou segurança de forma material;
- não exige uma nova decisão de produto ou arquitetura;
- não depende de credenciais ou informações ausentes.

Após a correção, a parte afetada deve ser revisada novamente.

## 7. Quando interromper e solicitar decisão humana

A execução somente deve ser interrompida quando existir pelo menos uma destas condições:

- ação destrutiva ou irreversível;
- merge, deploy em produção ou migração sem autorização aplicável;
- risco de exposição de segredo, credencial ou dado sensível;
- efeito financeiro ou alteração de cobrança;
- mudança material de escopo, produto ou arquitetura;
- conflito entre decisões aprovadas;
- informação essencial ausente que não possa ser obtida com segurança;
- baixa confiança que torne a automação insegura.

A interrupção deve informar exatamente o bloqueio, a evidência e a decisão necessária.

## 8. Classificação dos achados

| Severidade | Definição |
|---|---|
| `BLOQUEANTE` | Impede conclusão segura ou invalida a entrega. |
| `ALTA` | Pode causar falha relevante, regressão, risco operacional ou inconsistência grave. |
| `MÉDIA` | Problema real que deve ser remediado antes ou logo após a entrega. |
| `BAIXA` | Melhoria de clareza, consistência ou manutenção. |
| `INFORMATIVA` | Observação sem correção obrigatória. |

## 9. Vereditos finais

| Veredito | Uso |
|---|---|
| `PASS` | Entrega revisada, criticamente revisada e sem achados pendentes relevantes. |
| `PASS_WITH_NOTES` | Entrega válida, com observações não bloqueantes registradas. |
| `FAIL` | Existe achado bloqueante ou alto não remediado. |
| `BLOCKED` | A conclusão depende de decisão, acesso ou informação externa. |

## 10. Evidências mínimas

A conclusão deve registrar, conforme aplicável:

- o que foi executado;
- o que foi revisado;
- achados da revisão crítica;
- remediações efetuadas;
- validação posterior;
- arquivos, commits, issues, PRs ou recursos afetados;
- veredito final.

## 11. Aplicação a documentos

Para documentos, verificar no mínimo:

- coerência interna;
- terminologia;
- estrutura;
- tabelas e exemplos;
- referências cruzadas;
- versionamento;
- status;
- ausência de ambiguidade operacional.

## 12. Aplicação a software

Para software, verificar no mínimo:

- lint, análise estática e tipos, quando disponíveis;
- testes relevantes;
- build;
- tratamento de erros;
- regressões;
- segurança;
- recuperação;
- logs e observabilidade;
- documentação compatível com o comportamento real.

## 13. Registro da revisão

Entregas relevantes devem possuir um registro em:

```text
reviews/<AAAA-MM-DD>/<IDENTIFICADOR>-review.md
```

O registro deve separar:

1. execução;
2. revisão;
3. revisão crítica;
4. remediação;
5. verificação final;
6. veredito.

## 14. Regra permanente

A ausência de uma solicitação explícita de revisão não dispensa este fluxo. A revisão, a revisão crítica e a remediação fazem parte da própria execução da tarefa.