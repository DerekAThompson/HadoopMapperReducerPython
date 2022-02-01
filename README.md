# HadoopMapperReducerPython
Implementing Python to make use of a mapper and reducer through Hadoop


**Pre-requisites:**

Hadoop must be setup and configured properly on your PC.

The following link helped me configure Hadoop:
https://cwiki.apache.org/confluence/display/HADOOP2/Hadoop2OnWindows


**Guided Tutorial**

Followed the following tutorial for Hadoop mapper reducer: https://www.geeksforgeeks.org/hadoop-streaming-using-python-word-count-problem/

One of the things I noticed is that the python suggested documents in the tutorial appear to have been written python 2, so minor changes had to be made to make it python 3 compatible.


**Windows Lessons Learned**

Instead of performing: 'chmod 777 mapper.py reducer.py'
Try: 'icacls mapper.py'
Then: 'icacls reducer.py'

When attempting to run the Jar file, be sure to run it as follows:
C:\hadoop\word_count_in_python\hadoop-streaming-2.7.3.jar -input \word_count_data.txt -output \output -mapper \mapper.py -reducer \reducer.py


If: While running the Hadoop streaming Jar, if you encounter an issue that leads to the page https://cwiki.apache.org/confluence/display/HADOOP2/UnsetHostnameOrPort
Then: Be sure to edit your core-site.xml and be sure to have value set as 'hdfs://localhost'

