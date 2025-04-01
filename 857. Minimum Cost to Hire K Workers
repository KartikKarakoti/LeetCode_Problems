class Solution:
    def mincostToHireWorkers(
        self, quality: List[int], wage: List[int], k: int
    ) -> float:
        nQuality = len(quality)
        minCost = float("inf")
        qualityTillNow = 0
        wageQualityRatio = []

        for i in range(nQuality):
            heappush(wageQualityRatio, (wage[i] / quality[i], quality[i]))

        highQualityWorkers = []

        for i in range(nQuality):
            ratio, qua = heappop(wageQualityRatio)
            qualityTillNow += qua
            heappush(highQualityWorkers, -qua)

            if len(highQualityWorkers) > k:
                qualityTillNow += heappop(highQualityWorkers)

            if len(highQualityWorkers) == k:
                minCost = min(minCost, qualityTillNow * ratio)

        return minCost
