erDiagram
    Usuarios ||--o{ Pedidos : faz
    Pedidos ||--|{ ItensPedido : contem
    Produtos ||--o{ ItensPedido : e_contido_em
    Supermercados ||--o{ Produtos : possui
    Pedidos ||--o| EnderecosEntrega : contem

    Usuarios {
        int id PK
        string nome
        string email UNIQUE
        string senha
        string tipo_usuario
        datetime data_criacao
    }

    Supermercados {
        int id PK
        string nome
        string endereco
        string telefone
        int id_usuario FK
    }

    Produtos {
        int id PK
        string nome
        string descricao
        float preco
        int quantidade_estoque
        int id_supermercado FK
    }

    Pedidos {
        int id PK
        datetime data_pedido
        string status
        float total
        int id_usuario FK
    }

    ItensPedido {
        int id PK
        int quantidade
        float preco_unitario
        int id_produto FK
        int id_pedido FK
    }

    EnderecosEntrega {
        int id PK
        string rua
        string numero
        string cidade
        string estado
        string cep
        int id_pedido FK
    }
