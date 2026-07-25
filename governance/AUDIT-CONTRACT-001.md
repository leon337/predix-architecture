# AUDIT-CONTRACT-001 — Contrato Padronizado de Auditoria

**Status:** Proposto  
**Versão:** 1.0.0  
**Repositório:** `leon337/predix-architecture`  
**Responsável pela aprovação:** Leon  

## 1. Objetivo

Estabelecer um padrão único para auditorias do ecossistema Predix, permitindo que diferentes agentes analisem GitHub, Linear, Supabase, Vercel e outras plataformas sem produzir relatórios incompatíveis, contraditórios ou difíceis de consolidar.

O contrato garante que todos os auditores:

- trabalhem inicialmente em modo somente leitura;
- diferenciem fatos, inferências, desconhecidos e recomendações;
- registrem evidências verificáveis;
- usem a mesma classificação de risco, confiança e estado;
- entreguem resultados comparáveis e consolidados.

## 2. Escopo inicial

As auditorias iniciais cobrem quatro fontes:

1. GitHub;
2. Linear;
3. Supabase;
4. Vercel.

O Asana será usado posteriormente como camada visual de portfólio, não como substituto do Linear.

## 3. Princípios obrigatórios

### 3.1 Somente leitura

Durante a fase de auditoria, o agente não poderá:

- alterar código;
- criar, editar, fechar ou excluir issues;
- criar ou excluir branches;
- abrir ou mesclar pull requests;
- alterar bancos, autenticação, storage ou funções;
- alterar deployments, domínios ou variáveis;
- reorganizar projetos automaticamente;
- arquivar ou excluir recursos.

Qualquer mudança deverá ser proposta separadamente e depender de aprovação explícita.

### 3.2 Evidência antes de conclusão

Todo achado deve possuir uma evidência verificável. Quando não houver evidência suficiente, o agente deverá classificar o ponto como `DESCONHECIDO` ou `HIPÓTESE`, nunca como fato.

### 3.3 Separação entre observação e recomendação

Cada achado deve distinguir claramente:

- **Fato observado** — informação diretamente confirmada na fonte;
- **Inferência** — conclusão lógica baseada em fatos, mas não explicitamente confirmada;
- **Desconhecido** — informação ausente, inacessível ou não verificável;
- **Recomendação** — ação sugerida pelo auditor.

### 3.4 Sem exclusão durante a auditoria

Nenhum recurso será marcado para exclusão definitiva sem uma etapa posterior de revisão humana. O auditor poderá sugerir `ARQUIVAR`, `CONSOLIDAR`, `REESTRUTURAR` ou `REVISAR`, mas não executar essas ações.

### 3.5 Não interromper projetos ativos

O desenvolvimento do TriView Workspace V1 e de outros projetos ativos não deve ser interrompido por esta auditoria. Achados críticos poderão gerar alertas, mas mudanças serão planejadas em ondas separadas.

## 4. Identificação dos achados

Cada achado receberá um identificador único:

```text
AUD-<FONTE>-<ANO>-<NÚMERO>
```

Exemplos:

```text
AUD-GH-2026-001
AUD-LIN-2026-001
AUD-SUP-2026-001
AUD-VER-2026-001
```

Códigos de fonte:

| Código | Fonte |
|---|---|
| `GH` | GitHub |
| `LIN` | Linear |
| `SUP` | Supabase |
| `VER` | Vercel |
| `ASN` | Asana |
| `ARC` | Arquitetura |

## 5. Estrutura obrigatória de cada achado

```text
Identificador:
Fonte:
Projeto ou recurso:
Categoria:
Tipo de afirmação:
Descrição:
Evidência:
Impacto:
Severidade:
Confiança:
Recomendação:
Dependências:
Estado:
Responsável sugerido:
Data da observação:
```

## 6. Classificações padronizadas

### 6.1 Severidade

| Nível | Definição |
|---|---|
| `CRÍTICA` | Risco imediato de perda de dados, segurança, produção ou bloqueio grave. |
| `ALTA` | Impacto relevante em operação, manutenção, continuidade ou segurança. |
| `MÉDIA` | Problema real, mas sem risco imediato. Deve entrar no planejamento. |
| `BAIXA` | Melhoria de organização, documentação ou consistência. |
| `INFORMATIVA` | Observação sem necessidade direta de correção. |

### 6.2 Confiança

| Nível | Definição |
|---|---|
| `ALTA` | Evidência direta, completa e verificável. |
| `MÉDIA` | Evidência parcial ou inferência fortemente apoiada. |
| `BAIXA` | Hipótese plausível, mas ainda não confirmada. |

### 6.3 Estado do achado

| Estado | Significado |
|---|---|
| `ABERTO` | Achado registrado e ainda não analisado centralmente. |
| `EM_TRIAGEM` | Em análise pelo arquiteto de portfólio. |
| `ACEITO` | Recomendação aceita para planejamento. |
| `ADIADO` | Válido, mas sem prioridade atual. |
| `DESCARTADO` | Não será tratado, com justificativa registrada. |
| `RESOLVIDO` | Ação concluída e verificada. |
| `PRECISA_DE_EVIDÊNCIA` | Informação insuficiente para decisão. |

### 6.4 Classificação do projeto ou recurso

| Classificação | Significado |
|---|---|
| `ATIVO` | Em desenvolvimento ou operação atual. |
| `EM_CONSTRUÇÃO` | Iniciado, mas ainda não utilizável ou publicado. |
| `PAUSADO` | Temporariamente sem atividade. |
| `LEGADO` | Antigo, ainda relevante ou dependência de outro sistema. |
| `CANDIDATO_A_CONSOLIDAÇÃO` | Possível união com outro projeto. |
| `CANDIDATO_A_EXTRAÇÃO` | Contém módulo potencialmente reutilizável. |
| `CANDIDATO_A_ARQUIVAMENTO` | Sem atividade ou valor atual confirmado. |
| `DESCONHECIDO` | Estado não verificável. |

## 7. Categorias de auditoria

Categorias comuns:

- arquitetura;
- documentação;
- segurança;
- dependências;
- integração;
- duplicação;
- dívida técnica;
- governança;
- deploy;
- banco de dados;
- autenticação;
- observabilidade;
- testes;
- versionamento;
- manutenção;
- custos;
- propriedade;
- continuidade.

Cada auditor poderá adicionar subcategorias, mas não substituir as categorias principais.

## 8. Formato do relatório por plataforma

Cada relatório deverá conter, nesta ordem:

1. Resumo executivo;
2. Escopo analisado;
3. Limitações e acessos ausentes;
4. Inventário dos recursos encontrados;
5. Relações entre projetos e plataformas;
6. Achados críticos e altos;
7. Demais achados;
8. Recursos órfãos ou sem associação identificada;
9. Candidatos a engines ou componentes reutilizáveis;
10. Recomendações priorizadas;
11. Informações desconhecidas;
12. Anexo de evidências.

## 9. Regras específicas por fonte

### 9.1 GitHub

Auditar:

- repositórios;
- branches;
- pull requests;
- issues;
- releases;
- documentação;
- stacks;
- dependências;
- CI/CD;
- projetos duplicados;
- código reutilizável;
- candidatos a engines.

Não alterar código nem configuração.

### 9.2 Linear

Auditar:

- equipes;
- projetos;
- iniciativas;
- ciclos;
- issues;
- estados;
- duplicações;
- tarefas paradas;
- associação com repositórios;
- consistência de nomenclatura.

Não fechar, mover ou editar itens.

### 9.3 Supabase

Auditar:

- projetos;
- bancos;
- tabelas;
- migrations;
- autenticação;
- storage;
- funções;
- ambientes;
- integrações;
- projetos órfãos;
- riscos de segurança.

Nunca registrar valores de segredos, tokens ou chaves.

### 9.4 Vercel

Auditar:

- projetos;
- deployments;
- domínios;
- ambientes;
- associações com GitHub;
- builds com falha;
- deployments antigos;
- projetos duplicados;
- configuração de ambientes.

Nunca registrar os valores de variáveis de ambiente.

## 10. Regras de consolidação

O Arquiteto de Portfólio será o único responsável por converter os relatórios independentes em decisões de reorganização.

Os auditores:

- coletam fatos;
- apontam riscos;
- registram recomendações;
- não tomam decisões irreversíveis;
- não reorganizam o ecossistema isoladamente.

Conflitos entre relatórios devem ser registrados, não resolvidos silenciosamente.

## 11. Entregáveis mínimos

Cada auditoria deve produzir:

1. relatório em Markdown;
2. inventário estruturado em YAML ou JSON;
3. lista de achados priorizados;
4. lista de informações desconhecidas;
5. evidências ou referências suficientes para revisão;
6. declaração explícita de que nenhuma alteração foi executada.

## 12. Caminhos de armazenamento

```text
audits/<AAAA-MM-DD>/<fonte>-audit.md
portfolio/<fonte>.yaml
```

Exemplo:

```text
audits/2026-07-25/github-audit.md
portfolio/repositories.yaml
```

## 13. Critérios de conclusão

Uma auditoria será considerada concluída quando:

- o escopo estiver declarado;
- todos os recursos acessíveis tiverem sido inventariados;
- limitações estiverem registradas;
- cada achado possuir severidade, confiança e evidência;
- fatos e inferências estiverem separados;
- nenhuma alteração tiver sido executada;
- o relatório estiver pronto para consolidação.

## 14. Aprovação e mudanças deste contrato

Mudanças neste contrato devem:

1. ser propostas no repositório `predix-architecture`;
2. explicar a motivação;
3. registrar o impacto sobre auditorias já realizadas;
4. incrementar a versão do contrato;
5. depender de aprovação explícita.

---

## Declaração obrigatória do auditor

Todo relatório deverá terminar com:

> Declaro que esta auditoria foi executada em modo somente leitura. Os fatos, inferências, desconhecidos e recomendações foram identificados separadamente. Nenhuma alteração operacional foi realizada durante a coleta das evidências.
