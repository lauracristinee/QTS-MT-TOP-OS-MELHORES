# QTS-MT-TOP-OS-MELHORES
Os melhores 

Software - Eclipse exemplo carro 
criar uma classe Carro e acrescentar:

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
		if (ligado = true) {
		this.veloAtual += valor;
		}
		if (veloAtual <= veloMax) {
			return true;
		}
		else {
			return false;
		}
   }
	
	//freio 
	 public boolean frear(int valorfrear) {
		 if (ligado = true) {
		 this.veloMax -= veloAtual;
		 }
		 if (veloAtual <= veloMax) {
			 return false;
		 }
		 else {
			 
		 }
		return ligado;
	 }
}

depois que criar e fazer tudo isso, criar uma classe principal para testar todos os parametros estabelicidos na classe Carro
