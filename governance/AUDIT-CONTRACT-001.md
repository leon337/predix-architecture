# AUDIT-CONTRACT-001 — Contrato Padronizado de Auditoria

**Status:** Revisado — pronto para uso controlado  
**Versão:** 1.1.0  
**Repositório:** `leon337/predix-architecture`  
**Responsável pela diretriz:** Leo  
**Quality Gate aplicável:** `QUALITY-GATE-001`

## 1. Objetivo

Estabelecer um padrão único para auditorias do ecossistema Predix, permitindo que diferentes agentes analisem GitHub, Linear, Supabase, Vercel e outras plataformas sem produzir relatórios incompatíveis, contraditórios ou difíceis de consolidar.

O contrato garante que todos os auditores:

- trabalhem inicialmente em modo somente leitura nas fontes auditadas;
- diferenciem fatos, inferências, desconhecidos e recomendações;
- registrem evidências verificáveis e datadas;
- declarem cobertura, paginação, limitações e recorte temporal;
- usem a mesma classificação de risco, confiança e estado;
- entreguem inventários estruturados e resultados comparáveis;
- submetam o relatório a revisão, revisão crítica e remediação antes da consolidação.

## 2. Escopo inicial

As auditorias iniciais cobrem quatro fontes:

1. GitHub;
2. Linear;
3. Supabase;
4. Vercel.

O Asana será usado posteriormente como camada visual de portfólio, não como substituto do Linear.

## 3. Princípios obrigatórios

### 3.1 Somente leitura nas fontes auditadas

Durante a coleta de evidências, o agente não poderá:

- alterar código;
- criar, editar, fechar ou excluir issues;
- criar ou excluir branches;
- abrir ou mesclar pull requests;
- alterar bancos, autenticação, storage ou funções;
- alterar deployments, domínios ou variáveis;
- reorganizar projetos automaticamente;
- arquivar ou excluir recursos.

É permitido escrever exclusivamente os artefatos da auditoria no repositório `predix-architecture`, nos caminhos definidos por este contrato. Essa permissão não autoriza alterações nos sistemas auditados.

Qualquer mudança operacional deverá ser proposta separadamente e depender da autorização aplicável.

### 3.2 Evidência antes de conclusão

Todo achado deve possuir evidência verificável. Quando não houver evidência suficiente, o agente deverá classificar o ponto como `DESCONHECIDO` ou `HIPÓTESE`, nunca como fato.

A ausência de um item durante uma consulta não prova que ele não existe. O auditor deve registrar a diferença entre:

- `NÃO_ENCONTRADO_NO_ESCOPO_CONSULTADO`;
- `CONFIRMADO_INEXISTENTE`;
- `NÃO_VERIFICÁVEL`.

### 3.3 Separação entre observação e recomendação

Cada achado deve distinguir claramente:

- **Fato observado** — informação diretamente confirmada na fonte;
- **Inferência** — conclusão lógica baseada em fatos, mas não explicitamente confirmada;
- **Desconhecido** — informação ausente, inacessível ou não verificável;
- **Hipótese** — explicação provisória que requer validação adicional;
- **Recomendação** — ação sugerida pelo auditor.

### 3.4 Sem exclusão durante a auditoria

Nenhum recurso será marcado para exclusão definitiva sem uma etapa posterior de revisão humana. O auditor poderá sugerir `ARQUIVAR`, `CONSOLIDAR`, `REESTRUTURAR` ou `REVISAR`, mas não executar essas ações.

### 3.5 Não interromper projetos ativos

O desenvolvimento do TriView Workspace V1 e de outros projetos ativos não deve ser interrompido por esta auditoria. Achados críticos poderão gerar alertas, mas mudanças serão planejadas em ondas separadas.

### 3.6 Proteção de dados e segredos

O auditor nunca deve registrar:

- valores de tokens, chaves ou senhas;
- conteúdo de variáveis de ambiente sensíveis;
- dados pessoais desnecessários;
- strings completas de conexão;
- capturas contendo segredos sem redação adequada.

Quando a existência de um segredo ou configuração for relevante, registrar apenas o nome, o tipo, o estado observado e o risco, sem expor o valor.

## 4. Identificação da execução da auditoria

Cada execução receberá um identificador único:

```text
AUDRUN-<FONTE>-<AAAA-MM-DD>-<NNN>
```

Exemplos:

```text
AUDRUN-GH-2026-07-25-001
AUDRUN-LIN-2026-07-25-001
```

A execução deve registrar:

- data e hora de início e fim;
- fonte auditada;
- agente ou chat auditor;
- contrato e versão aplicados;
- recorte temporal;
- consultas ou mecanismos utilizados;
- quantidade de páginas ou lotes percorridos;
- limitações e interrupções;
- snapshot ou referência temporal da fonte.

## 5. Identificação dos achados

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

## 6. Estrutura obrigatória de cada achado

```text
Identificador:
Execução de auditoria:
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
Data e hora da observação:
Última verificação:
Achados relacionados:
```

## 7. Evidências

Cada evidência receberá um identificador:

```text
EVD-<FONTE>-<AAAA>-<NNN>
```

A evidência deve registrar, conforme disponível:

- tipo de fonte;
- recurso ou caminho;
- consulta ou filtro aplicado;
- data e hora da coleta;
- referência estável, ID, SHA, URL interna ou identificador equivalente;
- trecho mínimo necessário;
- limitações;
- achados relacionados.

Evidências voláteis devem informar que representam um snapshot temporal e podem mudar após a coleta.

## 8. Classificações padronizadas

### 8.1 Severidade

| Nível | Definição |
|---|---|
| `CRÍTICA` | Risco imediato de perda de dados, segurança, produção ou bloqueio grave. |
| `ALTA` | Impacto relevante em operação, manutenção, continuidade ou segurança. |
| `MÉDIA` | Problema real, mas sem risco imediato. Deve entrar no planejamento. |
| `BAIXA` | Melhoria de organização, documentação ou consistência. |
| `INFORMATIVA` | Observação sem necessidade direta de correção. |

### 8.2 Confiança

| Nível | Definição |
|---|---|
| `ALTA` | Evidência direta, completa e verificável. |
| `MÉDIA` | Evidência parcial ou inferência fortemente apoiada. |
| `BAIXA` | Hipótese plausível, mas ainda não confirmada. |

### 8.3 Estado do achado

| Estado | Significado |
|---|---|
| `ABERTO` | Achado registrado e ainda não analisado centralmente. |
| `EM_TRIAGEM` | Em análise pelo Arquiteto de Portfólio. |
| `ACEITO` | Recomendação aceita para planejamento. |
| `ADIADO` | Válido, mas sem prioridade atual. |
| `DESCARTADO` | Não será tratado, com justificativa registrada. |
| `RESOLVIDO` | Ação concluída e verificada. |
| `PRECISA_DE_EVIDÊNCIA` | Informação insuficiente para decisão. |
| `DUPLICADO` | Representa o mesmo problema de outro achado canônico. |

### 8.4 Classificação do projeto ou recurso

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

## 9. Categorias de auditoria

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

## 10. Cobertura, paginação e completude

O auditor deve declarar uma das seguintes coberturas:

| Cobertura | Significado |
|---|---|
| `COMPLETA_CONFIRMADA` | Todas as páginas, lotes ou recursos acessíveis foram percorridos e a fonte confirmou o fim da paginação. |
| `PARCIAL_DECLARADA` | Apenas parte do universo foi analisada, com limites registrados. |
| `AMOSTRAL` | Foi analisada uma amostra explicitamente definida. |
| `INDETERMINADA` | A ferramenta ou o acesso não permitiu medir a completude. |

Nunca declarar inventário completo sem confirmar paginação, limites e escopo.

## 11. Formato do relatório por plataforma

Cada relatório deverá conter, nesta ordem:

1. Metadados da execução;
2. Resumo executivo;
3. Escopo analisado;
4. Cobertura, paginação e recorte temporal;
5. Limitações e acessos ausentes;
6. Inventário dos recursos encontrados;
7. Relações entre projetos e plataformas;
8. Achados críticos e altos;
9. Demais achados;
10. Recursos órfãos ou sem associação identificada;
11. Candidatos a engines ou componentes reutilizáveis;
12. Recomendações priorizadas;
13. Informações desconhecidas;
14. Anexo de evidências;
15. Revisão, revisão crítica e remediação;
16. Declaração do auditor;
17. Veredito final.

## 12. Regras específicas por fonte

### 12.1 GitHub

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

Não alterar código nem configuração nos repositórios auditados.

### 12.2 Linear

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

### 12.3 Supabase

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

Nunca registrar valores de segredos, tokens, chaves ou strings de conexão.

### 12.4 Vercel

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

## 13. Correlação e duplicidade

Achados semelhantes entre fontes devem ser relacionados, não fundidos silenciosamente.

Quando houver duplicidade:

- escolher um achado canônico;
- marcar os demais como `DUPLICADO`;
- preservar todas as evidências;
- registrar os identificadores relacionados;
- não somar o mesmo risco várias vezes na consolidação.

Conflitos entre fontes devem permanecer explícitos até a consolidação.

## 14. Falhas, interrupções e condições de parada

O auditor deve interromper a coleta e registrar `BLOCKED` quando ocorrer:

- perda de acesso;
- autenticação expirada;
- paginação inconsistente;
- limite de ferramenta que impeça avaliar cobertura;
- resposta contraditória da fonte;
- risco de expor segredo ou dado sensível;
- necessidade de ação operacional para continuar;
- baixa confiança que possa gerar conclusão enganosa.

Não repetir indefinidamente uma consulta com erro. Registrar tentativas, impacto e próxima ação necessária.

## 15. Inventário estruturado

Além do relatório Markdown, cada auditoria deve produzir inventário YAML ou JSON contendo:

```text
schema_version
run_id
source
snapshot_at
coverage
resources
relationships
findings
unknowns
limitations
```

O inventário deve ser validável e manter IDs estáveis sempre que a fonte fornecer identificadores permanentes.

## 16. Regras de consolidação

O Arquiteto de Portfólio será o único responsável por converter os relatórios independentes em decisões de reorganização.

Os auditores:

- coletam fatos;
- apontam riscos;
- registram recomendações;
- não tomam decisões irreversíveis;
- não reorganizam o ecossistema isoladamente.

Conflitos entre relatórios devem ser registrados, não resolvidos silenciosamente.

## 17. Quality Gate obrigatório

Antes de ser marcado como pronto para consolidação, cada relatório deverá passar pelo `QUALITY-GATE-001`:

1. execução da auditoria;
2. revisão de completude e consistência;
3. revisão crítica adversarial;
4. remediação dos achados internos do relatório;
5. nova verificação;
6. veredito `PASS`, `PASS_WITH_NOTES`, `FAIL` ou `BLOCKED`.

O auditor não precisa aguardar nova solicitação do usuário para executar revisão e remediação não destrutiva dentro do escopo aprovado.

## 18. Entregáveis mínimos

Cada auditoria deve produzir:

1. relatório em Markdown;
2. inventário estruturado em YAML ou JSON;
3. lista de achados priorizados;
4. lista de informações desconhecidas;
5. evidências ou referências suficientes para revisão;
6. declaração explícita de que nenhuma alteração operacional foi executada;
7. registro da revisão crítica e das remediações;
8. veredito final.

## 19. Caminhos de armazenamento

```text
audits/<AAAA-MM-DD>/<fonte>-audit.md
portfolio/<fonte>.yaml
reviews/<AAAA-MM-DD>/<IDENTIFICADOR>-review.md
```

Exemplo:

```text
audits/2026-07-25/github-audit.md
portfolio/repositories.yaml
reviews/2026-07-25/AUDRUN-GH-2026-07-25-001-review.md
```

## 20. Critérios de conclusão

Uma auditoria será considerada concluída quando:

- o escopo estiver declarado;
- a cobertura e a paginação estiverem declaradas;
- todos os recursos dentro do escopo confirmado tiverem sido inventariados;
- limitações estiverem registradas;
- cada achado possuir severidade, confiança e evidência;
- fatos, inferências, hipóteses e desconhecidos estiverem separados;
- nenhuma alteração operacional tiver sido executada;
- o inventário estruturado estiver disponível;
- revisão e revisão crítica tiverem sido executadas;
- achados internos tiverem sido remediados ou registrados como pendentes;
- o relatório possuir veredito final;
- o relatório estiver pronto para consolidação.

## 21. Aprovação e mudanças deste contrato

Mudanças materiais neste contrato devem:

1. ser propostas no repositório `predix-architecture`;
2. explicar a motivação;
3. registrar o impacto sobre auditorias já realizadas;
4. incrementar a versão do contrato;
5. depender de aprovação explícita quando alterarem escopo, autoridade, risco ou responsabilidade.

Correções, clarificações e remediações não materiais podem ser executadas automaticamente pelo fluxo `QUALITY-GATE-001`, desde que sejam registradas e não ampliem autoridade operacional.

---

## Declaração obrigatória do auditor

Todo relatório deverá terminar com:

> Declaro que esta auditoria foi executada em modo somente leitura nas fontes auditadas. Os fatos, inferências, hipóteses, desconhecidos e recomendações foram identificados separadamente. Nenhuma alteração operacional foi realizada durante a coleta das evidências. A cobertura, as limitações e o recorte temporal foram declarados, e o relatório passou pelo Quality Gate aplicável.