# Message Chains - Code Smell

Demonstração interativa do **code smell Message Chains** para apresentações educacionais.

## 📖 Sobre o Code Smell

**Message Chains** é um code smell identificado por Martin Fowler que ocorre quando você vê uma longa cadeia de chamadas de métodos para acessar um objeto distante.

### 🚨 Problema
```java
// Code Smell - Message Chain
customer.getAddress().getStreet().getName().toUpperCase()
order.getCustomer().getAddress().getCity().getZipCode()
```

### ✅ Solução
```java
// Aplicando Lei de Demeter
customer.getStreetName()
order.getCustomerZipCode()
```

## 🎯 Lei de Demeter

**"Fale apenas com seus amigos próximos"**

Um método M de um objeto O deve invocar apenas métodos de:
- O próprio objeto O
- Parâmetros de M
- Objetos criados dentro de M
- Atributos diretos de O

## 🚀 Demo Interativa

Abra o `index.html` no navegador para:

- **Visualizar** exemplos de Message Chains
- **Comparar** código problemático vs. refatorado
- **Simular** refatorações em tempo real
- **Testar** conhecimento com quiz interativo

## 💡 Por que é um Problema?

| Problema | Descrição | Impacto |
|----------|-----------|---------|
| **Alto Acoplamento** | Classes conhecem estrutura interna de outras | Dificulta manutenção |
| **Código Frágil** | Mudanças na cadeia quebram clientes | Bugs em produção |
| **Baixa Legibilidade** | Cadeias longas são difíceis de entender | Reduz produtividade |
| **Violação de Encapsulamento** | Expõe estrutura interna | Design ruim |

## 🔧 Técnicas de Refatoração

### 1. Hide Delegate
```java
// Antes
manager.getPerson().getDepartment()

// Depois
manager.getDepartment()
```

### 2. Extract Method
```java
// Antes
customer.getAddress().getStreet().getName()

// Depois
getCustomerStreetName(customer)
```

### 3. Move Method
```java
// Mover lógica para a classe apropriada
class Customer {
    public String getStreetName() {
        return this.address.getStreet().getName();
    }
}
```

## 🎓 Para Educadores

Esta ferramenta é ideal para:
- Aulas de Clean Code
- Workshops de refatoração
- Demonstrações de SOLID
- Treinamentos corporativos

### Recursos Pedagógicos:
- Exemplos visuais interativos
- Comparações lado a lado
- Quiz de conhecimento
- Casos reais da indústria

## 🛠️ Como Executar

```bash
# Clone o repositório
git clone https://github.com/marchingbeagle/message-chains.git

# Abra no navegador
start index.html
```

## 📚 Referências

- **Refactoring** - Martin Fowler
- **Clean Code** - Robert C. Martin
- **Design Patterns** - Gang of Four

---

*Ferramenta educacional para ensino de Clean Code e refatoração*

## 🎯 O que é

O Message Chain é um padrão de comunicação onde mensagens passam sequencialmente por diferentes componentes, permitindo processamento modular e rastreável.

## 🚀 Demo

Abra o `index.html` no navegador para ver a demonstração interativa com:

- Explicação conceitual do padrão
- Fluxo visual animado
- Simulador interativo

## 💡 Casos de Uso

- **Pipelines de dados**: Validação → Transformação → Entrega
- **Integrações**: Processamento distribuído entre serviços
- **Auditoria**: Rastreamento de fluxos de mensagem

## 🛠️ Como Executar

```bash
# Clone o repositório
git clone https://github.com/marchingbeagle/message-chains.git

# Abra o arquivo no navegador
open index.html
```

---

Projeto educacional sobre padrões de comunicação em sistemas distribuídos
