# Spatial-Querying-using-SIMBA-Spark

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
