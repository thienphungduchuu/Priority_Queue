import java.util.ArrayList;
import java.util.*;
import java.io.File;
import java.io.FileNotFoundException;


public class QueueMain {
	
	static ArrayList<Integer> value;
	static ArrayList<Integer> priority;
	private static int max;
	
	public static void swap() {
		for (int i = priority.size()-1; i > 0; i--) {
			Collections.swap(value, i, i-1);
			Collections.swap(priority, i, i-1);
		}	
	}
	
	public static void enqueue(String[] token) {
		int temp = 0;
		
		if (priority.size() == max) {
			for (int i = 0; i < priority.size()-1; i++) {
				if (priority.get(temp) < priority.get(i+1))
					temp = temp;
				else 
					temp = i+1;
			}
			
			if (Integer.parseInt(token[2]) > priority.get(temp)) {
				value.remove(temp);
				priority.remove(temp);
				value.add(Integer.parseInt(token[1]));
				priority.add(Integer.parseInt(token[2]));
				swap();
			}
		}
		else if (priority.size() > 0) {
			value.add(Integer.parseInt(token[1]));
			priority.add(Integer.parseInt(token[2]));
			swap();			
		}
		else {
			value.add(Integer.parseInt(token[1]));
			priority.add(Integer.parseInt(token[2]));
		}
	}
	
	public static void dequeue() {
		int temp = 0;
		
		if (priority.size() > 0) {
			for (int i = 0; i < priority.size()-1; i++) {
				if (priority.get(temp) > priority.get(i+1))
					temp = temp;
				else 
					temp = temp+1;
			}
			
			value.remove(temp);
			priority.remove(temp);
		}
	}
	
	public static void main(String[] args) throws FileNotFoundException {
		File inputFile = new File("C:\\Users\\thien\\Eclipse_Project\\Priority_Queue\\src\\TestFile");
		Scanner input = new Scanner(inputFile);
		value = new ArrayList();
		priority = new ArrayList();
		String[] token;
		
		while (input.hasNextLine()) {
			String inputString = input.nextLine();
			token = inputString.split(" ");
			
			if (token[0].equals("enqueue"))
				enqueue(token);
			else if (token[0].equals("dequeue"))
				dequeue();
			else 
				max = Integer.parseInt(token[0]);			
		}
		
		for (int i = 0; i < value.size(); i++) {
			System.out.print(value.get(i) + " ");
		}
		
	}
}
