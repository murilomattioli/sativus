# Especificação Funcional - Sistema Juanita

## 1. Visão Geral do Sistema

O Sistema Juanita é uma plataforma de gestão de terapia com cannabis medicinal que permite o gerenciamento de pacientes, prescrições e consultas. O sistema possui três módulos principais: Dashboard, Pacientes, Prescrições, Agenda, Relatórios, Protocolos e Configurações.

## 2. Arquitetura da Interface

### 2.1 Layout Geral
- **Sidebar de Navegação**: Menu lateral fixo com logo "Sativus" e navegação principal
- **Área de Conteúdo Principal**: Área dinâmica que exibe o conteúdo da seção selecionada
- **Header Contextual**: Cabeçalho com título da seção e ações relevantes

### 2.2 Navegação Principal
A sidebar contém os seguintes itens de menu:
- Dashboard (ícone: gráfico)
- Pacientes (ícone: pessoa)
- Prescrições (ícone: receita)
- Agenda (ícone: calendário)
- Relatórios (ícone: documento)
- Protocolos (ícone: lista)
- Configurações (ícone: engrenagem)

## 3. Módulo Dashboard

### 3.1 Funcionalidades Principais

#### 3.1.1 Cards de Métricas
**Total de Pacientes**
- Valor: 125
- Indicador: +11% vs mês anterior
- Ícone: usuários
- Cor: verde (indicando crescimento positivo)

**Consultas Este Mês**
- Valor: 48
- Indicador: +6% vs mês anterior
- Ícone: calendário
- Cor: azul

**Prescrições Ativas**
- Valor: 89
- Indicador: +15% vs mês anterior
- Ícone: prescrição
- Cor: verde

**Taxa de Melhora**
- Valor: 87%
- Indicador: +3% vs mês anterior
- Ícone: gráfico crescente
- Cor: verde

#### 3.1.2 Seção Ações Rápidas
**Nova Prescrição**
- Botão principal verde
- Texto: "Criar prescrição para paciente"
- Ação: Redireciona para formulário de nova prescrição

**Novo Paciente**
- Ícone: usuário
- Texto: "Cadastrar paciente"
- Ação: Abre modal ou página de cadastro de paciente

**Agendar Consulta**
- Ícone: calendário
- Texto: "Marcar nova consulta"
- Ação: Abre interface de agendamento

**Relatório**
- Ícone: documento
- Texto: "Gerar relatórios"
- Ação: Acessa módulo de relatórios

#### 3.1.3 Atividades Recentes
Lista cronológica de atividades com:
- **Nova prescrição criada**: CBD 5% - 30ml para anedonia (há 2 horas)
- **Consulta realizada**: Consulta do seguimento (há 4 horas)
- **Novo paciente cadastrado**: Aplicação cannabis (há 6 horas)
- **Prescrição renovada**: THC+CBD 1:1 - 30ml (ontem)

Cada item deve mostrar:
- Tipo de atividade
- Detalhes relevantes
- Timestamp relativo
- Status/resultado

#### 3.1.4 Visão Geral dos Tratamentos
Gráfico de barras horizontais mostrando:
- **Ansiedade/Depressão**: 45 casos (36%)
- **Epilepsia**: 32 casos (26%)
- **Dor Crônica**: 28 casos (22%)

Cada barra deve:
- Mostrar número absoluto e percentual
- Ter cores distintas para cada condição
- Ser interativa (hover com detalhes)

### 3.2 Comportamentos Esperados
- Cards de métricas devem atualizar em tempo real
- Indicadores de crescimento devem mudar cor baseado em positivo/negativo
- Ações rápidas devem ter feedback visual ao hover
- Lista de atividades deve ser scrollável
- Gráfico de tratamentos deve ser responsivo

## 4. Módulo Pacientes

### 4.1 Funcionalidades Principais

#### 4.1.1 Header da Seção
- **Título**: "Pacientes"
- **Subtítulo**: "Gerencie informações dos seus pacientes"
- **Botão Primário**: "Novo Paciente" (verde, canto superior direito)

#### 4.1.2 Barra de Filtros e Busca
- **Campo de Busca**: "Buscar pacientes..." com ícone de lupa
- **Botão Filtros**: Ícone de filtro com texto "Filtros"

#### 4.1.3 Tabela de Pacientes
**Colunas da Tabela:**
- **Nome**: Nome completo do paciente
- **Idade**: Idade em anos
- **Condição**: Condição médica principal
- **Última Consulta**: Data da última consulta (formato DD/MM/AAAA)
- **Status**: Badge colorido (Ativo/Inativo)
- **Prescrição Atual**: Medicação atual prescrita
- **Ações**: Menu de três pontos para ações

**Dados de Exemplo:**
1. Maria Silva, 45 anos, Ansiedade, 15/01/2024, Ativo, CBD 5% - 30ml
2. João Santos, 62 anos, Epilepsia, 12/01/2024, Ativo, THC+CBD 1:1 - 30ml
3. Ana Costa, 38 anos, Dor Crônica, 10/01/2024, Ativo, CBD 10% - 15ml
4. Carlos Lima, 55 anos, Insônia, 08/01/2024, Inativo, CBD 2.5% - 10ml

#### 4.1.4 Cards de Resumo
**Pacientes Ativos**
- Valor: 3
- Cor: verde

**Consultas Este Mês**
- Valor: 24
- Cor: azul

**Taxa de Adesão**
- Valor: 92%
- Cor: verde

### 4.2 Funcionalidades de Interação

#### 4.2.1 Busca e Filtros
- Busca em tempo real por nome, condição ou prescrição
- Filtros por status (Ativo/Inativo)
- Filtros por condição médica
- Filtros por faixa etária
- Filtros por data da última consulta

#### 4.2.2 Ações da Tabela
- **Visualizar**: Ver detalhes completos do paciente
- **Editar**: Modificar informações do paciente
- **Nova Consulta**: Agendar nova consulta
- **Prescrever**: Criar nova prescrição
- **Histórico**: Ver histórico completo
- **Desativar/Ativar**: Alterar status do paciente

#### 4.2.3 Ordenação
- Todas as colunas devem ser ordenáveis
- Indicadores visuais de ordenação (setas)
- Ordenação padrão por última consulta (mais recente primeiro)

### 4.3 Estados e Validações
- Status "Ativo" em verde, "Inativo" em cinza
- Validação de campos obrigatórios no cadastro
- Confirmação antes de desativar paciente
- Loading states durante carregamento de dados

## 5. Módulo Prescrições

### 5.1 Funcionalidades Principais

#### 5.1.1 Header da Seção
- **Título**: "Prescrições"
- **Subtítulo**: "Gerencie prescrições de cannabis medicinal"
- **Botão Primário**: "Nova Prescrição" (verde, canto superior direito)

#### 5.1.2 Barra de Filtros e Busca
- **Campo de Busca**: "Buscar prescrições..." com ícone de lupa
- **Botão Filtros**: Ícone de filtro com texto "Filtros"

#### 5.1.3 Cards de Prescrições
Cada prescrição é exibida como um card contendo:

**Card 1 - CBD 5%**
- **Medicação**: CBD 5% (30ml)
- **Paciente**: Maria Silva
- **Condição**: Ansiedade
- **Posologia**: 5 gotas, 3x ao dia
- **Data**: Início: 01/01/2024
- **Status**: "Ativa" (badge verde)
- **Ações**: Botões "Editar" e "Renovar"
- **Renovações**: 2

**Card 2 - THC+CBD 1:1**
- **Medicação**: THC+CBD 1:1 (30ml)
- **Paciente**: João Santos
- **Condição**: Epilepsia
- **Posologia**: 3 gotas, 1x ao dia
- **Data**: Início: 12/12/2023
- **Status**: "Ativa" (badge verde)
- **Ações**: Botões "Editar" e "Renovar"
- **Renovações**: 1

**Card 3 - CBD 10%**
- **Medicação**: CBD 10% (15ml)
- **Paciente**: Ana Costa
- **Condição**: Dor Crônica
- **Posologia**: 4 gotas, 2x ao dia
- **Data**: Início: 30/12/2023
- **Status**: "Expirada" (badge laranja)
- **Ações**: Botões "Editar" e "Renovar"
- **Renovações**: 0

#### 5.1.4 Cards de Métricas
**Prescrições Ativas**
- Valor: 2
- Cor: verde

**Expiradas**
- Valor: 1
- Cor: laranja

**Total de Renovações**
- Valor: 3
- Cor: azul

**Medicações Diferentes**
- Valor: 3
- Cor: roxo

### 5.2 Funcionalidades de Interação

#### 5.2.1 Busca e Filtros
- Busca por paciente, medicação ou condição
- Filtros por status (Ativa/Expirada/Suspensa)
- Filtros por tipo de medicação (CBD, THC, THC+CBD)
- Filtros por concentração
- Filtros por data de criação/expiração
- Filtros por paciente

#### 5.2.2 Ações dos Cards
- **Editar**: Modificar posologia, duração ou observações
- **Renovar**: Criar nova prescrição baseada na atual
- **Suspender**: Interromper prescrição ativa
- **Imprimir**: Gerar PDF da prescrição
- **Histórico**: Ver todas as alterações

#### 5.2.3 Estados das Prescrições
- **Ativa**: Verde - prescrição em uso
- **Expirada**: Laranja - prescrição vencida
- **Suspensa**: Vermelho - prescrição interrompida
- **Renovada**: Azul - prescrição que gerou renovação

### 5.3 Validações e Regras de Negócio
- Não permitir edição de prescrições expiradas
- Validar posologia máxima por medicação
- Confirmar renovação com possibilidade de ajustes
- Alertar sobre interações medicamentosas
- Validar período mínimo entre renovações

## 6. Módulo Agenda

### 6.1 Funcionalidades Principais

#### 6.1.1 Header da Seção
- **Título**: "Agenda"
- **Subtítulo**: "Gerencie seus agendamentos e consultas"
- **Botão Primário**: "Nova Consulta" (verde, canto superior direito)

#### 6.1.2 Layout Principal
A tela de agenda é dividida em duas seções principais:
- **Calendário** (lado esquerdo): Visualização mensal
- **Agendamentos de Hoje** (lado direito): Lista de consultas do dia

#### 6.1.3 Componente Calendário
**Funcionalidades:**
- Navegação mensal com setas (< >)
- Exibição do mês/ano atual (July 2025)
- Grid semanal (Dom-Sáb)
- Destaque visual para o dia atual (22 - verde)
- Indicadores visuais para dias com agendamentos
- Clique em qualquer dia para ver agendamentos específicos

**Comportamentos:**
- Hover nos dias mostra preview dos agendamentos
- Dias com consultas têm indicador visual diferenciado
- Navegação por teclado (setas) entre os dias

#### 6.1.4 Lista de Agendamentos de Hoje
**Estrutura de cada agendamento:**

**Agendamento 1:**
- **Horário**: 09:00
- **Duração**: 45 min
- **Paciente**: Maria Silva
- **Tipo**: Consulta inicial
- **Status**: "confirmado" (badge verde)

**Agendamento 2:**
- **Horário**: 10:30
- **Duração**: 60 min
- **Paciente**: João Santos
- **Tipo**: Retorno
- **Status**: "pendente" (badge amarelo)

**Agendamento 3:**
- **Horário**: 14:00
- **Duração**: 45 min
- **Paciente**: Ana Costa
- **Tipo**: Acompanhamento
- **Status**: "confirmado" (badge verde)

### 6.2 Funcionalidades de Interação

#### 6.2.1 Ações dos Agendamentos
- **Confirmar**: Alterar status para confirmado
- **Reagendar**: Mover para outro horário/data
- **Cancelar**: Cancelar consulta
- **Iniciar Consulta**: Abrir interface de consulta
- **Ver Detalhes**: Expandir informações completas

#### 6.2.2 Estados dos Agendamentos
- **Confirmado**: Verde - consulta confirmada
- **Pendente**: Amarelo - aguardando confirmação
- **Cancelado**: Vermelho - consulta cancelada
- **Concluído**: Azul - consulta realizada

### 6.3 Validações e Regras
- Não permitir agendamentos em horários já ocupados
- Validar horário de funcionamento da clínica
- Confirmar cancelamentos e reagendamentos
- Alertar sobre conflitos de horário

## 7. Módulo Relatórios

### 7.1 Funcionalidades Principais

#### 7.1.1 Header da Seção
- **Título**: "Relatórios"
- **Subtítulo**: "Análises e estatísticas da clínica"
- **Botão Primário**: "Exportar PDF" (verde, canto superior direito)

#### 7.1.2 Cards de Métricas Principais
**Total de Pacientes**
- Valor: 1,284
- Indicador: +15% vs mês anterior
- Ícone: usuários
- Cor: azul

**Consultas no Mês**
- Valor: 67
- Indicador: +8% vs mês anterior
- Ícone: calendário
- Cor: verde

**Prescrições Ativas**
- Valor: 58
- Indicador: +12% vs mês anterior
- Ícone: prescrição
- Cor: roxo

#### 7.1.3 Navegação por Abas
**Abas disponíveis:**
- **Mensal**: Relatórios mensais (aba ativa)
- **Tratamentos**: Análise por tipo de tratamento
- **Resultados**: Eficácia e outcomes

#### 7.1.4 Gráfico Principal
**Consultas e Prescrições por Mês**
- Tipo: Gráfico de barras duplas
- Período: Janeiro a Junho
- Dados:
  - Janeiro: ~45 consultas, ~38 prescrições
  - Fevereiro: ~52 consultas, ~42 prescrições
  - Março: ~48 consultas, ~40 prescrições
  - Abril: ~62 consultas, ~52 prescrições
  - Maio: ~58 consultas, ~48 prescrições
  - Junho: ~68 consultas, ~58 prescrições

**Funcionalidades do Gráfico:**
- Hover para ver valores exatos
- Legenda interativa (consultas/prescrições)
- Zoom e pan para períodos específicos
- Exportação como imagem

### 7.2 Funcionalidades de Análise

#### 7.2.1 Filtros Disponíveis
- Período (data início/fim)
- Tipo de consulta
- Condição médica
- Faixa etária dos pacientes
- Status das prescrições

#### 7.2.2 Tipos de Relatórios
- **Relatório de Eficácia**: Taxa de melhora por condição
- **Relatório de Adesão**: Compliance dos pacientes
- **Relatório Financeiro**: Receitas e custos
- **Relatório de Medicações**: Uso por tipo de cannabis

### 7.3 Exportação e Compartilhamento
- Exportar como PDF com gráficos
- Exportar dados como CSV/Excel
- Agendar relatórios automáticos
- Compartilhar via email

## 8. Módulo Protocolos

### 8.1 Funcionalidades Principais

#### 8.1.1 Header da Seção
- **Título**: "Protocolos"
- **Subtítulo**: "Protocolos de tratamento e diretrizes clínicas"
- **Botão Primário**: "Novo Protocolo" (verde, canto superior direito)

#### 8.1.2 Barra de Filtros e Busca
- **Campo de Busca**: "Buscar protocolos..." com ícone de lupa
- **Navegação por Abas**: Meus Protocolos, Diretrizes, Templates

#### 8.1.3 Lista de Protocolos
**Protocolo 1 - Ansiedade Generalizada**
- **Condição**: Ansiedade
- **Medicação Base**: CBD 10mg/5mL
- **Duração**: 90 dias
- **Pacientes**: 12 pacientes
- **Status**: "Ativo" (badge verde)
- **Ações**: Visualizar, Editar

**Protocolo 2 - Tratamento de Dor Crônica**
- **Condição**: Dor Crônica
- **Medicação Base**: THC+CBD 1:1 - 5mg/5mL
- **Duração**: 90 dias
- **Pacientes**: 6 pacientes
- **Status**: "Ativo" (badge verde)
- **Ações**: Visualizar, Editar

**Protocolo 3 - Epilepsia Refratária Pediátrica**
- **Condição**: Epilepsia
- **Medicação Base**: CBD 25mg/1mL
- **Duração**: 90 dias
- **Pacientes**: 3 pacientes
- **Status**: "revisão" (badge laranja)
- **Ações**: Visualizar, Editar

### 8.2 Funcionalidades de Gestão

#### 8.2.1 Ações dos Protocolos
- **Visualizar**: Ver detalhes completos do protocolo
- **Editar**: Modificar parâmetros do protocolo
- **Duplicar**: Criar novo protocolo baseado no atual
- **Aplicar**: Usar protocolo em novo paciente
- **Arquivar**: Desativar protocolo

#### 8.2.2 Estados dos Protocolos
- **Ativo**: Verde - protocolo em uso
- **Revisão**: Laranja - protocolo em análise
- **Arquivado**: Cinza - protocolo desativado
- **Rascunho**: Azul - protocolo em desenvolvimento

#### 8.2.3 Informações do Protocolo
Cada protocolo deve conter:
- Nome e descrição
- Condição médica alvo
- Medicação e dosagem inicial
- Escalação de dose
- Duração do tratamento
- Critérios de inclusão/exclusão
- Monitoramento necessário
- Efeitos adversos esperados

### 8.3 Templates e Diretrizes

#### 8.3.1 Templates Pré-definidos
- Protocolos padrão por condição
- Templates personalizáveis
- Importação de protocolos externos

#### 8.3.2 Diretrizes Clínicas
- Referências científicas
- Boas práticas
- Atualizações regulamentares

## 9. Módulo Configurações

### 9.1 Funcionalidades Principais

#### 9.1.1 Header da Seção
- **Título**: "Configurações"
- **Subtítulo**: "Gerencie as configurações do sistema"
- **Botão Primário**: "Salvar Alterações" (verde, canto superior direito)

#### 9.1.2 Navegação por Abas
**Abas disponíveis:**
- **Perfil**: Informações pessoais (aba ativa)
- **Clínica**: Configurações da clínica
- **Notificações**: Preferências de notificação
- **Segurança**: Configurações de segurança
- **Sistema**: Configurações gerais

### 9.2 Seção Perfil (Informações Pessoais)

#### 9.2.1 Campos do Perfil
**Informações Básicas:**
- **Nome**: Dr. João (campo editável)
- **Sobrenome**: Silva (campo editável)
- **E-mail**: joao.silva@clinica.com (campo editável)
- **CRM**: 12345-6 (campo editável)
- **Especialidade**: Neurologia (dropdown selecionável)

#### 9.2.2 Validações do Perfil
- Validação de formato de email
- Validação de CRM (formato e existência)
- Campos obrigatórios marcados
- Confirmação antes de salvar alterações

### 9.3 Outras Seções de Configuração

#### 9.3.1 Configurações da Clínica
- Nome da clínica
- Endereço completo
- Telefone e contatos
- Horário de funcionamento
- Logo da clínica

#### 9.3.2 Notificações
- Notificações por email
- Notificações push
- Lembretes de consultas
- Alertas de prescrições vencendo
- Relatórios automáticos

#### 9.3.3 Segurança
- Alteração de senha
- Autenticação de dois fatores
- Sessões ativas
- Log de acessos
- Backup de dados

#### 9.3.4 Sistema
- Idioma da interface
- Fuso horário
- Formato de data/hora
- Unidades de medida
- Integrações externas

### 9.4 Funcionalidades de Gestão

#### 9.4.1 Salvamento de Configurações
- Auto-save para campos não críticos
- Confirmação para alterações importantes
- Histórico de alterações
- Possibilidade de reverter mudanças

#### 9.4.2 Validações e Segurança
- Confirmação de senha para alterações críticas
- Validação de permissões por seção
- Backup automático antes de mudanças
- Log de todas as alterações

## 10. Especificações Técnicas

### 6.1 Responsividade
- Layout adaptável para desktop, tablet e mobile
- Breakpoints: 1200px, 768px, 480px
- Menu lateral colapsável em telas menores
- Cards empilháveis em mobile
- Tabelas com scroll horizontal em mobile

### 6.2 Performance
- Paginação para listas com mais de 50 itens
- Loading states para todas as operações
- Cache de dados frequentemente acessados
- Lazy loading para imagens e componentes pesados

### 6.3 Acessibilidade
- Contraste mínimo WCAG AA
- Navegação por teclado
- Labels apropriados para screen readers
- Foco visível em todos os elementos interativos
- Textos alternativos para ícones

### 6.4 Estados de Erro
- Mensagens de erro claras e específicas
- Fallbacks para falhas de conexão
- Validação em tempo real nos formulários
- Retry automático para operações falhadas

## 7. Fluxos de Usuário

### 7.1 Fluxo de Cadastro de Paciente
1. Usuário clica em "Novo Paciente"
2. Modal/página de cadastro é aberta
3. Usuário preenche dados obrigatórios
4. Sistema valida informações
5. Paciente é salvo e aparece na lista
6. Usuário é redirecionado para detalhes do paciente

### 7.2 Fluxo de Nova Prescrição
1. Usuário clica em "Nova Prescrição"
2. Seleciona paciente (busca ou lista)
3. Escolhe medicação e concentração
4. Define posologia e duração
5. Adiciona observações se necessário
6. Sistema valida prescrição
7. Prescrição é salva e fica ativa
8. PDF é gerado automaticamente

### 7.3 Fluxo de Renovação
1. Usuário clica em "Renovar" na prescrição
2. Sistema carrega dados da prescrição atual
3. Usuário pode ajustar posologia/duração
4. Sistema valida nova prescrição
5. Prescrição anterior é marcada como renovada
6. Nova prescrição fica ativa

## 8. Integrações Necessárias

### 8.1 Sistema de Notificações
- Alertas de prescrições próximas ao vencimento
- Lembretes de consultas agendadas
- Notificações de novos pacientes

### 8.2 Geração de Relatórios
- Relatórios de eficácia por condição
- Estatísticas de uso por medicação
- Relatórios de adesão ao tratamento

### 8.3 Backup e Sincronização
- Backup automático dos dados
- Sincronização entre dispositivos
- Logs de auditoria para alterações

## 9. Considerações de Segurança

### 9.1 Proteção de Dados
- Criptografia de dados sensíveis
- Controle de acesso baseado em roles
- Logs de acesso e modificações
- Compliance com LGPD

### 9.2 Autenticação
- Login seguro com 2FA opcional
- Sessões com timeout automático
- Bloqueio após tentativas falhadas

## 10. Métricas e Analytics

### 10.1 KPIs do Sistema
- Taxa de adesão ao tratamento
- Tempo médio de consulta
- Eficácia por tipo de medicação
- Satisfação do paciente

### 10.2 Métricas de Uso
- Páginas mais acessadas
- Tempo de permanência por seção
- Ações mais realizadas
- Erros mais frequentes

Esta especificação deve ser usada como base para o desenvolvimento do sistema, garantindo que todas as funcionalidades apresentadas nos protótipos sejam implementadas corretamente.