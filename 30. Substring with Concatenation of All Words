class Solution:
    def findSubstring(self, s: str, words: List[str]) -> List[int]:
        n_word = len(words)
        n_char = len(words[0])
        word2freq = {}
        for word in words:
            if word in word2freq:
                word2freq[word] += 1
            else:
                word2freq[word] = 1

        all_start_ind = []
        for start_ind in range(n_char):
            curr_map = {}
            curr_total = 0
            excessive = False
            for i in range(start_ind, len(s), n_char):
                word = s[i:i+n_char]
                if word in word2freq: # a valid word for permutation 
                    curr_total += 1
                    if word in curr_map: # found valid word
                        curr_map[word] += 1
                        if curr_map[word] > word2freq[word]: 
                            excessive = word
                    else:
                        curr_map[word] = 1

                    earliest_ind = i - (curr_total-1)*n_char
                    while excessive:
                        earliest_word = s[earliest_ind: earliest_ind+n_char]
                        curr_map[earliest_word] -= 1
                        curr_total -= 1
                        if earliest_word == excessive:
                            excessive = False
                            break
                        earliest_ind += n_char
                    if curr_total == n_word:
                        earliest_ind = i - (n_word-1)*n_char

                        all_start_ind.append(earliest_ind)

                        earliest_word = s[earliest_ind: earliest_ind+n_char]
                        curr_total -= 1
                        curr_map[earliest_word] -= 1
                else:
                    curr_total = 0
                    curr_map = {}
        return all_start_ind
    
    def check_map_equal(self, curr_map, ref_map) -> bool:
        for word, freq in curr_map.items():
            if word not in ref_map or freq != ref_map[word]:
                return False
        return True
