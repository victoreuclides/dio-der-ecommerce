# Diagrama Entidade-Relacionamento de Ecommerce

### Esse projeto foi desenvolvido com o objetivo de praticar os conceitos de modelagem de dados aprendidos no **Bootcamp Randstad - Análise de Dados (2025)** da DIO

O _DER_ ilustra a modelagem do banco de dados de um ecommerce fictício. Ele foi feito na plataforma _"DMBL"_. 

Essa plataforma reconhece o código digitado e cria o diagrama a partir dele. 

## Código: 

```
Table Cliente {
  idCliente int [pk]
  nome varchar
  identificacao varchar
  endereco varchar
}

Table Pedido {
  idPedido int [pk]
  status varchar
  descricao varchar
  idCliente int [ref: > Cliente.idCliente]
}

Table Fornecedor {
  idFornecedor int [pk]
  razao_social varchar
  CNPJ varchar
}

Table Produto {
  idProduto int [pk]
  categoria varchar
  descricao varchar
  valor decimal
  idFornecedor int [ref: > Fornecedor.idFornecedor]
}

Table Estoque {
  idEstoque int [pk]
  local varchar
}

Table Produto_Estoque {
  idProduto int [ref: > Produto.idProduto]
  idEstoque int [ref: > Estoque.idEstoque]
  quantidade int
  [pk: idProduto, idEstoque]
}

Table Terceiro_Vendedor {
  idVendedor int [pk]
  razao_social varchar
  local varchar
}

Table Produto_Vendedor {
  idProduto int [ref: > Produto.idProduto]
  idVendedor int [ref: > Terceiro_Vendedor.idVendedor]
  [pk: idProduto, idVendedor]
}
```

Aqui no repo você consegue ver o arquivo _.svg_ para ver o resultado final. 