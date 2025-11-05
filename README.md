# ChessViz

**_Mapping Lichess Players by Their Opening Choice_**

Go to the [Interactive Visualization](https://suji04.github.io/ChessViz/)

## Methodology
(Code coming soon)
- Noise reduction
  - Ignore games with average Elo (white Elo + black Elo / 2) <1000 and time control <10 minutes
  - Ignore players with <20 games
  - Ignore games with irregular openings (ECO code A00)
- For each player, compute the distribution of openings played. This will yield a player × ECO matrix (≈500 ECO codes) counting openings as white and black. 
- Normalize rows to get per-player opening probability vectors.
- Compute cosine k-NN graph using faiss
- Detect player communities with the Leiden algorithm
- Reduce dimensions to 3D with UMAP
- Visualize randomly sampled 100k players for clarity
 

## Dataset
[https://database.lichess.org](https://database.lichess.org/) (Jan 2025)

## Tools used
- `python` - scripting
- `python-chess` - parsing the games
- `faiss-cpu` - k-NN
- `leidenalg` - community detection
- `umap` - dimensionality reduction
- `plotly` - visualization

## Animated Map
![animated map](https://github.com/Suji04/ChessViz/blob/main/animated_lichess_map.gif)





