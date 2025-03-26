class Solution:
    def uniqueMorseRepresentations(self, words: List[str]) -> int:
        # Define the English alphabet
        letters = "abcdefghijklmnopqrstuvwxyz"
        
        # Define the corresponding Morse code representations
        morse_code = [".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", ".---", "-.-", ".-..", "--", "-.", "---", ".--.", "--.-", ".-.", "...", "-", "..-", "...-", ".--", "-..-", "-.--", "--.."]

        # Create a dictionary that maps letters to Morse code
        morse_dict = dict(zip(letters, morse_code))

        # Initialize a list to store words converted to Morse code
        words2 = []

        # Iterate through each word in the input list
        for word in words:
            # Initialize an empty string to store the Morse code for the current word
            k = ""
            
            # Iterate through each character in the current word
            for i in word:
                # Append the Morse code representation of the character to the string
                k += morse_dict[i]

            # Append the Morse code for the current word to the list
            words2.append(k) 

        # Return the count of unique Morse code representations
        return len(set(words2))
