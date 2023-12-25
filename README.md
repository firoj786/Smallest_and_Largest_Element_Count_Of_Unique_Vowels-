# Smallest_and_Largest_Element_Count_Of_Unique_Vowels-

1. Finding the Minimum and Maximum Values in an Array (Commented Out):

int[] arr = { 23, 36, -9, 12, 77, 53, -63, 74, 63, 90 };

    Creates an integer array named arr with the given values.

    Arrays.stream(arr).min().orElseThrow(() -> new IllegalArgumentException("Array is empty"));

    Uses a stream to find the minimum value in the array.

    orElseThrow ensures an exception is thrown if the array is empty.

    Arrays.stream(arr).max().orElseThrow(() -> new IllegalArgumentException("Array is empty"));

     Similarly, finds the maximum value in the array.

		int[] arr = { 23, 36, -9, 12, 77, 53, -63, 74, 63, 90 };
  
		int min = Arrays.stream(arr).min().orElseThrow(() -> new IllegalArgumentException("Array is empty"));
  
		int max = Arrays.stream(arr).max().orElseThrow(() -> new IllegalArgumentException("Array is empty"));
  
		System.out.println("Smallest Element :-" + min);
  
		System.out.println("Largest Element :-" + max);
  
  
--------------------------------------------------------------------------------------------------------

Counting Unique Vowels and Their Frequency:

    1. String inputStr = "I am an Alphabet!";

    Stores a string in the variable inputStr.
    
    inputStr.toLowerCase().chars().filter(c -> "aeiou".indexOf(c) != -1).distinct().count();
    
    Converts the string to lowercase.
    
    Creates a stream of characters.
    
    Filters only vowels using the filter method.
    
    Keeps only unique vowels using distinct.
    
    Counts the remaining characters using count.
    
    Stores the count in unqueVowelCount.
    
    inputStr.toLowerCase().chars().filter(c -> "aeiou".indexOf(c) != -1).mapToObj(c -> (char) c).collect(Collectors.groupingBy(c -> c, Collectors.counting()));
    
    Filters vowels from the string, similar to the previous step.
    
    Maps each character to a Character object using mapToObj.
    
    Collects the characters into a map, grouping them by character and counting their occurrences using Collectors.groupingBy and Collectors.counting.

    Stores the map in vowelFrequency.

    2. Printing Results:
    System.out.println("count of the unique vowels" + unqueVowelCount);

    Prints the count of unique vowels.

    System.out.println("Frequncy of each vowel:-" + vowelFrequency);

    Prints the map containing vowel frequencies.

    

	  	String inputStr = "I am an Alphabet!";
  
		long unqueVowelCount = inputStr.toLowerCase().chars().filter(c -> "aeiou".indexOf(c) != -1).distinct().count();
  
		System.out.println("count of the unique vowels" + unqueVowelCount);
  
		Map<Character, Long> vowelFrequency = inputStr.toLowerCase().chars().filter(c -> "aeiou".indexOf(c) != -1)
				.mapToObj(c -> (char) c).collect(Collectors.groupingBy(c -> c, Collectors.counting()));
    
		System.out.println("Frequncy of each vowel:-" + vowelFrequency);
