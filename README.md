# Relational Causal Discovery (RCD)



This is a copy of source code for the causal structure learning algorithm called Relational Causal Discovery (RCD). This copy is created primarily to provide updated support for the dependencies. The original software was written quite some time ago. As a result, some of the dependency packages doesn't work as expected. This updated configuration is tested in Mac OS X Mojave. The original software is available [here](https://kdl-umass.github.io/relational_causal_discovery.html).

Please refer to the [changes](https://github.com/ragib06/RCD/blob/master/changes.md) file to review the changes made to original software.


---
Relational Causal Discovery (RCD) is a sound and complete algorithm for learning causal models from relational data. RCD employs a novel rule, called relational bivariate orientation, that can can detect the orientation of a bivariate dependency with no assumptions on the underlying distribution. Combined with relational extensions to the rules utilized by the PC algorithm[1], RCD is provably sound and complete under the causal sufficiency assumption. Given a database and schema, RCD outputs a partially directed model that represents the equivalence class of statistically indistinguishable relational causal models.

Please checkout [RCD-Light](https://github.com/sanghack81/rcd-light), which is the successor of RCD.


## Requirements

- Python 3.6

- There are two options to install all the required python packages
	1. **pip**
	
		```pip install -r requirements.tx```
		
		If you face any issue with the package *psycopg2* install it through conda:
		
		```conda install psycopg2```
		
	2. **Anaconda**
	
		```conda env create -f conda_venv_rcd.yml```
		
		It will create a conda venv named "rcd" which will contain all the required packages. You need to activate the venv before using it:
		
		```source activate rcd```
		
- [Mac OS X] You need to install [Postgres.app](https://postgresapp.com/). For managing Postgres databases [Postico](https://eggerapps.at/postico/) is a nice GUI tool.


## Running examples:

- Run Oracle example:

	```python src/runOracleRCD.py```

- Run Database Example: 
	- Configure Postgres database and load the dump file **src/rcd-test-data.sql**
	
	- Then run the following: 

		```python src/runDatabaseRCD.py```

----------
**References**

Sanghack Lee and Vasant Honavar (2016) On Learning Causal Models for Relational Data.  In *Proceedings of Thirtieth AAAI Conference on Artificial Intelligence (AAAI 2016),* *To Appear*.

Marc Maier, Katerina Marazopoulou, David Arbour, and David Jensen (2013) A sound and complete algorithm for learning causal models from relational data. In *Proceedings of the Twenty-Ninth UAI Conference on Uncertainty in Artificial Intelligence, (UAI-2013)*
