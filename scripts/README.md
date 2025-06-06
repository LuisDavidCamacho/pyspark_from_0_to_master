# Spark installation

To start you will need to install spark in your local device. Spark requires a jvm running, and the spark core.

At the time of this tutorial, the latest version of spark is 4.0.0 launched at May 23rd 2025.
You can find the spark package [here](https://dlcdn.apache.org/spark/spark-4.0.0/spark-4.0.0-bin-hadoop3.tgz).

"Spark runs on Java 17/21, Scala 2.13, Python 3.9+, and R 3.5+ (Deprecated). When using the Scala API, it is necessary for applications to use the same version of Scala that Spark was compiled for. Since Spark 4.0.0, it’s Scala 2.13."

*From official site documentation: you can read it [here](https://spark.apache.org/docs/latest/)*
 
## Installing JVM

JVM stands for Java Virtual Machine. It is a runtime environment that allows you to run java application.
There are a number of ways to install depending on your Operating System.

> ### Windows Installation
> Download java 17 or java 21 zip files from:
> 
> [java 17 x64bit](https://www.oracle.com/java/technologies/javase/jdk17-0-13-later-archive-downloads.html#license-lightbox)
> 
> [java 21 x64bit](https://javadl.oracle.com/webapps/download/AutoDL?BundleId=252044_8a1589aa0fe24566b4337beee47c2d29)
> 
>  - Once you've downloaded the file set a preferred location for you java installation and uncompress the file.
>  - Next set your JAVA_HOME environment variable
>  - Next add java to your path
>  - Test your installation opening a command line prompt and running:
> > ```bash
> > : java -version
> > ```
> Alternatively you can follow Linux instructions if you use WSL within your Windows installation. Also, you can use docker installation instructions. 

> ### Linux Installation
> Download java 17 or java 21 zip files from:
>
> > ### Download official oracle zip java version
> > [java 17 x64bit](https://www.oracle.com/java/technologies/javase/jdk17-0-13-later-archive-downloads.html#license-lightbox)
> >
> > [java 21 x64bit](https://download.oracle.com/graalvm/21/archive/graalvm-jdk-21.0.6_linux-x64_bin.tar.gz)
> >
> > - Once you've downloaded the file set a preferred location for you java installation and uncompress the file.
> > - Next set your JAVA_HOME environment variable by opening your terminal and run:
> > ```bash 
> > $ export JAVA_HOME=/your/jvm/path/java
> > ``` 
> > - Next add java to your path
> > ```bash 
> > $ PATH=\$PATH:\$JAVA_HOME/bin 
> > ```
> > - Test your installation running
> > ```bash
> > $ java -version
> > java version "17"
> > Java(TM) SE Runtime Environment (build 17)
> > Java HotSpot(TM) 64-Bit Server VM (build 23.2-b04, mixed mode)
> > ```
> > - Finally add java home and path inclusion to your .bashrc file by adding export lines to the end of it using your text editor
> > ```bash 
> > $ gedit ~/.bashrc
> > ```
> > - add:
> > ```
> > export JAVA_HOME=/your/jvm/path/java
> > PATH=\$PATH:\$JAVA_HOME/bin
> > ```
> 
> > ### Install openjdk from apt sources
> > Alternatively you can install java using openjdk from ubuntu (or similar) app repository
> >
> > ```bash
> > $ sudo apt install openjdk-[17|21]-[jre|jdk]
> > ```
> > use one option depending on your preferred installation
> > - Test your installation running in your terminal
> > ```bash
> > $ java -version
> > java version "17"
> > Java(TM) SE Runtime Environment (build 17)
> > Java HotSpot(TM) 64-Bit Server VM (build 23.2-b04, mixed mode)
> > ```
> >
> > *use one of the options specified in the squared brackets*
>
> > ### Install from installation scripts
> > Alternatively you can use the included script to execute this steps for you run 
> > ```bash
> > $ ./scripts/install_pyspark.sh --help
> > ```
> > to see instructions
> 
> Alternatively you can use docker installation

> ### Linux Installation
> Download java 17 or java 21 zip files from:
>
> > ### Download official oracle zip java version
> > [java 17 x64bit](https://www.oracle.com/java/technologies/javase/jdk17-0-13-later-archive-downloads.html#license-lightbox)
> >
> > [java 21 x64bit](https://download.oracle.com/graalvm/21/archive/graalvm-jdk-21.0.6_linux-x64_bin.tar.gz)
> >
> >
> > - Once you've downloaded the file set a preferred location for you java installation and uncompress the file.
> > - Next set your JAVA_HOME environment variable by opening your terminal and run:
> > ```bash 
> > $ export JAVA_HOME=/your/jvm/path/java
> > ``` 
> > - Next add java to your path
> > ```bash 
> > $ PATH=\$PATH:\$JAVA_HOME/bin 
> > ```
> > - Test your installation running
> > ```bash
> > $ java -version
> > java version "17"
> > Java(TM) SE Runtime Environment (build 17)
> > Java HotSpot(TM) 64-Bit Server VM (build 23.2-b04, mixed mode)
> > ```
> > - Finally add java home and path inclusion to your .bashrc file by adding export lines to the end of it using your text editor
> > ```bash 
> > $ nano ~/.zshrc
> > ```
> > - add:
> > - export JAVA_HOME=/your/jvm/path/java
> > - PATH=\$PATH:\$JAVA_HOME/bin
>
> > ### Install openjdk from brew sources
> > Alternatively you can install java using openjdk from brew app repository
> >
> > ```bash
> > $ brew install openjdk@[17|21]
> > ```
> > use one option depending on your preferred installation
> > - Test your installation running in your terminal
> > ```bash
> > $ java -version
> > java version "17"
> > Java(TM) SE Runtime Environment (build 17)
> > Java HotSpot(TM) 64-Bit Server VM (build 23.2-b04, mixed mode)
> > ```
> >
> > *use one of the options specified in the squared brackets*
>
> > ### Install from installation scripts
> > Alternatively you can use the included script to execute this steps for you run
> > ```bash
> > $ ./scripts/install_pyspark.sh --help
> > ```
> > to see instructions
>
> Alternatively you can use docker installation

## Installing spark

To run spark you'll need to download from the [official apache spark](https://www.apache.org/dyn/closer.lua/spark/spark-4.0.0/spark-4.0.0-bin-hadoop3.tgz) project.

At this point java must be installed in your local device.

> ### Windows Installation
> After downloading the spark distribution extract it to your preferred location.  
> Once extracted set SPARK_HOME variable
> ```bash 
> $ set SPARK_HOME=c:\your\installation\path\spark
> ``` 
> - Next add java to your path
> ```bash 
> $ PATH=%PATH%;%SPARK_HOME%/bin 
> ```
> Test your installation by running in your terminal
> ```bash 
> : spark -version 
> ```
> If everything went well you should be able to see the spark version and to run the spark shell with spark-sell command (for scala) or pyspark-shell command (for python).
> 
> Alternatively you may use Linux instructions is you're using WSL within your Windows device or the docker instructions instead.

> ### Linux & MacOS Installation
> After downloading the spark distribution extract it to your preferred location.  
> Once extracted set SPARK_HOME variable
> ```bash 
> $ export SPARK_HOME=/your/installation/path/spark
> ``` 
> - Next add java to your path
> ```bash 
> $ PATH=\$PATH:\$SPARK_HOME/bin 
> ```
> Test your installation by running in your terminal
> ```bash 
> $ spark -version 
> ```
> > If everything went well you should be able to see the spark version and to run the spark shell with spark-sell command (for scala) or pyspark-shell command (for python).
> 
> Alternatively you may use docker installation instead.

## Installing Python and dependencies

If you made it to this point you probably want to use pyspark instead of pure spark with scala or java.

To run pyspark you'll need python 3.9 and a few dependencies:

- pyspark (the pyspark package to use spark api)
- py4j (the bridge between python and java, which allows python to use java objects)
- [optionaly] findspark (a package that will find your spark installation and allow you to run python command instead of spark-submit to run a pyspark script)

> ### Windows Installation

> ### Linux Installation

> ### MacOS Installation

## Using docker image of pyspark

This is the easiest way to get pyspark up and running without changing your local setting. This approach is also OS-agnostic
giving you more portability and creating a consistent execution environment. Finally, this approach will allow you to create 
your own cluster with different nodes. 

In this tutorial we will not discuss how to deploy a spark cluster in any docker orchestrator such as kubernetes as it is our
of our scope.