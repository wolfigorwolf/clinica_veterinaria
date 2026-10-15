# trabalho-engenharia-software-2026
Trabalho de clínica veterinária do Técnico em Informática, segundo semestre de 2026.

## Diagramas UML

#Diagrama de classe de uso

```mermaid
flowchart LR
    Cliente([Cliente])
    Vet([Veterinário])

    subgraph Sistema["Sistema da Clínica Veterinária Vital"]
        direction TB

        subgraph ClienteAT["Atendimento ao cliente"]
            AT1([Cadastrar animal])
            AT2([Agendar consulta])
            AT3([Consultar agendamentos])
            AT4([Consultar histórico do animal])
        end

        subgraph VetAT["Atendimento veterinário"]
            AT5([Realizar consulta])
            AT6([Registrar prescrição])
            AT7([Registrar exames])
        end
    end

    Cliente -- "Solicita Atendimento" --- AT1
    Cliente -- "Solicita Atendimento" --- AT2
    Cliente -- "Solicita Atendimento" --- AT3
    Cliente -- "Solicita Atendimento" --- AT4

    Vet -- "Realiza Atendimento" --- AT5
    Vet -- "Realiza Atendimento" --- AT6
    Vet -- "Realiza Atendimento" --- AT7

    Vet -- "Atende" --- Cliente

    classDef cliente fill:#D6EAF8,stroke:#2874A6,color:#111
    classDef vet fill:#D5F5E3,stroke:#239B56,color:#111

    class AT1,AT2,AT3,AT4 cliente
    class AT5,AT6,AT7 vet

```

```mermaid
flowchart TD
    cliente["👲Cliente"]
    garçon["💂Garçon"]

   
%% ações
subgraph sistema
    comida["pedir comida"]
    vinho["pedir vinho"]
    end


%%relacionamentos
    cliente -- "faz pedido" --- comida
    garçon -- "recebe pedido" --- comida

    vinho -. "estende" .-> comida

```

### Diagrama de classes

```mermaid
classDiagram
    class Veterinario {
        -String CPF
        +darCPF() String
        +atenderAnimal(Animal animal) void
    }

    class Animal {
        -Cliente dono
        -String nome
        -String raca
        -float peso
        +darNome() String
        +darRaca() String
        +darPeso() float
    }

    class Cliente {
        -Animal[] animais
        -String telefone
        -String nome
        -String CPF
        +darTelefone() String
        +darNome() String
        +darCPF() String
    }

    Cliente -->  Animal : possui
    Veterinario -->  Animal : atende

```
