# Sistema de Controle Patrimonial de equipamentos de TI na GEXSTM

Sistema para o controle patrimonial de equipamentos de TI da Gerência Executiva do INSS, totalmente desenvolvido em Java para auxiliar no gerenciamento de computadores, monitores e impressoras.

---

## Sobre o Projeto

O **Sistema de Controle Patrimonial de Equipamentos de TI** foi desenvolvido com o objetivo de resolver uma lacuna encontrada durante o meu estágio na área de Tecnologia da Informação na Gerência Executiva do INSS de Santa Maria (GEXSTM).

Durante as atividades diárias, é necessário manter o controle patrimonial dos equipamentos presentes nas 13 APS (Agência da Previdência Social) da região, porém existem limitações no acesso ao sistema do próprio INSS responsável por esse gerenciamento, uma vez que eles dependem de permissões específicas e do uso de token de acesso que apenas servidores públicos especializados em logística possuem.

Devido a essas limitações, o meu controle e dos outros estagiários acaba sendo realizado por meio de planilhas, o que dificulta a organização e a atualização dos dados. E esse projeto acaba sendo uma alternativa simples para auxiliar no meu controle pessoal desses equipamentos, proporcionando uma forma mais estruturada para armazenar e consultar informações importantes, como o número de patrimônio, número de série, servidor responsável pelo equipamento, o setor e a localização, além de que facilitaria também em um controle de inventário mais preciso e eficaz, sabendo onde está exatamente cada computador e todos seus dados e substituindo o uso de planilhas longas.

---

## Tecnologias Utilizadas

* Java
* Visual Studio Code

---

## Aplicação de requisitos no projeto

### 1. Classes, Objetos e Atributos

O sistema foi modelado por meio das classes Equipamento, Computador, Monitor, Impressora, Usuario e Inventario. Essas classes representam entidades do problema e permitem a criação de objetos com os seus atributos específicos.

### 2. Construtores

As classes possuem construtores padrão que permitem a criação dos objetos. Também é utilizada sobrecarga de construtores para possibilitar diferentes formas de inicialização.

### 3. Encapsulamento

Os atributos das classes são declarados como privados, sendo acessados por meio de métodos getters e setters, garantindo maior segurança e controle sobre os dados armazenados.

### 4. Herança

A classe abstrata Equipamento representa todos equipamentos cadastrados. As classes Computador, Monitor e Impressora herdam suas características, reutilizando o código da classe mãe.

### 5. Polimorfismo

O sistema utiliza polimorfismo por meio de uma coleção do tipo ArrayList<Equipamento>, permitindo que diferentes tipos de equipamentos sejam tratados. Além disso, métodos sobrescritos nas subclasses permitem um comportamento específico para cada tipo de equipamento.

### 6. Classe Abstrata e Interface

A classe Equipamento foi definida como abstrata, servindo como base para os demais equipamentos. Também foi criada a interface Manutencao, estabelecendo métodos que devem ser implementado pelas classes filhas que necessitam realizar alguma manutenção.

### 7. Tratamento de Exceções

Foi criada uma exceção personalizada chamada PatrimonioInvalidoException, responsável por garantir que o número de patrimônio seja composto por exatamente nove dígitos, que é padrão de todos os itens com patrimônio no INSS. O sistema também faz uso de blocos try-catch-finally para tratar situações excepcionais e evitar falhas na execução do programa.

---

---

## Estrutura do Projeto

```
SistemaControlePatrimonialTI/
│
├── Main.java                            # Execução principal do sistema
├── Equipamento.java                     # Classe abstrata dos equipamentos de TI
├── Usuario.java                         # Servidor responsável pelos equipamentos
├── Computador.java                      # Classe dos computador
├── Monitor.java                         # Classe dos monitores
├── Impressora.java                      # Classe das impressoras
├── Manutencao.java                      # Interface de manutenção
├── Inventario.java                      # Onde será o controle dos equipamentos cadastrados
└── PatrimonioInvalidoException.java     # Exceção personalizada, onde o patrimônio só será válido se tiver 9 digitos
```

---

## Funcionamento

O sistema realiza:

### 1. Cadastro dos Equipamentos

* Cadastro de computadores
* Cadastro de monitores
* Cadastro de impressoras
* Armazenamento de marca, modelo, número de série e patrimônio

### 2. Controle dos Responsáveis

* Responsável pelo equipamento
* Setor
* Localização

### 3. Gerenciamento do Inventário

* Armazenamento dos equipamentos em uma coleção
* Consulta dos equipamentos cadastrados
* Organização das informações em um único lugar

### 4. Validação dos Dados

* Verificação do número do patrimônio
* Tratamento de exceções para patrimônios inválidos
* Utilização de blocos try-catch-finally para evitar falhas durante a execução

---
## Como Executar

### 1. Clone o repositório

```bash
git clone <repositorio>
```

### 2. Abra o projeto no Visual Studio Code

Certifique-se de possuir o Java instalado e configurado.

### 3. Execute

Execute o arquivo:

```bash
Main.java
```

---

## Autor

Lucas Camargo de Souza

Projeto desenvolvido para uso pessoal no meu estágio e como trabalho final da disciplina de Programação Orientada a Objetos.
