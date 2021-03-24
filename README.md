package arvorebinary;
import tree.arvorebinary.ArvoreBinary;

public class ArvoreBinary_Teste {
    static ArvoreBinary bt;
    
    
    public static int [] encontrarNumerosPrimos (int size){
        int[] primos = new int[size];
        
        
        int valor = 2, i;
        boolean eehPrimo;
        int contagem = 0;
        while (contagem < size){
            eehPrimo = true;
            for (i = (valor - 1); i > 1; i--){
                if (valor % i == 0){
                    eehPrimo = false;
                    break;
                }
            }
            if (eehPrimo)
                primos [contagem++] = valor;
            valor++;
            
        }
        return primos;
    }
    
    public static void main (String[] args){
        bt = new ArvoreBinary();
        
        
        int[] primos;
        //Letra A
        primos = encontrarNumerosPrimos(1000);
        for (int value: primos){
            bt.insert(value);
        }
        
        //Letra B
        System.out.println("Pre:.\t" + bt.printPre());
        System.out.println("In:.\t" + bt.printIn());
        System.out.println("Pos:.\t" + bt.printPos());
        
        //Letra C
        int size = bt.getSize();
        for (int i = 0; i < size; i += 100){
            bt.remove(primos[i]);
            
        }
        
        //Letra D
        System.out.println("Pre:.\t" + bt.printPre());
        System.out.println("In:.\t"+ bt.printIn());
        System.out.println("Pos:.\t"+ bt.printPos());
    }
    
}

