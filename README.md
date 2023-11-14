# CardNumberGen16
credit cards number generation


public class CardNumberGen {

	public static void main(String[] args) {
		

		long n = 654321400000001L;
		for (int i = 1; i <=2; i++) {
			System.out.println("Num " + n);
			int ckdigit = checkSumDigit(Long.toString(n));
			System.out.println("ckdigit " +n+ckdigit);
			n++;
		}
	}

	public static int checkSumDigit(String x) {
		int sum = 0, res;
		for (int i = 0; i < x.length(); i++) {
			if (i % 2 == 0) {
				res = (x.charAt(i) - '0') * 2;
				sum += res > 9 ? res / 10 + res % 10 : res;
			} else {
				sum += (x.charAt(i) - '0');
			}
		}
		int j = sum % 10;
		return j == 0 ? 0 : 10 - j;
	}

}
