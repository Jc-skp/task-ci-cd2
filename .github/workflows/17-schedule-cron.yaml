name: GitHub Actions - Cron Job Template
run-name: Running - ${{ github.event_name }}
on:
  schedule:
    # Backups diários às 2:00 AM UTC (23:00 horário de Brasília)
    - cron: '0 2 * * *'
    
    # Limpeza de logs às segundas e quintas às 6:30 AM UTC (3:30 AM Brasília)
    - cron: '30 6 * * 1,4'
    
    # Relatório semanal às sextas às 17:00 UTC (14:00 Brasília)
    - cron: '0 17 * * 5'
    
    # Backup mensal no primeiro dia do mês às 4:00 AM UTC (1:00 AM Brasília)
    - cron: '0 4 1 * *'
    
    # Verificação de segurança às 18:00 todas as quartas (15:00 Brasília)
    - cron: '0 18 * * 3'
    
    # Teste especial no último dia do ano às 23:59 UTC (20:59 Brasília)
    - cron: '59 23 31 12 *'

  # Também pode ser acionado manualmente
  workflow_dispatch:
    inputs:
      tipo_teste:
        description: 'Tipo de teste a ser executado'
        type: choice
        options: ['completo', 'rapido', 'personalizado']
        default: 'rapido'

jobs:
  cron_job_principal:
    runs-on: ubuntu-latest
    steps:
      - name: Verificar hora atual
        run: |
          echo "⏰ Horário UTC: $(date -u)"
          echo "🌎 Horário Brasil (UTC-3): $(TZ='America/Sao_Paulo' date)"
          echo "📅 Data completa: $(date)"
          
      - name: Executar tarefa agendada
        run: |
          echo "🔄 Executando tarefa agendada..."
          echo "🔍 Verificando triggers..."
          echo "📁 Fazendo backup de logs..."
          echo "🧹 Limpando cache temporário..."
          echo "📊 Gerando relatórios..."
          
      - name: Registrar execução
        run: |
          echo "📝 Registrando execução no log..."
          echo "Execução: $(date)" >> execution_log.txt
          echo "Workflow: ${{ github.workflow }}" >> execution_log.txt
          echo "Trigger: ${{ github.event_name }}" >> execution_log.txt
          
      - name: Notificar conclusão
        run: |
          echo "✅ Tarefa agendada concluída com sucesso!"
          echo "⏰ Próxima execução conforme agendamento"
          
  teste_seguranca:
    runs-on: ubuntu-latest
    needs: cron_job_principal
    if: github.event.schedule == '0 18 * * 3' || github.event_name == 'workflow_dispatch'
    
    steps:
      - name: Verificação de segurança
        run: |
          echo "🛡️  Iniciando verificação de segurança..."
          echo "🔒 Verificando dependências..."
          echo "📦 Analisando vulnerabilidades..."
          echo "✅ Verificação de segurança concluída!"
