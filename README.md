# uriOnlineTeste
Exercício básico com tentativa de orientação a objeto
 
 package application;

import java.util.Scanner;

import entities.Products;;

public class Program {

	public static void main(String[] args) {
		double valorProduto;
		
		Scanner scan = new Scanner(System.in);

		System.out.println("Digite o codigo do Produto: ");
		int codProduto = scan.nextInt();
		System.out.println("Digite a quantidade de produtos: ");
		int quantProduto = scan.nextInt();


		Products products = new Products(codProduto, quantProduto) ;
		switch (codProduto) {
		
		case 1:
			valorProduto = 4;
			products = new Products(valorProduto, quantProduto);
			break;
		case 2:
			valorProduto = 4.50;
			products = new Products(valorProduto, quantProduto);
			break;
		case 3:
			valorProduto = 5.00;
			products = new Products(valorProduto, quantProduto);
			break;
		default:
			System.out.println("Erro ");
			break;
		}
		
		
		products.somaFinal();

		System.out.println(products.toString());
		scan.close();

	}

}

////////////////CLASSE

package entities;

public class Products {
	
	private int codProduto;
	private int quantProduto;
	private double valorProduto;
	
	public Products(double valorProduto, int quantProduto) {

		this.quantProduto = quantProduto;

		this.valorProduto = valorProduto;
	}

	public Products(int codProduto, int quantProduto) {
		this.quantProduto = quantProduto;
		this.codProduto = codProduto;
		
	}

	
	public int getCodProduto() {
		return codProduto;
	}


	public int getQuantProduto() {
		return quantProduto;
	}


	public double getValorProduto() {
		return valorProduto;
	}


	public double somaFinal() {
		
		return this.quantProduto * this.valorProduto;
		
	}
	
	public String toString() {
		
		return "Total: R$ "+
				String.format("%.2f", somaFinal());
		
	}

}


