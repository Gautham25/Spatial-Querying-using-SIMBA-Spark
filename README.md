# Spatial-Querying-using-SIMBA-Spark

#Some of the data files are too big for github hence cannot be uploaded here

Part one
Create RTree index using the Spark SIMBA on the dataset provided 

Part two

1. Retrieved all the restaurants located inside the 5th road ring of the city of Beijing. 
2. Determined count of how many people (average per hour) are around 2 Km of the famous Tiananmen Square in Beijing on workdays (Monday to Friday)
3. Used midpoints of the area from the 5th ring found previously and determined the number of trajectories start in a quadrant but end in a different one and how many trajectories start and end in the same quadrant
4. Divided the trajectory dataset into samples between two months and discovered the top 20 points with the highest the number of points within 100 meters radius around them
5. Discovered the top 10 most popular Points of interest between different year individually

First, unzip the project folder. Then go into the project folder. Run sbt package

Second, go into the spark folder

Then
For part1, run bin/spark-submit –class org.apache.spark.sql.simba.examples.RTreeIndex [path of the compiled source code jar]
Then you need to run ./plot.py [sparkpath/mbrs.csv] [sparkpath/points.csv]

For part2 query one, run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryOne [path of the compiled source code jar]. 
For part2 query two, run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryTwo [path of the compiled source code jar].
For part2 query three, run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryThree [path of the compiled source code jar].
For part2 query four, run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryFour [path of the compiled source code jar].
For part2 query five, run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryFive [path of the compiled source code jar].


For part3, we tried to write a wrapper on top of query 4 and query 5, but ended up with memory size issues. So we had to manually run all parameters. Steps are as follow:
Change a combination of parameters. E.g. 100m and 4 cores
Recompile by sbt package
run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryFour
run bin/spark-submit -class org.apache.spark.sql.simba.examples.queryFive
