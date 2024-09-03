```
graph TD
    A[Início do Processo] --> B[Criação de Empresa - Holding]
    B --> C[Criar Lançamentos]
    C --> D{Vencimento do Lançamento?}
    D -->|Sim| E[Criar Objeto de Remessa]
    E --> F[Selecionar Lançamentos que Vencem Hoje]
    F --> G[Gerar PDF com Lançamentos]
    G --> H[Enviar PDF para Gestor Validar]
    H --> I{PDF Aprovado pelo Gestor?}
    I -->|Não| H
    I -->|Sim| J[Atualizar Status dos Lançamentos para Autorizado]
    J --> K{Pagamento Concluído?}
    K -->|Não| J
    K -->|Sim| L[Atualizar Status dos Lançamentos para Pago]
    L --> M[Fim do Processo]

    %% Definindo os Status dos Lançamentos
    C --> N((Status: Aberto))
    H --> O((Status: Pendente))
    J --> P((Status: Autorizado))
    L --> Q((Status: Pago))
```