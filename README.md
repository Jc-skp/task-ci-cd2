# task-ci-cd2
Atividade de CI/CD com GitHub Actions
## 📋 Workflows Implementados

### 1. Workflow Dispatch Combinado
- **Arquivo**: `.github/workflows/16-workflow-dispatch-combinado.yaml`
- **Trigger**: Manual com inputs múltiplos
- **Funcionalidade**: Demonstra combinação de diferentes tipos de inputs

### 2. Workflow Schedule
- **Arquivo**: `.github/workflows/17-schedule-cron.yaml`
- **Trigger**: Automático por cron
- **Funcionalidade**: Execução agendada com múltiplos horários

## 🚀 Como Testar

### Workflow Dispatch
1. Vá para a aba **Actions**
2. Selecione **"GitHub Actions - Workflow Dispatch Template"**
3. Clique em **"Run workflow"**
4. Preencha os inputs e execute

### Workflow Schedule
- O workflow será executado automaticamente conforme o cronograma
- Para teste rápido, modifique um cron para `*/5 * * * *`

## ⏰ Conversão de Horários (UTC para Brasil)
- UTC → Brasil: Subtraia 3 horas
- Exemplo: 14:00 UTC = 11:00 (Brasília)

## 📊 Status
![CI/CD](https://github.com/seu-usuario/task-ci-cd/actions/workflows/16-workflow-dispatch-combinado.yaml/badge.svg)
