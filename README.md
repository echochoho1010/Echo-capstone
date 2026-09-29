# Echo capstone

N-1 reports for two sort-center networks. Each report takes one sort center offline at a time and compares package flow with the intact baseline.

Both notebooks read `lane_summary.csv` and `path_summary.csv` from this repo, so they run in Colab without a local data folder. Charts use the daily average over the measured window: 14 days, 2026-05-04 inclusive to 2026-05-18 exclusive. A line is one facility connection, both directions combined. Color is packages per day on that connection.

## East Coast network

[Open `codebook/east_coast_n_minus_1.ipynb`](codebook/east_coast_n_minus_1.ipynb) in Colab from the badge at the top of the notebook.

Sort centers, north to south: BOSC, NJSC, PHSC, BASC, RMSC, CLTC, ATLS.

Scenario folders are directly under [`data/`](data/): `Baseline/` and one `{SC} down/` folder per center.

## Pro network

[Open `codebook/pro_network_n_minus_1.ipynb`](codebook/pro_network_n_minus_1.ipynb) in Colab from the badge at the top of the notebook.

This is the north-east demo (`northeastdemo`), the network from the "check pro" run. Sort centers, north to south: BOSC, NJSC, HASC, CBSC, CLTC, ATLS.

Scenario folders are under [`data/pro-network/`](data/pro-network/). They are not mixed into `data/Baseline/` because several hub names match the East Coast run, and the two simulations are different networks. On this network, CLTC traffic can still be delivered via CBSC. The other five outages drop the packages that have no remaining path to the destination.

## Requirements

pandas, numpy, and matplotlib. No parquet engine is required.
