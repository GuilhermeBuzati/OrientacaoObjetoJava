# 📘 Resumo das Anotações
**Curso:** Java: Aplicando a Orientação a Objetos


## 🧱 Classe, Atributos e Instanciação de Objetos

### 📦 Classe

- Uma classe em Java é como um molde para criar objetos.
Ela define as características (atributos) e comportamentos (métodos) que os objetos terão.

### 🧬 Atributos
- Os atributos são as variáveis internas de uma classe. Representam o estado do objeto.

```java
public class Filme {
    String titulo;
    int anoDeLancamento;
}
```

### 🆕 Instanciando um Objeto
 
- Um objeto é criado a partir da classe usando o operador new.

```java
Filme meuFilme = new Filme();
meuFilme.titulo = "Matrix";
meuFilme.anoDeLancamento = 1999;
```

- Após instanciar, podemos acessar e modificar os atributos com . (ponto).

---

## 🛠️ Métodos em Java
 - Métodos são blocos de código que representam comportamentos de uma classe.

 - São usados para executar ações, manipular atributos ou retornar valores.

### 📌 Estrutura de um método:

```java
public void exibirFichaTecnica() {
    System.out.println("Título: " + titulo);
    System.out.println("Ano: " + anoDeLancamento);
}
```

### 🔑 Componentes de um método:

- public: modificador de acesso
- void: tipo de retorno (void = sem retorno)
- exibirFichaTecnica: nome do método
- () parênteses: indicam que é um método e podem receber parâmetros

### ✅ Chamando um método:

```java
meuFilme.exibirFichaTecnica();
```

### 🧠 Observações:
- Métodos podem receber parâmetros e retornar valores.
- Exemplo com retorno:

```java
public int obterAno() {
    return anoDeLancamento;
}
```
---

## 🔒 Modificador private e Métodos Acessores (get/set)

### 🔐 private

- O modificador private restringe o acesso de um atributo ou método apenas dentro da própria classe.

- Isso faz parte do princípio de encapsulamento, protegendo os dados internos do objeto.

```java
public class Filme {
    private String titulo;
    private int anoDeLancamento;
}
```

### 📥 Método get

- Usado para acessar (ler) o valor de um atributo private.

```java
public String getTitulo() {
    return titulo;
}
```

### 📤 Método set

- Usado para alterar (escrever) o valor de um atributo private.

```java
public void setTitulo(String novoTitulo) {
    this.titulo = novoTitulo;
}
```
### ✅ Exemplo de uso:

```java
Filme filme = new Filme();
filme.setTitulo("Matrix");
System.out.println(filme.getTitulo());  // Saída: Matrix
```

---

## 🛡️ Modificadores de Acesso em Java

- Os modificadores de acesso definem o nível de visibilidade de classes, atributos e métodos para outras partes do código.

    ![img.png](img.png)

### ✅ Exemplos:
```java
public class Pessoa {
    private String nome;           // Visível apenas dentro da classe
    protected int idade;           // Visível no mesmo pacote e subclasses
    String cidade;                 // (package-private) visível no mesmo pacote
    public String nacionalidade;   // Visível em qualquer lugar
}
```

---

## 📦 Pacotes em Java e Convenções de Nomenclatura

### 🗂️ O que são pacotes?

- Pacotes (packages) são usados para organizar classes em grupos lógicos.
- Facilitam a manutenção do código e evitam conflitos de nomes.
- Um pacote é representado por uma estrutura de diretórios no projeto.

### 🧾 Como declarar um pacote:

- A declaração deve ser a primeira linha do arquivo .java:

```java
package br.com.guilherme.minhaplicacao;
```

- Isso indica que a classe pertence ao pacote br.com.guilherme.minhaplicacao.

## ✍️ Convenções de Nomenclatura para Pacotes e Classes

### 📌 Pacotes:

- Usam letras minúsculas.
- Costumam seguir o padrão do domínio invertido da empresa.

- Exemplos:
  - com.alura.loja
  - br.com.guilherme.minhaplicacao

### 📌 Classes:

- Nome com inicial maiúscula, estilo CamelCase.
- Exemplo: Filme, PessoaFisica, CalculadoraFinanceira

---

## 🧱 Encapsulamento em Java

- Encapsulamento é o princípio de esconder os detalhes internos de uma classe e expor apenas o necessário para uso externo.
- Ele protege os dados e melhora a manutenção e segurança do código.

### ✅ Como aplicar encapsulamento:

- Tornar os atributos private.
- Fornecer métodos public de acesso (get) e modificação (set).

## 📌 Exemplo:

```java
public class Conta {
private double saldo;

    public double getSaldo() {
        return saldo;
    }

    public void setSaldo(double novoSaldo) {
        if (novoSaldo > 0) {
            this.saldo = novoSaldo;
        }
    }
}
```

### 🔒 Benefícios:

- Impede acesso direto e indesejado aos atributos.
- Permite aplicar regras de negócio (ex: validações) nos métodos set.
- Ajuda a manter o controle sobre o estado interno do objeto.