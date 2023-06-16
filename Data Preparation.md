it's all in the name baby, you're preparing data for further manipulation or analysis by 'cleaning' it

it basically makes the data usable and sharpens it's relevancy by removing unnecessary shit

STEPS:
	- BASIC STEPS PRIOR
		- if the dataset has UIDS (unique ids) for rows, change this id column to dataframe row index
		- remove constant features (features with only one unique val, ie always true or something else), theyre irrelevant for data science
		- remove any feature not relevant to 'learning' from the data (eg name of database the row comes from)
		- remove redundant features that convey same info as another feature
		- date features cant be used as they are generally and need to be transformed
	- NEXT STEPS
		- take care of outliers (clamp, impute, drop or set to missing vals)
		- missing vals are imputed or the rows with them are dropped
		- any categorical descriptive feature is encoded:
			- [[One-Hot Encoding]] for nominals
			- [[One-Hot Encoding]] or [[Integer Encoding]] for ordinals
		- all descriptive features (numeric now due to above) are scaled
		- if there's a classification problem (a prob deciding on classification for certain data) its label encoded
		- if dataset has too many observations only a small subset is selected to be used in modelling
		- normalising any single numeric features that cover a wide range
		- before using any scikit learn modules, any [[Pandas]] series or [[Dataframes]] is converted to a [[NumPy]] array using the values method in [[Pandas]]
		
		
See also: 
- [[Data Science]]
- https://developers.google.com/machine-learning/data-prep/transform/transform-categorical
- [[Data Augmentation]]