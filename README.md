```mermaid
classDiagram
    class Usuario {
        +String id
        +String nome
        +String email
        +String senha
        +String cpf
        +String rg
    }

    class Cliente {
        +String id
        +String nome
        +String cpf
        +String rg
        +String telefone
    }

    class Financeiro {
        +String id
        +double saldo
        +void registrarDespesa(double valor, String descricao)
        +void registrarReceita(double valor, String descricao)
    }

    class Despesa {
        +String id
        +double valor
        +String descricao
        +Date data
    }

    class Receita {
        +String id
        +double valor
        +String descricao
        +Date data
    }

    class Horario {
        +String id
        +Date data
        +String descricao
        +double horasTrabalhadas
    }

    Usuario --> Cliente : pode cadastrar
    Cliente "1" --> "0..*" Horario : tem registros de horário
    Financeiro "1" --> "0..*" Despesa : tem despesas
    Financeiro "1" --> "0..*" Receita : tem receitas
