# Aula-22-10-2025
Lista
public class Pessoa {
    private String nome;

    public Pessoa(String nome){
        this.nome = nome;
    }

    public String getNome(){
        return nome;
    }

    @Override
    public String toString() {
        return nome;
    }
}


import java.util.ArrayList;

public class ListaFesta {

    
    private static ListaFesta instance;

    
    private ArrayList<Pessoa> lista;

    
    private ListaFesta(){
        lista = new ArrayList<Pessoa>();
        lista.add(new Pessoa("Luisa"));
        lista.add(new Pessoa("José"));
        lista.add(new Pessoa("Maria"));
        lista.add(new Pessoa("João"));
    }

    
    public static ListaFesta getInstance(){
        if(instance == null){
            instance = new ListaFesta();
        }
        return instance;
    }

    
    public void listarPessoas(){
        System.out.println("==== Lista da Festa ====");
        for(Pessoa p : lista){
            System.out.println(p);
        }
    }
}

public class Main {
    public static void main(String[] args) {

        ListaFesta festa = ListaFesta.getInstance(); 
        festa.listarPessoas();
    }
}
