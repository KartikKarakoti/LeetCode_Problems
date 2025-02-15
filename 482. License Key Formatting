class Solution:
    def licenseKeyFormatting(self, s: str, k: int) -> str:
        # Remove all dashes and convert the string to uppercase
        string = s.replace('-', '').upper()

        # Determine the size of the first group
        mod = len(string) % k

        # Use a list for efficient string building
        parts = []

        # Add the first group if it is not empty
        if mod > 0:
            parts.append(string[:mod])

        # Add the remaining groups
        for i in range(mod, len(string), k):
            parts.append(string[i:i+k])

        # Join parts with a dash
        return '-'.join(parts)
      
