import pandas as pd

def order_scores(scores: pd.DataFrame) -> pd.DataFrame:
    # First method
    score_unique = sorted(scores['score'].unique(), reverse=True)
    dct = {score_unique[i]: i + 1 for i in range(len(score_unique))}
    scores = scores.sort_values('score', ascending=False)
    scores['rank'] = scores['score'].map(lambda p: dct[p])
    return scores[['score', 'rank']]

    #Second method
    rank = scores['score'].rank(method='dense', ascending=False)
    scores['rank'] = rank
    return scores[['score', 'rank']].sort_values('rank')
