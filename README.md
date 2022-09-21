# Modelando-E-commerce

Arquivo em formato PDF disponibilizado como E-commerce

Modelagem de um banco de dados relacional para uma plataforma de E-commerce. Desafio proposto pela plataforma Dio.me

Neste modelo simplicado de um E-commerce temos algumas entidades como: Cliente, Pedido, Fornecedor, Entrega, Pagamento, Estoque, Terceiro Vendedor...

Em meu refinamento da proposta, optei por utilizar PF(pessoa fisica) e PJ(pessoa juridica) como atributos do Cliente, não vi necessidade de se criar uma nova entidade para esse tipo de informação. É necessario que esse dados sejam auto-excludentes, ou seja, caso o campo de PF esteja preenchido o de PJ estará como NULL e vice-versa.

Escolhi tambem criar duas novas entidades, sendo elas o Pagamento e a Entrega.

Pagamento: Entidade com atributos como: IDPagamento, Forma do pagamento, Data, quantidade de parcelas...
O pagamento se relaciona com a tabela Cliente, já que um cliente pode fazer mais de uma compra no site e os pagamentos podem ser feitos por varios Clientes, gerando dessa forma uma nova tabela Cliente_pagamento.
Além do mais, a entidade pagamento tambem se relaciona com a tabela Produtos por pedido, dessa forma, conseguimos consultar na tabela pagamento a qual pedido, produto e cliente está associado, recuperando dessa forma todas as informações necessarias.

Entrega: Entidade com atributos como: Data, Status, Valor
A entrega se relaciona com a tabela Produtos por pedido, dessa forma conseguimos recuperar assim como na tabela Pagamento, a qual pedido e a qual produto a entrega se refere
