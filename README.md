# Exercício Corrida

O objetivo desse exercício é praticar a implementação de uma classe em Java e
sua utilização em outra classe.

## Orientações Gerais

- Você deve fazer um passo de cada vez, testá-lo, fazer o commit e enviar suas alterações.
Somente depois disso é que você deve passar para o próximo passo.

- **ATENÇÃO**: **desligue o GitHub Copilot para fazer o exercício!**
  - Se você utilizá-lo você não estará realmente exercitando os conceitos aprendidos e
    não terá o domínio adequado para desenvolver as habilidades necessárias para se tornar
	um bom programador/desenvolvedor.
  - Sem contar ainda a questão do plágio.
  - Os exercícios trazem exemplos de código em Java, e você também pode consultar os
    slides das aulas teóricas de revisão.

- Esse arquivo README pode ser melhor visualizado no VS Code (com formatação adequada) 
  abrindo-o no modo de visualização. Para isso, basta apertar Ctrl+Sfhit+V com ele aberto.


## Passo 1 - Classe para corredores

Neste exercício vamos criar uma classe para representar um corredor amador, ou seja,
uma pessoa que corre com o objetivo de cuidar de sua saúde.

Para facilitar, vamos considerar um cenário bem simples, no qual todo corredor tem 
apenas um nome, a distância percorrida e as calorias gastas na corrida.

Neste passo, você deve então criar uma classe para representar corredores.

- A classe deve ter um nome que represente bem os seus objetos.
- A classe deve ter os atributos conforme citado acima (nome, distância e calorias gastas).
  - Considere que a distância e as calorias são valores inteiros.
- A classe deve ter um construtor que inicialize os corredores com um estado válido.
- A classe deve ter métodos de acesso (_get_) que permitam acessar os valores dos três atributos.

Para ajudá-lo a lembrar da sintaxe do Java, segue abaixo um exemplo de código de uma classe.

```java
// --- CÓDIGO DE EXEMPLO ---
// Por convenção os nomes das classes iniciam-se com letra maiúscula; 
//  e os nomes de atributos e métodos com letra minúscula.
// Também por convenção utilizamos nomes com camelCase.
// - Ou seja, sem separar com _ e cada palavra do nome, a partir da segunda, iniciada com letra maiúscula
public class NomeDaClasse {

	// Atributos
    // Lembre-se que os atributos de uma classe devem ser encapsulados (ou seja, devem ser sempre privados).
	private int atrituboInteiro;
	private String atributoString;

	// Construtor
	public NomeDaClasse(Tipo parametro1, ...) {
		...		
	}

	// Método para retornar um atributo
    // É convenção também abrir as chaves ao final da linha.
	public int getAtributoInteiro() {
		return atributoInteiro;
	}
}
```

Neste passo ainda não é possível testar o seu código.

De todo modo, ao terminar, faça o commit e sincronize as suas alterações (use `passo1` no comentário do commit).

- Obs.: se precisar fazer novo commit com alguma correção, use o comentário `passo1 - correções`.

## Passo 2 - Primeiro Programa

Agora altere a classe `App`, que tem o método `main`. 
Dentro do método, crie um objeto do tipo da classe que você criou no passo anterior.
O objeto deve representar um corredor chamado `Tião` que ainda não percorreu nenhuma distância e nem gastou calorias.

Depois de criar o objeto exiba na tela as suas informações (nome, distância e calorias).

Obs.: a classe que representa o corredor não deve fazer nenhuma exibição de dados para o usuário.

Segue abaixo um exemplo de código que cria um objeto de uma classe e exibe informações na tela.

```java
// --- CÓDIGO DE EXEMPLO ---
public class Programa {

	public static void main(String[] args) {
		// Criamos objetos em Java com a palavra-chave new e 
        // usando o nome da classe (o construtor dela será chamado).
		NomeDaClasse nomeDaVariavel = new NomeDaClasse();
		
        // exemplo de uso de um método de acesso para obter o valor de um atributo do objeto.
		int a = nomeDaVariavel.getAtributoInteiro();
	
        // exemplo de exibição de informação no terminal
		System.out.println("Valor de a:" + a);
	}	
}
```


Teste suas alterações!
Depois, faça o commit e sincronize suas alterações (use `passo2` no comentário do commit).

## Passo 3 - Correndo

Vamos melhorar nossa classe. 

Crie na classe que representa o corredor um método chamado `correr`.
Neste método a distância deve ser aumentada em 500 unidades, representando 500 metros percorridos.
Além disso, as calorias gastas devem ser incrementadas considerando-se que são gastas 40 calorias para percorrer 500 metros.

Por fim, altere a classe `App` adicionando linhas para que o Tião corra uma vez e sejam exibidos novamente os dados dele.

Teste suas alterações!
Depois, faça o commit e sincronize suas alterações.

## Passo 4 - Obtendo dados do usuário

Altere a classe que representa o corredor, criando uma sobrecarga do método `correr` 
(ou seja, crie na classe um novo método também chamado `correr`).
- Este método deve receber por parâmetro a quantidade de vezes que o corredor vai correr.
- Para cada vez que ele for correr, deve ser chamado o método criado no passo anterior (para isso, use uma estrutura de repetição, como `for` ou `while`).
- Dessa forma, se o método for chamado passando-se o valor 4 como parâmetro, por exemplo, o corredor correrá 2000 metros.

Em seguida, altere a classe `App` de forma a obter do usuário a quantidade de vezes que o corredor deve correr, 
e fazendo com que o Tião corra essa quantidade de vezes (usando o método que você acabou de criar).
Ao final, exiba novamente os dados do corredor na tela.

Abaixo é apresentado um código de exemplo que mostra como utilizar um objeto da classe `Scanner` para obter
uma informação do usuário.


```java
// importamos a classe Scanner
import java.util.Scanner;

public class Programa {
	public static void main(String[] args) {
		// criamos um objeto Scanner que permite obter dados via terminal
		Scanner entrada = new Scanner(System.in);
		// usamos o método nextLine para obter uma informação com o objeto Scanner
        // (e, nesse caso, convertemos a string obtida para um valor inteiro)
		int a = Integer.parseInt(entrada.nextLine());

        // ...
		
        // Ao final precisamos nos lembrar de fechar o objeto Scanner utilizado para
        // liberar os recursos do objeto quando ele não é mais usado
        // Obs.: No VS Code, enquanto essa linha não é implementada é exibido um aviso (warning) de compilação: 
        // “Resource leak: 'entrada' is never closed". 
		entrada.close();
	}	
}
```

Teste suas alterações!
Depois, faça o commit e sincronize suas alterações.

## Passo 5 - Menu

Altere o programa do passo anterior de forma que ele exiba o menu abaixo e permita executar as ações do menu.

- Devem ser criados, na classe `App`, um método separado para exibição do menu e outro para tratar a opção de menu escolhida pelo usuário.
- Deixe comentado o código da classe `App` referente aos passos anteriores para que o professor possa fazer a correção dos mesmos.

```
Criar corredor
Correr
Exibir dados do corredor
Sair

  Digite sua opção:
```

Obs.: Neste passo, passa a fazer sentido que a classe `App` tenha um atributo da classe que representa o corredor.

Teste suas alterações!
Depois, faça o commit e sincronize suas alterações.

## Passo 6 - Evitando atributos e métodos estáticos

O fato do método `main` ser estático em Java, acaba levando a declarações de atributos e métodos estáticos 
dentro da mesma classe (no nosso caso, dentro da classe `App`). 
Mas, conceitualmente, muitas vezes não faz muito sentido que eles sejam estáticos.

Por isso, uma boa prática é deixar que a classe que tem o método `main` tenha apenas este método, e, dentro do método,
criar um objeto de uma outra classe que realmente é a classe principal do programa.

- Dessa forma, dentro desta outra classe principal os atributos e métodos não precisam ser declarados como estáticos. 
- Vamos fazer isso neste exercício seguindo as instruções abaixo.

Crie uma classe chamada `Principal` e leve para ela os atributos e métodos que antes estavam na classe `App` 
(exceto o método `main`, é claro). 
  - Deixe o loop do menu em um método chamado `executar`.
  - Lembre-se que os atributos e métodos da classe `Principal` **não devem** ser estáticos!

Altere o método `main` da classe `App` para que ele tenha apenas duas linhas de código:
  - Uma para declaração e criação de um objeto da classe `Principal`.
  - E outra para a chamada do método `executar` do objeto criado.

**Fica a dica**: Sempre adotaremos essa estratégia nos programas criados na disciplina.

Teste suas alterações!
Depois, faça o commit e sincronize suas alterações.

## Passo 7 - Trabalhando com vetores

Vamos agora alterar a classe `Principal` para que ela passe a trabalhar com um vetor de corredores de 4 posições.

Faça as alterações necessárias para tratar o vetor, dentre elas:

- Declare o atributo e crie-o no construtor.
- Na opção de criar corredor, um único corredor deve ser criado e acrescentado ao vetor.
  - O usuário poderá acessar essa opção várias vezes, para criar vários corredores.
  - Mas depois que o vetor estiver cheio, o usuário deve ser informado que não é possível criar mais corredores.
- Altere a opção correr do menu pedindo ao usuário qual corredor deve correr.
  - Para isso, peça o nome do corredor ao usuário e encontre-o no vetor.
- Por fim, altere a opção exibir do menu para que sejam exibas as informações de todos os corredores já criados.

**Dica**: lembre-se de testar todas as opções de menu sem ter criado nenhum corredor, tendo criado alguns e com o vetor cheio.
- O código deve ser cercado para evitar que ocorram erros em quaisquer situações.

Teste suas alterações!
Depois, faça o commit e sincronize suas alterações.


