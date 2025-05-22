-- banco.sql

CREATE TABLE IF NOT EXISTS clientes (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    cpf_cnpj TEXT UNIQUE NOT NULL,
    telefone TEXT,
    endereco TEXT,
    data_cadastro DATE DEFAULT (DATE('now'))
);

CREATE TABLE IF NOT EXISTS produtos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    categoria TEXT,
    quantidade INTEGER DEFAULT 0,
    preco_custo REAL,
    preco_venda REAL,
    fornecedor TEXT
);

CREATE TABLE IF NOT EXISTS financeiro (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    tipo TEXT CHECK(tipo IN ('ativo', 'passivo')) NOT NULL,
    categoria TEXT NOT NULL,
    descricao TEXT,
    valor REAL NOT NULL,
    data_movimento DATE DEFAULT (DATE('now'))
);
