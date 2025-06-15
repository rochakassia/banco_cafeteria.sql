-- Criação da tabela de produtos
CREATE TABLE produtos (
    id_produto INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    preco REAL NOT NULL,
    estoque INTEGER NOT NULL
);

-- Criação da tabela de pedidos
CREATE TABLE pedidos (
    id_pedido INTEGER PRIMARY KEY,
    id_produto INTEGER,
    quantidade INTEGER NOT NULL,
    data_pedido DATE DEFAULT CURRENT_DATE,
    FOREIGN KEY (id_produto) REFERENCES produtos (id_produto)
);

-- Inserir produtos
INSERT INTO produtos (id_produto, nome, preco, estoque) VALUES
(1, 'Café Expresso', 1.20, 100),
(2, 'Cappuccino', 1.80, 80),
(3, 'Pastel de Nata', 0.90, 150);

-- Inserir pedidos
INSERT INTO pedidos (id_pedido, id_produto, quantidade) VALUES
(1, 1, 2),
(2, 3, 5),
(3, 2, 1);
