__Running Hadoop in pseudo-distributed mode__

Export the project as a Runnable JAR le. We name it wordcount.jar and save it to
the Desktop.

Open Terminal, type in cd /usr/local/hadoop.

This will start all necessary Hadoop deamons, including
NameNode, DataNode, TaskTracker, SecondaryNameNode, JobTracker.

bin/start-all.sh

Type jps to see if everything is turned on

Type bin/hadoop dfs -ls. It should output nothing, since there is nothing inside
HDFS.

Type bin/hadoop dfs -copyFromLocal /Desktop/dataset dataset to put the dataset
folder on the Desktop to HDFS.

Type bin/hadoop dfs -ls again. Now you should see Figure 11, indicating dataset
is in HDFS.

Let's use 3 mappers and 1 reducer for the program.
Update the le /usr/local/hadoop/src/mapred/mapred-default.xml, set the value
of mapred.min.split.size to be 3 as

Type bin/hadoop jar /Desktop/wordcount.jar dataset output to run the Hadoop
job.

Type bin/hadoop dfs -ls and you can see there appears output folder in HDFS

Type bin/hadoop dfs -ls output and you can see the content in output folder

Type bin/hadoop dfs -cat output/part-r-00000 and you can see the contents of
part-r-00000 which contains the letter counts.