name: GitHub Actions - Workflow Dispatch choice Template

on:
  workflow_dispatch:
    inputs:
      tag:
        description: 'Escolha uma tag para deploy'
        required: true
        default: 'tag1'
        type: choice
        options:
          - tag1
          - tag2
          - tag3

jobs:
  print-choice:
    runs-on: ubuntu-latest
    steps:
      - name: Print the choice
        run: echo "Você escolheu a tag ${{ github.event.inputs.tag }}"
      
      - name: Execute based on choice
        run: |
          if [ "${{ github.event.inputs.tag }}" == "tag1" ]; then
            echo "Executando procedimento para tag1"
          elif [ "${{ github.event.inputs.tag }}" == "tag2" ]; then
            echo "Executando procedimento para tag2"
          else
            echo "Executando procedimento para tag3"
          fi
