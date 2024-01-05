Hi, you just got hired at the Census Bureau, which collects census data and creates interesting visualizations and insights from it.

The person who had your job before you left you all the data they had for the most recent census. It is in multiple csv files. They didn’t use pandas, they would just look through these CSV files manually whenever they wanted to find something. Sometimes they would copy and paste certain numbers into Excel to make charts. The thought of it makes you shiver. This is not scalable or repeatable.

Your boss wants you to make some scatterplots and histograms by the end of the day. Can you get this data into pandas and reasonable shape so that you can make these histograms? Inspect the Data! 

- The first visualization your boss wants you to make is a scatterplot that shows the average income in a state vs the proportion of women in that state.
- Open some of the census CSV files in the navigator. How are they named? What kind of information do they hold? Will they help us make this graph?
- It will be easier to inspect this data once we have it in a data frame. You can’t even call .head() on these csvs! How are you supposed to read them?
- Using glob, loop through the census files available and load them into DataFrames or maybe load them separately in different DataFrames. Then, concatenate all of those DataFrames together into one DataFrame, called something like us_census.
- Look at the .columns and the .dtypes of the us_census DataFrame. Are those datatypes going to hinder you as you try to make histograms?
- Look at the .head() of the DataFrame so that you can understand why some of these dtypes are objects instead of integers or floats.
- Start to make a plan for how to convert these columns into the right types for manipulation.
- Look at the GenderPop column. We are going to want to separate this into two columns, the Men column, and the Women column. Split the column into those two new columns using str.split and separating out those results. Convert both of the columns into numerical datatypes.
- There is still an M or an F character in each entry! We should remove those before we convert.
- Now you should have the columns you need to make the graph and make sure your boss does not slam a ruler angrily on your desk because you’ve wasted your whole day cleaning your data with no results to show!
- Use matplotlib to make a scatterplot!
- plt.scatter(the_women_column, the_income_column) Remember to call plt.show() to see the graph!
- Did you get an error? These monstrous CSV files probably have nan or null values in them! Print out your column with the number of women per state to see.
- We can fill in those nans by using pandas’ .fillna() function.
- You have the TotalPop per state, and you have the Men per state. As an estimate for the nan values in the Women column, you could use the TotalPop of that state minus the Men for that state.
- Print out the Women column after filling in the nan values to see if it worked!
- We forgot to check for duplicates! Use .duplicated() on your census DataFrame to see if we have duplicate rows in there.
- Drop those duplicates using the .drop_duplicates() function.
- Make the scatterplot again. Now, it should be perfect! Your job is secure, for now.
- Histograms of Races. Now, your boss wants you to make a bunch of histograms out of the race data that you have. Look at the .columns again to see what the race categories are.
- Try to make a histogram for each one!
- You will have to get the columns into numerical format, and those percentage signs will have to go.
- Don’t forget to fill the nan values with something that makes sense! You probably dropped the duplicate rows when making your last graph, but it couldn’t hurt to check for duplicates again.
- Phew. You’ve definitely impressed your boss on your first day of work.


