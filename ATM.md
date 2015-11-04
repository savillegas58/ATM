# ATM
package edu.sbcc.cs105;

import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		AtmPin ap = new AtmPin();
		while (ap.attempts <= 3) {
			System.out.println("Input your PIN : ");
			String code = in.next();

			if (ap.acceptPinCode(code)) {
				System.out.println("Your PIN is correct");
				ap.resetPasswordAttempts();
			} else if (ap.isBadPassword(code)) {
				System.out.println("Your PIN is incorrect");
				if (ap.isBlocked()) {
					System.out.println("You have been blocked");

				}

			}
			System.out.print(ap.attempts);
		}
		in.close();
	}

}
