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

## CÓDIGO ARRUMADO (TENTATIVA)

        public class Carro {
    public String marca;
    public String modelo;
    public int veloatual;
    public double velomax;
    public boolean ligado;

    public void ligar() {
        this.ligado = true;
    }

    public void desligar() {
        this.ligado = false;
    }

	    
     /*Pensamento: Faz o calculo e verifica se a velocidade atual+aceleração vai passar ou nao da velocidade permitida, se for menor ai sim o vai ser somado e retornar true */

    public boolean acelerar(int aceleracao) {
        if (ligado = true) {
            if ((veloatual + aceleracao) <= velomax) { 
                this.veloatual += aceleracao; 
                return true;
		
            } else {
                return false;
            }

// Outro metodo 

    public boolean frear(int frear) {
    if ((veloatual - frear) > 0 ) {
        this.veloatual -= frear; // Se não for negativa ai sim pode fazer o calculo, retornando true
            return true;
	    
        } else {
            this.veloatual = 0;  se for igual a zero, retorna falso   
            return false;
        }
    }
}
