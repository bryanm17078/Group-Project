# Group-Project
Create a web application that should:
1. Provide the user with background information about all known human protein kinases, e.g. their
name and gene symbol, the families they belong to, where in the cell they are typically found, and
the sites they are known to phosphorylate.
2. Allow the user to browse phosphosites in terms of their genomic location, neighbouring sequence,
etc.
3. Provide the user with background information about all known inhibitors of human protein
kinases, e.g. their name, chemical structure, and which kinases they are known to inhibit.
4. Allow the user to upload quantitative phosphoproteomics data of the format provided in example
file az20.tsv. The web application should then summarise this data 

I was part of a 4 person team and my role was to provide the statistical analysis for the quantitative phosphoproteomics data.
I intially cleaned the data,filtering any zero values (no data) and extracting significant values (p<0.05). Then I did some  Exploratory Data Analysis (EDA) to see the shape of the data and identify any trends.
After the EDA I decided that volcano plot would be the best way to display the data for the 1st part of the analysis as it showed the down and up regulated substrates and this information would be more valuable to the user than the other methods.
I also included the top 10 up and down regulated substrates as the volcano plot doesnt display this and it would also benefit the user.

The 2nd part of this analysis involved the calculation of the kinase scores.
Firstly I had to find the inhibited kinases by matching the substrate in the text file to the created database.
Kinase Score Formula
𝑠𝑐𝑜𝑟𝑒=((𝑠 ̅−𝑝 ̅)√𝑚)/𝛿
Where 𝑠 ̅  represents the mean log2 fold change of known 
substrates of the given kinase 
𝑝 ̅  represents the mean log2 change of all substrates in the dataset
 m represents the total number of  substrates that matched to a specific kinase
  δ denotes the standard deviation of the log2 fold change across all substrates in the dataset
(Wiredja, Koyutürk and Chance, 2017)
After doing that I used the formula above to calculated the kscore for each kinase.Then display them in  a barplot going from highest to lowest up and downregulated substrates. I also showed them the top 10 up and downregulated kinase so they can see this information and it may be of use to them.
