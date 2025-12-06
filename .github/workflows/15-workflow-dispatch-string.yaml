name: GitHub Actions - Workflow Dispatch string Template

on:
  workflow_dispatch:
    inputs:
      reason:
        description: 'Razão para executar a pipeline'
        required: true
        type: string
      version:
        description: 'Versão da aplicação (ex: 1.0.0)'
        required: false
        type: string
        default: '1.0.0'

jobs:
  print-reason:
    runs-on: ubuntu-latest
    steps:
      - name: Print the inputs
        run: |
          echo "📝 Razão fornecida: ${{ github.event.inputs.reason }}"
          echo "🏷️  Versão: ${{ github.event.inputs.version }}"
          echo "👤 Executado por: ${{ github.actor }}"
          echo "📅 Data: $(date)"
      
      - name: Log the execution
        run: |
          echo "LOG DE EXECUÇÃO" >> log.txt
          echo "Razão: ${{ github.event.inputs.reason }}" >> log.txt
          echo "Versão: ${{ github.event.inputs.version }}" >> log.txt
          cat log.txt
