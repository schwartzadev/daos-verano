# DAO Deployments Data Collection

This directory contains scripts and data for collecting DAO deployment information from various platforms. Data was last updated via DAO Analyzer on July 20, 2023.

## Data Schema

Each platform's data is collected into a standardized format with the following columns:

| Column | Description |
|--------|-------------|
| `platform` | Platform identifier |
| `platform_id` | Unique identifier within the platform |
| `name` | DAO name (optional) |
| `website` | DAO website URL (optional) |
| `additional` | Additional metadata like social links (optional) |
| `votes_count` | Number of votes in the deployment* |
| `proposals_count` | Number of proposals in the deployment |

\* Note: Vote counting varies by platform:
- Snapshot: Sum of total votes
- DAOstack, Aragon, DAO Haus: Total votes including duplicates from same voter

## Types

Currently collecting data from:

- [Snapshot](https://snapshot.org/#/) (2,404 DAOs)
- [Tally](https://www.tally.xyz/)
- [Realms](https://realms.today/) (18 DAOs)
- [Aragon](https://aragon.org/) (84 DAOs, via DAO Analyzer)
- [DAOstack](https://daostack.io/) (12 DAOs, via DAO Analyzer) 
- [DAO Haus/Moloch](https://daohaus.club/) (36 DAOs, via DAO Analyzer)

## Platforms Under Consideration

Single-organization platforms to potentially add:
- Aave (on-chain voting)
- Uniswap (on-chain voting, [governance portal](https://app.uniswap.org/#/vote))
- Compound Finance (on-chain voting)

## Unsupported Platforms

The following platforms are currently not included:

| Platform | Count | Reason |
|----------|--------|--------|
| Governor | 62 | No public API |
| AssetsOnly | 30 | Platform not found |
| Substrate | 27 | No API (has [directory](https://substrate.io/ecosystem/projects/)) |
| OpenLaw | 3 | Too few DAOs, n<10 |
| Colony | 2 | Too few DAOs, n<10 |

## Notes

- Previous Snapshot limitation of 15k deployments has been resolved as of July 20, 2023
- Messari data includes additional unstructured content (forums, Notion pages, etc.)