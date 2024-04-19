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
