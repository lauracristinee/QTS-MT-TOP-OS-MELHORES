package atividadeCarro_turmaAzul;

public class Carro {
	//atributos
	public String marca;
	public String modelo;
	public int veloAtual;
	public double veloMax;
	public boolean ligado;


	//métodos
	// ligar
	public void ligar() {
		this.ligado = true;
	}

	// desligar
	public void desligar() {
		this.ligado = false;
	}

	// acelerar
	public boolean acelerar(int valor) {
		if (ligado == true) {
			if ((veloAtual + valor) <= veloMax ){
				this.veloAtual += valor;
				return true;
			}
			else {
				return false;
			}
		}
		
		return false;
	}

	//freio 
	public boolean frear(int valorfrear) {
		if ((veloAtual - valorfrear) > 0) {
			this.veloAtual -= valorfrear;
			return true;
		}
		 else {
			this.veloAtual = 0 ;
		}
		return false;
	}
	
}

> PRINCIPAL
package atividadeCarro_turmaAzul;

//testes
public class Principal {
	public static void main(String[] args) {
		Carro cc1 =  new Carro();


		cc1.modelo = "modelo Híbrido";
		cc1.marca = "Toyota";
		cc1.veloMax = 250;

		
//testes manuais - ARRUMADO MUITO TOPP
		
		//arrumar o ligar, sem a variável sucesso
		//ligar
		System.out.println("Teste 1 - ligar");
		cc1.ligar();
		boolean sucesso = (true);
		System.out.println("O carro está ligado? " + sucesso);
		
		//desligar
		System.out.println("Teste 2 - desligado");
		cc1.ligar();
		sucesso = (false);
		System.out.println("O carro está ligado? " + sucesso);
		
		//acelerar 
		System.out.println("Teste 3 - acelerar");
		boolean sucesso2 = cc1.acelerar(100);
		System.out.println("O " + cc1.marca + cc1.modelo + " está a " + cc1.veloAtual + "km/h");
		System.out.println("O carro ultrapassou a velocidade? " + sucesso2);

		
		System.out.println("Teste 4 - acelerar ultrapassando");
		boolean sucesso3 = cc1.acelerar(2500);
		System.out.println("O " + cc1.marca + cc1.modelo + " está a " + cc1.veloAtual + "km/h");
		System.out.println("O carro ultrapassou a velocidade? " + sucesso3);

		
		
		//frear
		System.out.println("Teste 5 - frear");
		boolean sucesso4 = cc1.frear(10);
		System.out.println("O " + cc1.marca + cc1.modelo + " está a " + cc1.veloAtual + "km/h");
		System.out.println("O carro freou? " + sucesso4);

		
		System.out.println("Teste 6 - frear até negativo");
		boolean sucesso5 = cc1.frear(280);
		System.out.println("O " + cc1.marca + cc1.modelo + " está a " + cc1.veloAtual + "km/h");
		System.out.println("O carro ultrapassou a freagem? " + sucesso5);
			
}
}




// dia 03 - pom
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>etec.com</groupId>
  <artifactId>conta_corrente_etim_azul</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  
<!-- mae das dependencias -->
  
  <dependencies> 
    <dependency>
       <groupId>junit</groupId>
       <artifactId>junit</artifactId>
  	   <version>4.13.2</version>
    </dependency>
  </dependencies>
</project>



//classe conta
package conta_corrente_etim_azul;

public class ContaCorrente {
	public String nomeTitular;
	public double saldo;
	
	public void depositar(double valor) {
		this.saldo += valor;
	}
	
	public boolean sacar(double valor) {
		if(this.saldo < valor) {
			return false;
		}
		this.saldo -= valor;
		return true;
	}
	
	public boolean tranferir(double valor, ContaCorrente contaDestino) {
		if(this.saldo < valor) {
			return false;
		}
		this.saldo -= valor;
		contaDestino.saldo += valor;
		return true;
	}

}

//testes
package conta_corrente_etim_azul;

import static org.junit.Assert.assertEquals;

import org.junit.Test;

public class ContaCorrenteTest {
	final double VARIACAO = 0.1; 
	// magic number - ao inves de colocar um número solto, atribuimos esse valor, declaramos como final, para podermos reutilizar 

	
	//teste
	@Test
	public void testeDepositar() {
		//cenário
		ContaCorrente cc = new ContaCorrente ();
		cc.depositar(100);
		assertEquals(100, cc.saldo, VARIACAO);
		// comparando doubles, variação para compensar.
		cc.depositar(100);
		assertEquals(200, cc.saldo, VARIACAO);
		cc.depositar(100);
		assertEquals(300, cc.saldo, VARIACAO);
		//tudo isso esta dentro de um teste , para outros o @
	}
	
	@Test
	public void testeSacar() {
		//cenário
		ContaCorrente cc = new ContaCorrente ();
		cc.depositar(300);
		//ação
		cc.sacar(10);
		//verificação
		assertEquals(290, cc.saldo, VARIACAO);
		// comparando doubles, variação para compensar.
		cc.sacar(100);
		assertEquals(190, cc.saldo, VARIACAO);
		cc.sacar(100);
		assertEquals(90, cc.saldo, VARIACAO);
	}
	
	@Test
	public void testeTransferir() {
		//cenário
		ContaCorrente cc1 = new ContaCorrente ();
		ContaCorrente cc2 = new ContaCorrente ();
		
		cc1.depositar(200);
		//ação
		cc1.tranferir(50,cc2);
		assertEquals(150, cc1.saldo, VARIACAO);	
		assertEquals(50, cc2.saldo, VARIACAO);

	}
}

