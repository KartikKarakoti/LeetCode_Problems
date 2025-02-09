class Solution:
    def readBinaryWatch(self, num: int) -> list[str]:
        times = []

        for h in range(12):
            for m in range(60):
                hOnes = bin(h).count('1')
                mOnes = bin(m).count('1')

                if hOnes + mOnes == num:
                    times.append(f"{h}:{m:02d}")

        return times
