# Auto-Complete-
Auto text completion program which simply suggests the most likely next letter from user input.
//Lauren Acosta
import java.util.Stack;

public class WordScramble {

	public static String encode(String str)
	{
		//two arrays to separate consonants and vowels 
		char[] consonants = new char[4];
		char[] vowels = new char[4];
		// counters to keep track of indexes in array
		int vowelIndex = 0, consIndex = 0;
		// empty string to store space for output 
		String product = "";
		//create empty stack
		Stack<Character> stack = new Stack<Character>();
		char character, poppedChar;
		int i, j;

		//iterates through length of string input until 2 is reach, to indicate the first group
		for(i=0; i<str.length(); i++)
		{
			// once 2 is reached pop the character from the stack 
			character = str.charAt(i);
			if (character == '2')
			{
				poppedChar = stack.pop();
				while(poppedChar != '1')
				{
					//compare each popped character and determine if its a vowel or consonant
					//then the character is stored accordingly 
					if (isVowel(poppedChar) == 1)
					{
						vowels[vowelIndex] = poppedChar;
						vowelIndex++;
					}
					else
					{
						consonants[consIndex] = poppedChar;
						consIndex++;
					}
					poppedChar = stack.pop();
				}
				
				//Pulls characters starting at the end of consonant array and concatenates to output string
				for (j = consIndex - 1; j >= 0; j--)
				{
					product += consonants[j];
				}
				//Pulls characters starting at the end of vowel array and concatenates to output string
				for (j = vowelIndex - 1; j >= 0; j--)
				{
					product += vowels[j];
				}
				
				//resets the arrays and values 
				vowelIndex = 0;
				consIndex = 0;
				consonants = null;
				vowels = null;
				consonants = new char[4];
				vowels = new char[4];
				
			}
			else
			{
				
				stack.push(character);
			}
		}

		return product;
	}
	
	// takes the character as input and determines if its a vowel or not 
	public static int isVowel(char letter)
	{
		if (letter == 'a' || letter == 'e' || letter == 'i' || letter == 'o' || letter == 'u')
				return 1;
		return 0;
	}

	public static void main(String[] args) {

		System.out.println(encode("1cat2"));
		System.out.println(encode("11top2e1cat22"));
		System.out.println(encode("111tom2op2it2"));
		System.out.println(encode("11top2i1tom22"));

	}

}
