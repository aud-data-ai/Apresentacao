# SEAUDAD — Trilhas de Auditoria por Análise de Dados

> Repositório do **Serviço de Auditoria por Análise de Dados (SEAUDAD)**, vinculado à Coordenação de Auditoria de TI (COAUDTI). Aqui mantemos código, painéis e documentação das **trilhas de auditoria** — tanto de **testes automatizados** quanto de **automação do processo de auditoria (TAPA)**.

## Sumário
- #visão-geral
- #tipos-de-trilhas
- #principais-trilhas-mantidas
- #ferramentas-e-técnicas
- #arquitetura-e-fluxo-de-trabalho
- #estrutura-do-repositório
- #como-começar
- [Padrões de contribuição](#padrões-de-contribuição)
e-e-conformidade
- #segurança-e-privacidade
- [Roadmap inicial](#roadmap-inicial)
nks-úteis
- [Contato](#contato)
e uso](#licença-e-uso)

al

Adotamos o termo **trilhas de auditoria** para qualquer uso de **Técnicas de Auditoria Assistidas por Computador (TAAC)** dentro da Auditoria do Senado, abrangendo desde testes automatizados em grandes volumes de dados até a automação de etapas do processo de auditoria. Esses artefatos melhoram o planejamento, execução, relatório e acompanhamento, ampliando cobertura de testes, reduzindo esforço manual e aumentando a efetividade.  
Fonte: Guia interno da COAUDTI/SEAUDAD.

## Tipos de trilhas

1. **Trilhas de Testes de Auditoria (testes automatizados)**  
   Testes sistemáticos e contínuos de conformidade, legalidade e eficiência sobre bases corporativas (ex.: folha, suprimento, saúde), usando Python/SQL/Qlik e cruzando dados de sistemas como *Ergon, SIAFI, Arquimedes e bases do TCU*. O objetivo é detectar inconsistências, duplicidades e desvios de cálculo.

2. **Trilhas de Automação do Processo de Auditoria (TAPA)**  
   Fluxos, scripts e painéis que **preparam** os dados (coleta, tratamento, cruzamentos) para agilizar as etapas operacionais e permitir que os times foquem nos testes. Diferentemente dos testes de conformidade, estruturam um **ambiente integrado de auditoria digital** com rastreabilidade.

> Também exploramos **agentes de IA** (NLP, embeddings e IA generativa) para análise de **dados não estruturados** (relatórios, contratos, PDFs, e-mails), com usos como sumarização, extração de cláusulas e classificação temática.

## Principais trilhas mantidas

- **Folha de Pagamento**
- **Suprimento de Fundos**
- **Sistema de Saúde do Senado Federal**
- **Empresas Impedidas**
- **Contratações**

> Essas frentes cobrem rubricas sensíveis (vencimentos, gratificações, pensões, etc.) e processos de alto risco, com ênfase em coerência, integridade e cobertura de população.

## Ferramentas e técnicas

- **Linguagens/ETL**: Python (pandas, polars, etc.), SQL.
- **Visualização/BI**: Qlik Sense (painéis analíticos, indicadores e achados).
- **IA/NLP**: modelos para leitura de documentos, extração de padrões e suporte à análise textual.

**Abordagem determinística (tradicional)**  
Regras e lógicas explícitas (joins, filtros, agregações), com critérios definidos pelos auditores.

**Abordagem baseada em texto (IA)**  
Perguntas/objetivos de leitura orientados pelo auditor (p.ex.: “o contrato prevê cláusula de SLA?”) e interpretação por contexto e conteúdo textual.

## Arquitetura e fluxo de trabalho

1. **Coleta de dados**: conectores/ingestão de *Ergon, SIAFI, Arquimedes, TCU* e outras fontes.
2. **Tratamento e validação**: limpeza, normalização, chaves de vinculação e regras de qualidade.
3. **Regras de auditoria**: lógicas determinísticas para testes automatizados **ou** prompts/parâmetros para IA/NLP em dados não estruturados.
4. **Output**: datasets auditáveis, relatórios de achados e **painéis no Qlik Sense**.
5. **Rastreabilidade**: registros de execução, versão de regras, hashes dos insumos e carimbo de tempo.

## Estrutura do repositório
``
