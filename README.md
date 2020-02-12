# Use Unsupervised Machine Learning to analyze what cryptocurrencies are on the trading market and how cryptocurrencies could be grouped toward creating a classification

## Objectives: The goals for this challenge are to:
- Prepare the data for dimensions reduction with PCA and clustering using K-means
- Reduce data dimensions using PCA algorithms from sklearn
- Predict clusters using cryptocurrencies data using the K-means algorithm form sklearn
- Create some plots and data tables to present your results

## Data Preprocessing
In this section, we load the information about cryptocurrencies from the provided CSV file and perform the following data preprocessing tasks:
- Remove all cryptocurrencies that aren’t trading
- Remove all cryptocurrencies that don’t have an algorithm defined
- Remove the IsTrading column
- Remove all cryptocurrencies with at least one null value
- Remove all cryptocurrencies without coins mined
- Store the names of all cryptocurrencies on a DataFramed named coins_name
- Remove the CoinName column
- Create dummies variables for all of the text features, and store the resulting data on a DataFrame named X
- Use the StandardScaler from sklearn
 
## Reducing Data Dimensions Using PCA
Use the PCA algorithm from sklearn to reduce the dimensions of the X DataFrame down to three principal components.

## Clustering Cryptocurrencies Using K-means
Use the KMeans algorithm from sklearn to cluster the cryptocurrencies using the PCA data.

Complete the following tasks:
- Create an elbow curve to find the best value for K, and use the pcs_df DataFrame
- Once the best value for K is defined, we run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data. 
- Use the pcs_df to run the K-means algorithm.
- Create a new DataFrame named “clustered_df,” that includes the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

## Visualizing Results
We created data visualizations to present the final results.
- Created a 3D scatter plot using Plotly Express to plot the clusters using the clustered_df DataFrame. And included the following parameters on the plot: hover_name="CoinName" and hover_data=["Algorithm"] to show this additional info on each data point.
- Used hvplot.table to create a data table with all the current tradable cryptocurrencies. The table has the following columns: CoinName, Algorithm, ProofType, TotalCoinSupply, TotalCoinsMined, and Class.
- Created a scatter plot using hvplot.scatter to present the clustered data about cryptocurrencies having x="TotalCoinsMined" and y="TotalCoinSupply" to contrast the number of available coins versus the total number of mined coins. Used the hover_cols=["CoinName"] parameter to include the cryptocurrency name on each data point.
- Created an additional scatterplot using hvplot.scatter with logarithmic axes
