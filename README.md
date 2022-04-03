# K-means-Clustering

Present here is a dataset of recent customers of a supermarket. Now, it wants to segment its customers into groups for targeted marketing. 

The purpose of this program is to divide the customers(points) into k clusters using k-means clustering.

# Program Explanation:
1. The data was imported in a dataframe and column named ID was dropped out of it cause it’s unique and there can be no relation in between two id’s
2. Now, the technique of k means clustering requires Euclidean distance to be calculated, so, in order to normalize the parameters so that each parameter has equal contribution z-score needs to be calculated
3. To calculate the z-score the mean of the columns as well as the standard deviation of the columns were calculated and stored in avg_arr[] and std_dev[]
4. Once both the avg_arr[] and std_dev[] were calculated, all the entries of the dataframe were changed to their respective z-scores. The formula for z-score was given by: z-score=(value-mean)/standard_deviation
5. Then, a distance function was made to calculate the distance between the customers/points and the centroid of the clusters. The centroid of the cluster is a point to represent the central location of the cluster. It is usually the mean of parameters(features of dataframe) of all the points in that cluster. The distance function returns the cluster number in which the point needs to be put. The cluster number is decided based on the minimum distance between the point and the clusters centroid 
6. Now that we have been talking a lot about k means clustering many of you would be wondering what is the value of k, right? Well, in order to get the optimal value of k, elbow method has been used which calculates the wss score for each k, plots wss vs k and picks the value of k for which wss first starts to diminish and this is visible as an elbow in the plot. WSS stands for within cluster sum of squared errors and it sounds a bit complex, let’s break it down:
  a. The Squared Error for each point is the square of the distance of the point from its representation i.e. its predicted cluster center 
  b. The WSS score is the sum of these Squared Errors for all the points
7. The code for performing the elbow method has been well explained with proper comments
8. Once the wss score for each k has been calculated, the value of k was found out based on when the plot first starts to diminish and with a lot of observation a technique was used which calculates the first point where the slope decreased to one-fifth of the initial slope and that first point becomes k
9. Once we get the optimal value of k, it’s time to divide the data into those k clusters and print the output in the Output file

The program is running perfectly fine, however it may take 5-6 minutes to run based on the kernel of your device.
