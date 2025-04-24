# Modelagem Conceitual Oficina de Mecanica 
Este projeto modela o esquema conceitual de um sistema de ordens de serviço para uma oficina. 

## Contexto

Clientes levam veículos para conserto ou revisão. Cada veículo é designado a uma equipe que avalia e executa os serviços. O sistema gerencia ordens de serviço (OS), os serviços executados, as peças utilizadas, os mecânicos envolvidos e os clientes.

## Diagrama ER

![Untitled](https://github.com/user-attachments/assets/03607a68-90b1-4bb7-8cda-1d7247d9c243) 

## 🧱 Descrição das Entidades e Relacionamentos

### Cliente
Representa a pessoa que leva o veículo à oficina. Um cliente pode possuir **vários veículos**, mas cada veículo pertence a **apenas um cliente**.

### Veículo
Identificado por placa, modelo e ano, é o objeto de conserto ou revisão. Cada veículo está associado a **um cliente** e pode gerar **várias ordens de serviço** ao longo do tempo.

### Ordem_de_Serviço (OS)
Documento que centraliza os dados da manutenção ou revisão: data de emissão, status, data de entrega, serviços executados, peças utilizadas e valor total. Cada OS está vinculada a **um veículo** e é executada por **uma equipe**.

### Equipe
Conjunto de mecânicos responsável por avaliar e executar os serviços. Cada equipe pode ser atribuída a **várias ordens de serviço** e contém **vários mecânicos**.

### Mecânico
Profissional com especialidade definida, pertencente a uma equipe. Cada mecânico está associado a **uma única equipe**.

### Serviço
Ações realizadas sobre o veículo, podendo ser **revisão** ou **conserto**. Possui um custo de mão de obra. Uma mesma OS pode incluir **vários serviços**, e um serviço pode aparecer em **várias OS**.

### Peça
Item utilizado para reposição ou conserto do veículo. Cada OS pode envolver o uso de **várias peças**, e uma peça pode estar presente em **diversas OS**.

### OS_Serviço (tabela associativa)
Relaciona ordens de serviço com serviços específicos executados, permitindo registrar o **valor individual da mão de obra** aplicada por serviço.

### OS_Peça (tabela associativa)
Relaciona ordens de serviço com as peças utilizadas, registrando a **quantidade** e o **valor total das peças** aplicadas.



## Considerações

- A tabela de referência de mão de obra foi modelada como atributo dentro de "Serviço".
- Serviços podem ser do tipo **conserto** ou **revisão**.
- Uma OS pode conter vários serviços e peças.

