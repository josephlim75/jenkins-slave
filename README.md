Jenkins Slave Daemon
====================

Daemon script for running jenkins workers on ubuntu/debian-like linux operating systems.

To install, run:

    $ sudo cp -r etc /

You can customize the slave properties by editing the ``etc/defaults/jenkins-slave`` file

    # java location
    JAVA=/usr/bin/java

    # arguments to pass to java
    JAVA_ARGS="-Djava.awt.headless=true"  # Allow graphs etc. to work even when an X server is present
    #JAVA_ARGS="-Xmx256m"
    #JAVA_ARGS="-Djava.net.preferIPv4Stack=true" # make jenkins listen on IPv4 address

    # file with the jenkins slave process PID
    PIDFILE=/var/run/jenkins/$NAME.pid

    # user and group to be invoked as (default to jenkins)
    JENKINS_USER=jenkins
    JENKINS_GROUP=jenkins

    # jenkins home location
    JENKINS_HOME=/home/jenkins/jenkins

    # slave jar file location (downloaded by the daemon)
    JENKINS_JAR=$JENKINS_HOME/slave.jar

    # log file location
    JENKINS_LOG=$JENKINS_HOME/jenkins.log

    # hostname of master that this slave is to be connected to
    JENKINS_MASTER=my-master-node.my-domain.com

    # name of this worker node
    JENKINS_NAME=linux-01

    # arguments to pass to jenkins
    JENKINS_ARGS="-jnlpUrl http://$JENKINS_MASTER/computer/$JENKINS_NAME/slave-agent.jnlp"
