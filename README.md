<div align="center"> 
<img width="330" height="138" alt="Group 1 - GAPI branco" src="https://github.com/user-attachments/assets/882f3f99-aedd-48e8-b57c-7fc8760660d9" />


<b>  Instituto Federal Catarinense – Campus Videira</b>  

<b>Autores: João Paulo Kowalski, Julia Luzzi Baldissera, Samuel Castilho Pereira</b>

 </div>



## 1. Plano de Projeto

**Objetivo.** Desenvolver o GAPI, plataforma web que centraliza o ciclo de vida das portarias do IFC Videira: solicitação, elaboração, validação, aprovação, assinatura, publicação, acompanhamento, encerramento e arquivamento.

**Justificativa.** Hoje o controle é feito por planilhas e documentos manuais, o que dificulta rastreabilidade, auditoria e consulta pública, além de gerar retrabalho e inconsistências.

**Escopo (dentro).** Solicitação online; elaboração e edição digital; vínculo com memorandos; aprovação e assinatura eletrônica; controle de vigência; notificações; consulta pública; relatórios; histórico e auditoria; consulta/integração com o SIPAC.

**Fora do escopo (nesta versão).** Substituição do SIPAC; envio automático ao Diário Oficial; assinatura com certificado ICP-Brasil (a definir, ver questões em aberto).

**Partes interessadas.** Direção Geral (DG), DAP, DEPE, Gabinete Institucional (principal operador), servidores e público externo.

**Equipe.** João Paulo Kowalski, Julia Luzzi Baldissera e Samuel Castilho Pereira. Orientação: professor Tiago L. Gonçalves.

**Fases e cronograma sugerido**

| Fase | Entregas | Duração |
| --- | --- | --- |
| 1. Iniciação | Plano, EAP, mapeamento de talentos | 1 semana |
| 2. Requisitos | RF/RNF, regras de negócio, critérios de aceitação, casos de uso | 2 semanas |
| 3. Design | Modelagem do banco, arquitetura, protótipo navegável, landing page | 2 semanas |
| 4. Desenvolvimento | Backend, frontend, integração SIPAC | 6 semanas |
| 5. Testes | Testes funcionais, validação com Gabinete | 2 semanas |
| 6. Implantação | Deploy, treinamento, documentação | 1 semana |

**Riscos e mitigação**

| Risco | Probabilidade | Mitigação |
| --- | --- | --- |
| Dependência da integração com o SIPAC | Alta | Começar por consulta de dados e prever importação manual (CSV) como contingência |
| Migração de portarias históricas | Média | Importação em lote com validação e relatório de inconsistências |
| Resistência/treinamento de usuários | Média | Treinamento curto e manual do usuário por perfil |
| Indefinição de autenticação e assinatura | Média | Decidir cedo com a TI do campus; isolar em módulo próprio |

**Comunicação.** Reunião semanal da equipe, validação quinzenal com o Gabinete, repositório Git com issues por requisito.

## 2. EAP do Projeto

1. **GAPI**
   1. **Gestão do projeto**
      1. Plano de projeto
      2. EAP
      3. Mapeamento de talentos
      4. Acompanhamento e relatórios de status
   2. **Requisitos e análise**
      1. Levantamento com o Gabinete
      2. Requisitos funcionais e não funcionais
      3. Regras de negócio
      4. Critérios de aceitação
      5. Casos de uso
   3. **Projeto (design)**
      1. Modelagem do banco de dados
      2. Arquitetura do sistema
      3. Protótipo funcional e navegável
      4. Landing page de apresentação
   4. **Desenvolvimento**
      1. Backend: autenticação e perfis
      2. Backend: cadastros (servidores, departamentos, memorandos, usuários)
      3. Backend: portarias e fluxo de estados
      4. Backend: auditoria, notificações e vigência
      5. Backend: relatórios
      6. Frontend: telas de acesso (login, recuperação de senha, home)
      7. Frontend: solicitações, elaboração e aprovação
      8. Frontend: consulta pública e relatórios
      9. Integração com SIPAC
   5. **Testes e validação**
      1. Testes unitários e de integração
      2. Testes de aceitação com usuários
      3. Correções
   6. **Implantação**
      1. Migração de dados históricos
      2. Publicação em produção
      3. Treinamento e manual do usuário
      4. Encerramento do projeto

## 3. Mapeamento de Talentos e Habilidades

Tabela inicial para a equipe completar com as competências reais (1 = básico, 5 = avançado).

| Membro | Papel sugerido | Backend | Frontend | Banco de dados | UI/UX | Documentação | Gestão |
| --- | --- | :---: | :---: | :---: | :---: | :---: | :---: |
| **João Paulo Kowalski** | Backend | 4 | 2 | 4 | 2 | 3 | 4 |
| **Julia Luzzi Baldissera** | UI/UX & Frontend | 2 | 4 | 2 | 4 | 4 | 3 |
| **Samuel Castilho Pereira** | Fullstack & Documentação | 3 | 3 | 3 | 3 | 4 | 3 |

**Papéis a distribuir:** Gerente de projeto / analista de requisitos; Desenvolvedor backend e banco de dados; Desenvolvedor frontend e designer de interface.

**Lacunas a observar:** integração com SIPAC, segurança e auditoria, e conhecimento do rito de portarias (suprir com apoio do Gabinete).

## 4. Critérios de Aceitação do Projeto

**Critérios gerais**

- Todos os requisitos funcionais de prioridade alta implementados e testados.
- Fluxo completo (Solicitação → Arquivamento) executável de ponta a ponta sem intervenção manual fora do sistema.
- Aprovado pelo Gabinete Institucional em teste de aceitação com dados reais ou simulados.
- Documentação entregue: plano, requisitos, modelagem, protótipo, manual do usuário.

**Critérios por funcionalidade**

| Funcionalidade | Aceita quando |
| --- | --- |
| Login | Usuário válido acessa conforme seu perfil; credencial inválida exibe erro; após 5 falhas a conta é bloqueada temporariamente |
| Recuperação de senha | Link enviado ao e-mail cadastrado expira em até 1 hora e permite definir nova senha |
| Solicitação | Qualquer servidor autenticado registra solicitação com descrição e prioridade e acompanha seu status |
| Elaboração | Gabinete cria portaria com número, título, texto e assinante; sem esses campos o sistema impede o salvamento |
| Aprovação e assinatura | Somente Diretor/Reitor aprova, assina e revoga; outros perfis não visualizam essas ações |
| Publicação | Só é possível publicar portaria aprovada; portaria publicada aparece na consulta pública |
| Vigência e alertas | Portarias a vencer em 30 dias geram notificação ao Gabinete |
| Auditoria | Toda alteração registra autor, data/hora e valor anterior/novo |
| Relatórios | Os cinco relatórios são gerados com filtros por período e exportados em PDF |
| Consulta pública | Visitante sem login pesquisa por número, título, tipo e período |
| Desempenho | Páginas principais respondem em até 3 s com 50 usuários simultâneos |

## 5. Requisitos Funcionais e Não Funcionais

### Requisitos funcionais

| ID | Requisito | Prioridade |
| --- | --- | --- |
| RF01 | Autenticar usuários com login e senha | Alta |
| RF02 | Recuperar senha por e-mail | Alta |
| RF03 | Controlar acesso por perfil (Servidor, Gabinete, Diretor/Reitor, Público) | Alta |
| RF04 | Cadastrar e manter servidores, departamentos, usuários e memorandos | Alta |
| RF05 | Registrar solicitação de portaria (solicitante, data, descrição, prioridade) | Alta |
| RF06 | Acompanhar status das solicitações | Alta |
| RF07 | Elaborar e editar portarias (número, título, tipo, texto, objetivo, assinante) | Alta |
| RF08 | Vincular uma ou mais portarias a memorandos e anexos | Média |
| RF09 | Aprovar, assinar e revogar portarias | Alta |
| RF10 | Gerenciar os estados da portaria (Solicitada a Arquivada) | Alta |
| RF11 | Publicar portarias e disponibilizar consulta pública | Alta |
| RF12 | Controlar vigência e encerrar portarias vencidas | Alta |
| RF13 | Retificar portarias mantendo versão anterior | Média |
| RF14 | Emitir notificações (vencimento, inconsistências, alterações, designações, revogações, retificações) | Média |
| RF15 | Gerar relatórios (portarias, solicitações, acompanhamento, por servidor, por categoria) | Média |
| RF16 | Registrar histórico e auditoria de todas as alterações | Alta |
| RF17 | Consultar e importar portarias antigas do SIPAC e disponibilizar as publicadas | Média |
| RF18 | Gerenciar tipos de portaria (Administrativa, Normativa, Fiscalização de Contrato, Resolução, outros) | Baixa |

### Requisitos não funcionais

| ID | Categoria | Requisito |
| --- | --- | --- |
| RNF01 | Segurança | Senhas armazenadas com hash forte (bcrypt/argon2); tráfego via HTTPS |
| RNF02 | Segurança | Proteção de dados sensíveis (CPF) conforme a LGPD |
| RNF03 | Segurança | Controle de acesso por perfil em todas as rotas e ações |
| RNF04 | Integridade | Documentos publicados imutáveis; alterações só por retificação com versionamento |
| RNF05 | Disponibilidade | Disponibilidade mínima de 99% em horário administrativo |
| RNF06 | Desempenho | Resposta de até 3 s nas operações comuns |
| RNF07 | Usabilidade | Interface responsiva (desktop e mobile) e acessível (WCAG 2.1 AA) |
| RNF08 | Manutenibilidade | Código versionado em Git, documentado e com testes automatizados |
| RNF09 | Portabilidade | Compatível com Chrome, Firefox e Edge atuais |
| RNF10 | Interoperabilidade | Integração com SIPAC via API ou importação estruturada |
| RNF11 | Auditoria | Logs imutáveis com retenção definida pela política institucional |
| RNF12 | Backup | Backup diário com restauração testada |

## 6. Regras de Negócio

| ID | Regra |
| --- | --- |
| RN01 | Qualquer servidor pode solicitar uma portaria. |
| RN02 | Toda portaria deve ter número identificador, título, texto e assinante. |
| RN03 | Somente Reitores e Diretores podem aprovar e assinar portarias. |
| RN04 | Uma portaria pode estar vinculada a um ou mais memorandos. |
| RN05 | A publicação só ocorre após a aprovação. |
| RN06 | Portarias de resolução seguem os procedimentos de publicação do Diário Oficial. |
| RN07 | Todas as alterações mantêm histórico de auditoria. |
| RN08 | O sistema registra quem realizou cada alteração. |
| RN09 | O sistema permite consulta pública das portarias publicadas. |
| RN10 | O sistema controla a vigência das portarias. |
| RN11 *(sugerida)* | O número da portaria é único e sequencial por ano e não é reutilizado, mesmo se revogada. |
| RN12 *(sugerida)* | Somente o Gabinete elabora e edita portarias; o texto fica bloqueado após a aprovação. |
| RN13 *(sugerida)* | Transições de estado só ocorrem na ordem do fluxo: Solicitada, Em elaboração, Aguardando aprovação, Aprovada, Publicada, Vigente, Encerrada, Arquivada. Retificada e Revogada podem ocorrer após a publicação. |
| RN14 *(sugerida)* | Portaria revogada permanece visível na consulta pública, identificada como revogada. |
| RN15 *(sugerida)* | A data de vigência final não pode ser anterior à data de publicação. |
| RN16 *(sugerida)* | Servidores inativos não podem ser designados em novas portarias. |

As regras RN11 a RN16 são sugestões nossas e devem ser validadas com o Gabinete.


<div align="center"> 
 
## Interfaces do Sistema
[![My Skills](https://skillicons.dev/icons?i=figma&theme=dark)](https://skillicons.dev)




### Login 

<img width="876" height="601" alt="image" src="https://github.com/user-attachments/assets/1dd679fe-3a77-4e82-b4de-3605121bd487" />#

---

### Esqueci Minha Senha

<img width="879" height="601" alt="image" src="https://github.com/user-attachments/assets/d48f2020-41fa-4087-a74c-a1b772753ee5" />

---

### Home

<img width="565" height="632" alt="image" src="https://github.com/user-attachments/assets/533efa34-c39a-4c1a-9163-d4c65556a1fd" />

---

### 8. Prototipação Funcional e Navegável

Protótipo com navegação entre as telas: [Abrir no Figma](https://www.figma.com/design/98fsUNQWJA50YcEdtiwYZJ/Princ%C3%ADpios-do-UI-Design?node-id=7-1405&t=u8BwYbM4Vpa56AZ1-1)

---

### 9. Landing page de Apresentação

<img width="672" height="754" alt="image" src="https://github.com/user-attachments/assets/e75a10a7-0b9d-4648-8448-026af03774c8" />
 </div>
