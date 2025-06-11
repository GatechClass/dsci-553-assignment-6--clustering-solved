# dsci-553-assignment-6--clustering-solved
**TO GET THIS SOLUTION VISIT:** [DSCI-553 Assignment 6- Clustering Solved](https://mantutor.com/product/dsci-553-foundations-and-applications-of-data-mining-solved-4/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;114969&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;DSCI-553 Assignment 6- Clustering Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Assignment 6 Clustering

1. Overview of the Assignment

In Assignment 6, you will implement the Bradley-Fayyad-Reina (BFR) algorithm. The goal is to let you be familiar with the process of clustering in general and various distance measurements. The datasets you are going to use is synthetic dataset.

2. Assignment Requirements

2.1 Programming Language and Library Requirements

You must use Python to implement the algorithm. You can only use the following external Python libraries: numpy and sklearn.

2.2 Programming Environment

Python 3.6, JDK 1.8, Scala 2.12 and Spark 3.1.2

We will use these library versions to compile and test your code. You are required to make sure your code works and runs on Vocareum otherwise we won’t be able to grade your code.

2.3 Write your own code

Do not share your code with other students!!

3. Dataset

Since the BFR algorithm has a strong assumption that the clusters are normally distributed with independent dimensions, we generated synthetic datasets by initializing some random centroids and creating some data points with the centroids and some standard deviations to form the clusters. We also added some other data points as outliers in the dataset to evaluate the algorithm. Data points which are outliers belong to clusters that are named or indexed as “-1”. Figure 1 shows an example of a part of the dataset. The first column is the data point index. The second column is the name/index of the cluster that the data point belongs to. The rest columns represent the features/dimensions of the data point.

Figure 1: An example of the dataset

a. hw6_clustering.txt is the synthetic clustering dataset. The dataset is available on Vocareum (public data folder).

b. We generate the testing dataset using a similar method. Notice that the number of the dimensions could be different from the hw6_clustering.txt. We do not share the testing dataset.

4. Task

You will implement the Bradley-Fayyad-Reina (BFR) algorithm to cluster the data contained in hw6_clustering.txt.

In BFR, there are three sets of points that you need to keep track of:

Discard set (DS), Compression set (CS), Retained set (RS) For each cluster in the DS and CS, the cluster is summarized by:

N: The number of points

SUM: the sum of the coordinates of the points

SUMSQ: the sum of squares of coordinates

The conceptual steps of the BFR algorithm (Please refer to the slide for details):

Implementation details of the BFR algorithm: (just for your reference, the number of input clusters = n_cluster parameter given as input)

Step 1. Load 20% of the data randomly.

Step 2. Run K-Means (e.g., from sklearn) with a large K (e.g., 5 times of the number of the input clusters) on the data in memory using the Euclidean distance as the similarity measurement.

Step 3. In the K-Means result from Step 2, move all the clusters that contain only one point to RS (outliers).

Step 4. Run K-Means again to cluster the rest of the data points with K = the number of input clusters.

Step 5. Use the K-Means result from Step 4 to generate the DS clusters (i.e., discard their points and generate statistics).

The initialization of DS has finished, so far, you have K numbers of DS clusters (from Step 5) and some numbers of RS (from Step 3).

Step 6. Run K-Means on the points in the RS with a large K (e.g., 5 times of the number of the input clusters) to generate CS (clusters with more than one points) and RS (clusters with only one point).

Step 7. Load another 20% of the data randomly.

Step 8. For the new points, compare them to each of the DS using the Mahalanobis Distance and assign them to the nearest DS clusters if the distance is &lt; 2√𝑑.

Step 11. Run K-Means on the RS with a large K (e.g., 5 times of the number of the input clusters) to generate CS (clusters with more than one points) and RS (clusters with only one point).

Step 12. Merge CS clusters that have a Mahalanobis Distance &lt; 2√𝑑.

Repeat Steps 7 – 12.

If this is the last run (after the last chunk of data), merge CS clusters with DS clusters that have a Mahalanobis Distance &lt; 2√𝑑.

At each run, including the initialization step, you need to count and output the number of the discard points, the number of the clusters in the CS, the number of the compression points, and the number of the points in the retained set.

Input format: (we will use the following command to execute your code) python3 task.py &lt;input_file&gt; &lt;n_cluster&gt; &lt;output_file&gt;

Param: input_file: the name of the input file (e.g., hw6_clustering.txt), including the file path.

Param: n_cluster: the number of the clusters.

Param: output_file: the name of the output txt file, including the file path.

Output format:

The output file is a text file, containing the following information (see Figure 2):

a. The intermediate results (the line is named as “The intermediate results”). Then each line should be started with “Round {𝑖}:” and 𝑖 is the count for the round (including the initialization, i.e., initialization would be “Round 1:”. You need to output the numbers in the order of “the number of the discard points”, “the number of the clusters in the compression set”, “the number of the compression points”, and “the number of the points in the retained set”.

Leave one line in the middle before writing out the cluster results.

b. The clustering results (the line is named as “The clustering results”), including the data points index and their clustering results after the BFR algorithm. The clustering results should be in [0, the number of clusters). The cluster of outliers should be represented as -1.

Figure 2: the output example for text file Grading:

a. We will compare the percentage of discard points after the last round to our threshold.

Dataset Percentage of discard points after last round

hw6_ clustering.txt 98.5%

b. We will compare the centroids of the clusters you find to those in the ground truth.

c. We will compute the accuracy of your clustering results to the ground truth. We will check the percentage of data points that you issue to the correct cluster (except the outliers) using the following formula:

𝑡ℎ𝑒 𝑡𝑜𝑡𝑎𝑙 𝑛𝑢𝑚𝑏𝑒𝑟 𝑜𝑓 𝑝𝑜𝑖𝑛𝑡𝑠 𝑖𝑛 𝑡ℎ𝑒 𝑐𝑜𝑟𝑟𝑒𝑐𝑡 𝑐𝑙𝑢𝑠𝑡𝑒𝑟𝑠

𝐴𝑐𝑐𝑢𝑟𝑎𝑐𝑦 =

Dataset Accuracy

hw6_ clustering.txt 98.0%

d. No point if your runtime is more than or equal to 600 seconds.

Execution format:

Task: python3 task.py &lt;input_file&gt; &lt;n_cluster&gt; &lt;output_file&gt;

/home/local/spark/latest/bin/spark-submit –class task –executor-memory 4G –driver-memory 4G hw6.jar &lt;input_file&gt; &lt;n_cluster&gt; &lt;output_file&gt;

5. Submission

You need to submit following files on Vocareum with exactly the same name: a. One Python script, named: (all lowercase) task.py

b. [OPTIONAL] One Scala scripts, named: (all lowercase)

1. task.scala

2. hw6.jar

c. You don’t need to include your results or the datasets. We will grade on your code with our testing data (data will be in the same format).

6. Grading Criteria

(% penalty = % penalty of possible points you get)

2. There will be a 10% bonus for correct Scala implementation provided the python implementation works correctly.

3. If we cannot run your programs with the command we specified, there will be no regrading.

4. If your program cannot run with the required Python versions, there will be a 20% penalty.
