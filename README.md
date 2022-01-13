	static Cliente cliente = new Cliente ("Amanda cunha", "Rua gamboa, 45");
	static Conta conta = new Conta (1, 200, 300, cliente);
	static Scanner teclado = new Scanner(System.in);
	
	public static void depositar() {
		System.out.println(" ====== DEPOSITO ====== ");
		System.out.println("INFORME O VALOR PARA DEPOSTIO: ");
		float valor = teclado.nextFloat();
		if(valor > 0 ) {
		    conta.depositar(valor);
		    System.out.println("DEPOSITO EFETUADO COM SUCESSO.");
	}else {
		System.out.println("O valor precisa ser positivo. ");
	   }
	}
	
	public static void sacar()  {
		System.out.println(" ====== SAQUE ====== ");
		System.out.println("INFORME O VALOR PARA SAQUE: ");
		float valor = teclado.nextFloat();
		if(valor > 0 ) {
		    conta.sacar(valor);
		    System.out.println("SAQUE REALIZADO COM SUCESSO.");
	}else {
		System.out.println("O valor precisa ser positivo. ");
	   }
	}

    public static void consultar() {
    	System.out.println("Seu saldo é " + conta.getSaldo());
    	
    }
	public static void main(String[] args) {
		int opcao = 0;
		System.out.println("Bem-vindo ao banco santander");
	
		do {
			
			System.out.println("1 - Depositar ");
			System.out.println("2 - Sacar ");
			System.out.println("3 - Consultar saldo ");
			System.out.println("0 - Sair ");
			opcao = teclado.nextInt();
			
			switch (opcao) {
			case 1:
				depositar();
				break;
			case 2:
				sacar();
				break;
			case 3:	
				consultar();
				break;
			case 0:
				break;
		    default:
		    System.out.println("Opcao invalida. ");
			}
		}while (opcao > 0);
		teclado.close();
		
		}
	}
