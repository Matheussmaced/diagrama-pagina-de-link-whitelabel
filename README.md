# diagrama-funeraria

```mermaid
classDiagram
    class Usuário {
        int id
        String nome
        String email
        String senha
        Role role
        cadastrar()
        visualizar()
        editar()
        deletar()
    }

    class Role {
        int id
        String nome
        cadastrar()
        visualizar()
        editar()
        deletar()
    }

    class Pagamento {
        int id
        float valor
        Date data_pagamento
        String status
        visualizar_pagamento()
        atualizar_pagamento()
    }

    class MétodoDePagamento {
        int id
        String tipo
        realizar_pagamento()
    }

    class CobrançaAutomática {
        int id
        float valor
        Date data_vencimento
        cobrar_cartao_credito()
    }

    class Cobrança {
        int id
        float valor
        Date data_vencimento
        enviar_email_cobranca()
        mostrar_cobranca_usuario()
    }

    class Plano {
        int id
        String nome
        String descricao
        float preco
        List~Foto~ fotos
        cadastrar_foto()
        editar_foto()
        deletar_foto()
    }

    class Foto {
        int id
        String url
        String descricao
        adicionar_foto()
        deletar_foto()
    }

    Usuário --> Role : "1"
    Usuário --> Pagamento : "1..*"
    Pagamento --> MétodoDePagamento : "1"
    Plano --> Foto : "1..*"
    CobrançaAutomática --> Pagamento : "1"
