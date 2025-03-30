class Solution:
    def isNStraightHand(self, hand: List[int], groupSize: int) -> bool:
        if len(hand) % groupSize != 0:
            return False

        hand.sort()
        count = Counter(hand)
        
        for card in hand:
            if count[card] == 0:
                continue
            for i in range(groupSize):
                if count[card + i] > 0:
                    count[card + i] -= 1
                else:
                    return False
        return True
