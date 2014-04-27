simple-yarn-app
===============

Simple YARN application to run n copies of a unix command - deliberately kept simple (with minimal error handling etc.)

Usage(with Apache2.3.0):
======
Use mvn eclipse:eclipse to generate eclipse project

### Unmanaged mode

$ bin/hadoop jar $HADOOP_YARN_HOME/share/hadoop/yarn/hadoop-yarn-applications-unmanaged-am-launcher-2.3.0.jar Client -classpath simple-yarn-app-1.0-SNAPSHOT.jar -cmd "java com.hortonworks.simpleyarnapp.ApplicationMaster /bin/date 2"

You will the date out put is in the out of the yarn job.
In my case, it is /hadoop-2.3.0/logs/userlogs/application_1398635014957_0001/container_1398635014957_0001_01_000002

### Managed mode

$ bin/hadoop fs -copyFromLocal simple-yarn-app-1.0-SNAPSHOT.jar /apps/simple/simple-yarn-app-1.0-SNAPSHOT.jar

$ bin/hadoop jar simple-yarn-app-1.0-SNAPSHOT.jar com.hortonworks.simpleyarnapp.Client /bin/date 2 /apps/simple/simple-yarn-app-1.0-SNAPSHOT.jar
  
    
