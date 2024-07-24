public class Lista {
    protected Elo prim = null;

    public Lista() {
    }

    public boolean vazia() {
        return this.prim == null;
    }

    public void insere(int novo) {
        Elo p = new Elo(novo);
        p.prox = this.prim;
        this.prim = p;
    }

    public boolean busca(int elem) {
        for(Elo p = this.prim; p != null; p = p.prox) {
            if (p.dado == elem) {
                return true;
            }
        }

        return false;
    }

    public boolean buscaRecursiva(int elem) {
        return this.vazia() ? false : this.buscaRecursiva(elem, this.prim);
    }

    private boolean buscaRecursiva(int elem, Elo p) {
        if (p == null) {
            return false;
        } else {
            return p.dado == elem ? true : this.buscaRecursiva(elem, p.prox);
        }
    }

    public boolean remove(int elem) {
        Elo ant = null;

        Elo p;
        for(p = this.prim; p != null && p.dado != elem; p = p.prox) {
            ant = p;
        }

        if (p == null) {
            return false;
        } else {
            if (p == this.prim) {
                this.prim = this.prim.prox;
            } else {
                ant.prox = p.prox;
            }

            p = null;
            return true;
        }
    }

    public void imprime() {
        System.out.println("Elementos da lista:");

        for(Elo p = this.prim; p != null; p = p.prox) {
            System.out.print(p.dado + " ");
        }

        System.out.println();
    }

    public void imprimeRecursivo() {
        System.out.println("Elementos da lista:");
        if (!this.vazia()) {
            this.imprimeRecursivo(this.prim);
            System.out.println();
        }
    }

    private void imprimeRecursivo(Elo p) {
        if (p != null) {
            System.out.print(p.dado + " ");
            this.imprimeRecursivo(p.prox);
        }
    }

    public int tamanho() {
        int tam = 0;

        for(Elo p = this.prim; p != null; p = p.prox) {
            ++tam;
        }

        return tam;
    }

    public int tamanhoRecursivo() {
        return this.vazia() ? 0 : this.tamanhoRecursivo(this.prim);
    }

    private int tamanhoRecursivo(Elo p) {
        return p == null ? 0 : 1 + this.tamanhoRecursivo(p.prox);
    }

//    public static Lista constroi(int[] v, int n) {
//        Lista l = new Lista();
//        Elo ult = null;
//
//        for(int i = 0; i < n; ++i) {
//            Elo p = l.new Elo(v[i]);
//            if (l.prim == null) {
//                l.prim = p;
//                ult = p;
//            } else {
//                ult.prox = p;
//                ult = p;
//            }
//        }

//        return l;
//    }

    //Exercicio 2

    public int max(){
        if(this.vazia())
            return 0;
        return max(prim);
    }

    private int max(Elo p){
        if(p.prox == null){
            return p.dado;
        }
        else{
            int e = max(p.prox);
            if(e > p.dado)
                return e;
            else
                return p.dado;
        }

    }

    //Exercicio 3

    public Lista separa(int n){
        Lista lista2 = new Lista();
        Elo e = null;
        Elo antes = prim;
        for(Elo p = prim; p != null; p = p.prox){
            if(p.dado == n){
                e = p;
                break;
            }
            antes = p;
        }
        if(e == null){
            System.out.println("Esse número não existe na lista");
            return null;
        }
        antes.prox = null;
        lista2.prim = e;
        return lista2;
    }

    //Exercicio 4

    public static Lista concatena(Lista l1, Lista l2){
        Elo fim = l1.prim;
        if(l1.vazia()){
            System.out.println("A primeira lista está vazia");
            return l2;
        }
        else if(l2.vazia()){
            System.out.println("A segunda lista está vazia");
            return l1;
        }
        else{
            for(Elo p = l1.prim; p != null; p = p.prox){
                fim = p;
            }
            fim.prox = l2.prim;
        }
        return l1;
    }

    //exercicio 5

    public static Lista constroi(int [] v, int n){
        Lista lista = new Lista();
        if(n == 0){
            lista.prim = null;
        }
        else{
            Elo e = lista.new Elo(v[0]);
            lista.prim = e;
            for(int i = 1; i < n; i++){
                e.prox = lista.new Elo(v[i]);
                e = e.prox;
            }
        }
        return lista;
    }

    protected class Elo {
        protected int dado;
        protected Elo prox;

        public Elo() {
            this.prox = null;
        }

        public Elo(int elem) {
            this.dado = elem;
            this.prox = null;
        }

        public Elo(int elem, Elo proxElem) {
            this.dado = elem;
            this.prox = proxElem;
        }
    }
}
