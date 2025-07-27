class Atleta {
    constructor(nome, idade, peso, altura, notas) {
        this.nome = nome;
        this.idade = idade;
        this.peso = peso;
        this.altura = altura;
        this.notas = notas;
    }

    obtemNomeAtleta() {
        return this.nome;
    }

    obtemIdadeAtleta() {
        return this.idade;
    }

    obtemPesoAtleta() {
        return this.peso;
    }

    obtemAlturaAtleta() { 
        return this.altura;
    }

    obtemNotasAtleta() {
        return this.notas;
    }

    calculaCategoria() {
        if (this.idade >= 9 && this.idade <= 11) {
            return "Infantil";
        } else if (this.idade >= 12 && this.idade <= 13) {
            return "Juvenil";
        } else if (this.idade >= 14 && this.idade <= 15) {
            return "Intermediário";
        } else if (this.idade >= 16 && this.idade <= 30) {
            return "Adulto";
        } else {
            return "Sem categoria";
        }
    }

    calculaIMC() {
        // imc = peso / (altura x altura)
        return this.peso / (this.altura * this.altura);
    }

    calculaMediaValida() {
        
        let notasOrdenadas = [...this.notas];

        notasOrdenadas.sort((a, b) => a - b);
        let notasValidas = notasOrdenadas.slice(1, 4);

        let somaNotas = 0;
        notasValidas.forEach(nota => {
            somaNotas += nota;
        });

        if (notasValidas.length === 0) {
            return 0;
        }
        return somaNotas / notasValidas.length;
    }

    obtemCategoria() {
        return this.calculaCategoria();
    }

    obtemIMC() {
        return this.calculaIMC();
    }

    obtemMediaValida() {
        return this.calculaMediaValida();
    }

    exibeInformacoes() {
        console.log(`Nome: ${this.obtemNomeAtleta()}`);
        console.log(`Idade: ${this.obtemIdadeAtleta()}`);
        console.log(`Peso: ${this.obtemPesoAtleta()}`);
        console.log(`Altura: ${this.obtemAlturaAtleta()}`);
        console.log(`Notas: ${this.obtemNotasAtleta().join(',')}`);
        console.log(`Categoria: ${this.obtemCategoria()}`);
        console.log(`IMC: ${this.obtemIMC()}`);
        console.log(`Média válida: ${String(this.obtemMediaValida()).replace('.', ',')}`);
        console.log('');
    }
}

