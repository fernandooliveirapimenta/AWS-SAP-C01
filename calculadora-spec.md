# Especificações: Calculadora em Java (CLI)

## Requisitos
- **Interface:** Console (CLI)
- **Funcionalidades:** Operações básicas (+, -, *, /) + Histórico
- **Tecnologia:** Java 25 + Maven 4

## Estrutura do Projeto

```
calculadora/
├── pom.xml                           (Maven config)
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/
│   │           └── calculadora/
│   │               ├── Main.java
│   │               ├── Calculadora.java
│   │               ├── Operacao.java
│   │               └── Historico.java
│   └── test/
│       └── java/
│           └── com/
│               └── calculadora/
│                   └── CalculadoraTest.java
```

## Arquivos a Criar

### 1. pom.xml
Configuração Maven com:
- JUnit 5 para testes
- Compilação com Java 25

### 2. Operacao.java
Enum com tipos de operação:
```java
SOMA, SUBTRACAO, MULTIPLICACAO, DIVISAO
```

### 3. Historico.java
Classe para gerenciar:
- Lista de operações executadas
- Formato: `10.0 + 5.0 = 15.0`
- Método `exibirHistorico()`

### 4. Calculadora.java
Lógica principal:
- Métodos para as 4 operações
- Validação (ex: divisão por zero)
- Integração com histórico

### 5. Main.java
Menu interativo:
- Exibir opções
- Ler entrada do usuário
- Loop de execução
- Opção para sair

### 6. CalculadoraTest.java
Testes unitários

## Fluxo do Usuário

```
1. Exibir menu
2. Usuário escolhe operação (1-4) ou histórico (5) ou sair (0)
3. Solicitar dois números
4. Executar cálculo
5. Salvar no histórico
6. Mostrar resultado
7. Repetir
```

## Comandos Maven

```bash
# Compilar
mvn compile

# Executar testes
mvn test

# Empacotar
mvn package

# Executar aplicação
mvn exec:java -Dexec.mainClass="com.calculadora.Main"
```

## Requisitos Técnicos
- Java 25+ (OpenJDK)
- Maven 4+
- JUnit 5 para testes

## Observações
- A calculadora deve validar entradas numéricas
- Tratamento de divisão por zero
- Histórico mantém todas as operações até o fim da execução
- Interface limpa e amigável no console