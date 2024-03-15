# Livro-2

package main;

import java.util.Scanner;

public class Main {

   
    public static void main(String[] args) {
       Scanner scanner = new Scanner(System.in);

        // Ler informações do Autor
        System.out.println("Digite o nome do autor:");
        String nomeAutor = scanner.nextLine();
        System.out.println("Digite a data de nascimento do autor:");
        String dataNascimentoAutor = scanner.nextLine();
        System.out.println("Digite o CPF do autor:");
        String cpfAutor = scanner.nextLine();
        System.out.println("Digite o endereço do autor:");
        String enderecoAutor = scanner.nextLine();
        Autor autor = new Autor(nomeAutor, dataNascimentoAutor, cpfAutor, enderecoAutor);

        // Ler informações da Editora
        System.out.println("Digite o nome da editora:");
        String nomeEditora = scanner.nextLine();
        System.out.println("Digite a cidade da editora:");
        String cidadeEditora = scanner.nextLine();
        System.out.println("Digite o CNPJ da editora:");
        String cnpjEditora = scanner.nextLine();
        System.out.println("Digite o endereço da editora:");
        String enderecoEditora = scanner.nextLine();
        System.out.println("Digite o telefone da editora:");
        String telefoneEditora = scanner.nextLine();
        Editora editora = new Editora(nomeEditora, cidadeEditora, cnpjEditora, enderecoEditora, telefoneEditora);

        // Criar livro com construtor vazio
        Livro livro1 = new Livro();
        livro1.setISBN("1234567890123");
        livro1.setNome("Livro 1");
        livro1.setAnoPublicacao(2010);
        livro1.setAutor(autor);
        livro1.setEditora(editora);

        // Criar livro com construtor que recebe informações
        Livro livro2 = new Livro("9876543210987", "Livro 2", 2015, autor, editora);

        // Exibir informações dos livros criados
        System.out.println("Livro 1:");
        System.out.println("ISBN: " + livro1.getISBN());
        System.out.println("Nome: " + livro1.getNome());
        System.out.println("Ano de Publicação: " + livro1.getAnoPublicacao());
        System.out.println("Autor: " + livro1.getAutor().getNome());
        System.out.println("Editora: " + livro1.getEditora().getNome());

        System.out.println("\nLivro 2:");
        System.out.println("ISBN: " + livro2.getISBN());
        System.out.println("Nome: " + livro2.getNome());
        System.out.println("Ano de Publicação: " + livro2.getAnoPublicacao());
        System.out.println("Autor: " + livro2.getAutor().getNome());
        System.out.println("Editora: " + livro2.getEditora().getNome());
    }
    
}


package main;


public class Livro {
   private String ISBN;
    private String nome;
    private int anoPublicacao;
    private Autor autor;
    private Editora editora;

    public Livro() {
        // Construtor vazio
    }

    public Livro(String ISBN, String nome, int anoPublicacao, Autor autor, Editora editora) {
        this.ISBN = ISBN;
        this.nome = nome;
        this.anoPublicacao = anoPublicacao;
        this.autor = autor;
        this.editora = editora;
    }

    // Métodos getters e setters para Livro

    public void setISBN(String ISBN) {
        if (ISBN.length() == 13) {
            this.ISBN = ISBN;
        } else {
            System.out.println("ISBN inválido. Deve possuir 13 dígitos.");
        }
    }

    public String getISBN() {
        return ISBN;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getNome() {
        return nome;
    }

    public void setAnoPublicacao(int anoPublicacao) {
        if (anoPublicacao <= 2013) {
            this.anoPublicacao = anoPublicacao;
        } else {
            System.out.println("Ano de publicação inválido. Deve ser menor ou igual a 2013.");
        }
    }

    public int getAnoPublicacao() {
        return anoPublicacao;
    }

    public void setAutor(Autor autor) {
        this.autor = autor;
    }

    public Autor getAutor() {
        return autor;
    }

    public void setEditora(Editora editora) {
        this.editora = editora;
    }

    public Editora getEditora() {
        return editora; 
}}


package main;


public class Editora {
    private String nome;
    private String cidade;
    private String cnpj;
    private String endereco;
    private String telefone;

    public Editora(String nome, String cidade, String cnpj, String endereco, String telefone) {
        this.nome = nome;
        this.cidade = cidade;
        this.cnpj = cnpj;
        this.endereco = endereco;
        this.telefone = telefone;
    }

    // Métodos getters e setters para Editora
     public void setNome(String nome) {
        this.nome = nome;
    }

    public String getNome() {
        return nome;
    }

    public void setCidade(String cidade) {
        this.cidade = cidade;
    }

    public String getCidade() {
        return cidade;
    }

    public void setCnpj(String cnpj) {
        this.cnpj = cnpj;
    }

    public String getCnpj() {
        return cnpj;
    }

    public void setEndereco(String endereco) {
        this.endereco = endereco;
    }

    public String getEndereco() {
        return endereco;
    }

    public void setTelefone(String telefone) {
        this.telefone = telefone;
    }

    public String getTelefone() {
        return telefone;
}
}


package main;


public class Autor {
    private String nome;
    private String dataNascimento;
    private String cpf;
    private String endereco;

    public Autor(String nome, String dataNascimento, String cpf, String endereco) {
        this.nome = nome;
        this.dataNascimento = dataNascimento;
        this.cpf = cpf;
        this.endereco = endereco;
    }

    // Métodos getters e setters para Autor
     public void setNome(String nome) {
        this.nome = nome;
    }

    public String getNome() {
        return nome;
    }

    public void setDataNascimento(String dataNascimento) {
        this.dataNascimento = dataNascimento;
    }

    public String getDataNascimento() {
        return dataNascimento;
    }

    public void setCpf(String cpf) {
        this.cpf = cpf;
    }

    public String getCpf() {
        return cpf;
    }

    public void setEndereco(String endereco) {
        this.endereco = endereco;
    }

    public String getEndereco() {
        return endereco;
    }
}
