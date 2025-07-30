# DAOs Ecosystem Census

A comprehensive data collection and analysis project for Decentralized Autonomous Organizations (DAOs) across multiple platforms. This repository contains tools and scripts to gather, process, and analyze data about DAO deployments, proposals, and voting patterns.

## About This Project

This codebase is a data collection and analysis framework designed to study
the DAO ecosystem across multiple platforms. It is designed to gather, processes,
and standardize data about DAO deployments, proposals, and voting patterns
to enable comprehensive analysis of DAO governance.

## Academic Context

This work is part of a doctoral thesis research project at Universidad
Complutense de Madrid (UCM), focusing on the empirical analysis of
decentralized governance systems.

The collected data and analysis tools support research into DAO participation
patterns, governance effectiveness, and cross-platform comparisons.

## Recomended citation

If you use this code, dataset, or associated publication in your work, please cite the following:

### Code
Schwartz, A. & Peña-Calvin, A. *DAO Ecosystem Census*. GitHub, 2024. Available at: https://github.com/Grasia/dao-ecosystem-census

### Dataset
Census of the Ecosystem of Decentralized Autonomous Organizations 
DOI: 10.5281/zenodo.10794915
Link: https://zenodo.org/records/10794916 
Example citation:  
Peña-Calvin, A., Arroyo, J., Schwartz, A., Hassan, S., & Davó, D. *Census of the Ecosystem of Decentralized Autonomous Organizations*. Zenodo, 2024. DOI: https://doi.org/10.5281/zenodo.10794916

### Publication
Peña-Calvin, A., Arroyo, J., Schwartz, A., Hassan, S. 2024. *Concentration of Power and Participation in Online Governance: the Ecosystem of Decentralized Autonomous Organizations*. In Companion Proceedings of the ACM Web Conference 2024 (WWW '24). Association for Computing Machinery, New York, NY, USA, 927–930. https://doi.org/10.1145/3589335.3651481

Please cite the code, dataset and/or publication depending on your use case:
> - **If you use the dataset** → cite the dataset and the publication (and optionally the code).
> - **If you use the results, methods, or analysis in the paper** → cite the publication.
> - **If you use or modify the code** → cite the GitHub repo and the publication.

## Quick Start Guide

1. Clone the repository:
```bash
git clone https://github.com/Grasia/dao-ecosystem-census
cd dao-ecosystem-census
```

2. Install dependencies:
- Python 3.8+
- Jupyter Notebooks
- Node.js (required for Realms data collection)
- Required Python packages (see `requirements.txt`)

3. Configure platform-specific settings:
- Set up API keys where required (e.g., Snapshot, Tally)
- Configure data collection parameters in respective platform directories

4. Run data collection:
- Each platform has its own collection script in its respective directory
- Follow platform-specific README files for detailed instructions

## Technical Details

### Data Collection Architecture

The project collects data from multiple DAO platforms and standardizes it into a common schema for analysis. The data collection is organized into three main components:

1. **Deployments**: Information about DAO deployments across platforms
2. **Proposals**: Proposal data from each DAO
3. **Votes**: Voting records for each proposal

### Supported Platforms

Currently collecting data from:
- Aragon
- DAOstack
- Moloch/DAOhaus
- Realms
- Snapshot
- Tally

Data sources:
- Direct API access (Snapshot, Tally, Realms)
- [DAO Analyzer dataset](https://www.kaggle.com/datasets/daviddavo/dao-analyzer) (Aragon, DAOstack, DAOhaus)
- [Realms JS SDK](https://www.npmjs.com/package/@solana/spl-governance), now legacy, see [docs](https://docs.realms.today/sdk)

### Data Schema

#### Deployments
- platform
- platform_id
- name
- website
- votes_count
- proposals_count
- additional (may contain website, social info)

#### Proposals
- platform
- platform_deployment_id
- proposal_id
- author
- date
- votes_count

#### Votes
- platform
- platform_deployment_id
- proposal_id
- vote_id
- voter
- date
- choice
- weight

## Technical Implementation

### Project Structure
```
daos-verano/
├── deployments/      # Platform-specific deployment data collection
├── proposals/        # Proposal data collection scripts
├── votes/            # Voting data collection and processing
├── organizations/    # Organization data processing
└── parquet_versions/ # Data versioning and cleanup
```

### Data Collection Process

1. **Platform-specific Collection**: Each platform has custom collectors
based on available APIs/data sources
2. **Data Standardization**: Raw data is transformed into a common schema
3. **Data Validation**: Automated checks ensure data consistency
4. **Storage**: Data is stored in Parquet format for efficient processing

### Running the Collection

Each platform has its own code/process for collecting data, according to
various factors, including:

- API availability and rate limits
- Data volume and structure
- Platform-specific authentication requirements

See each platform's directory for specific collection instructions.

## Data Collection Dates

Data was collected during June and July of 2023:
- Snapshot: June 23-27, 2023
- DAO Analyzer data: July 20, 2023
- Realms: July 12, 2023
- Tally: July 18, 2023

## Authorship and License

* **Corresponding Author**: Andrea Peña Calvin
* **Contact**: andpen03@ucm.es
* **Institution**: Universidad Complutense de Madrid (UCM)
* **Additional Author**: [Andrew Schwartz](https://aschwartz.me/)
* **License**: MIT

This work was developed as part of a doctoral thesis at the [Universidad Complutense de Madrid](https://www.ucm.es/).

## References

- [DAO Analyzer Scripts](https://github.com/Grasia/dao-analyzer/blob/master/cache_scripts/README.md)
- [DAO Analyzer Dataset](https://www.kaggle.com/datasets/daviddavo/dao-analyzer)
