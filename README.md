# atividade-1poo
import java.time.LocalDate;
import java.time.Period;

public class Pessoa {
    private String nome;
    private LocalDate dataNascimento;
    private int idade;

    public Pessoa() {
    }

    public Pessoa(String nome, LocalDate dataNascimento) {
        this.nome = nome;
        this.dataNascimento = dataNascimento;
        calcularIdade();
    }

    public Pessoa(String nome, LocalDate dataNascimento, int idade) {
        this.nome = nome;
        this.dataNascimento = dataNascimento;
        this.idade = idade;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public LocalDate getDataNascimento() {
        return dataNascimento;
    }

    public void setDataNascimento(LocalDate dataNascimento) {
        this.dataNascimento = dataNascimento;
        calcularIdade();
    }

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) {
        this.idade = idade;
    }

    private void calcularIdade() {
        if (dataNascimento != null) {
            idade = Period.between(dataNascimento, LocalDate.now()).getYears();
        }
    }

    public static void main(String[] args) {
        LocalDate dataNascimento = LocalDate.of(1990, 5, 15);
        Pessoa pessoa1 = new Pessoa("João", dataNascimento);
        System.out.println("Nome: " + pessoa1.getNome());
        System.out.println("Data de Nascimento: " + pessoa1.getDataNascimento());
        System.out.println("Idade: " + pessoa1.getIdade() + " anos");
    }
}
