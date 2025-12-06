name: GitHub Actions - Workflow Dispatch boolean Template

on:
  workflow_dispatch:
    inputs:
      should-deploy:
        description: 'Deseja fazer deploy?'
        required: true
        type: boolean
      environment:
        description: 'Ambiente de produção?'
        required: false
        default: false
        type: boolean

jobs:
  check-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Print choices
        run: |
          echo "Deploy autorizado: ${{ github.event.inputs.should-deploy }}"
          echo "Ambiente de produção: ${{ github.event.inputs.environment }}"
      
      - name: Check deploy choice
        run: |
          if [ "${{ github.event.inputs.should-deploy }}" == "true" ]; then
            echo "🚀 Iniciando procedimento de deploy..."
            if [ "${{ github.event.inputs.environment }}" == "true" ]; then
              echo "⚠️  ATENÇÃO: Deploy em PRODUÇÃO!"
              echo "Realizando backup do banco de dados..."
              echo "Deploy em produção concluído!"
            else
              echo "Deploy em ambiente de staging concluído!"
            fi
          else
            echo "❌ Deploy não autorizado. Apenas validação será executada."
            echo "Executando testes de validação..."
            echo "Validação concluída com sucesso!"
          fi
