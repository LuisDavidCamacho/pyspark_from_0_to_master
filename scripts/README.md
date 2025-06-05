# Spark installation

To start you will need to install spark in your local device. Spark requires a jvm running, and the spark core.

At the time of this tutorial, the latest version of spark is 4.0.0 launched at May 23rd 2025.
Yoy can find the spark package [here](https://dlcdn.apache.org/spark/spark-4.0.0/spark-4.0.0-bin-hadoop3.tgz).

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
> > :> java -version
> > 

> ### Linux Installation
> Download java 17 or java 21 zip files from:
>
> [java 17 x64bit](https://www.oracle.com/java/technologies/javase/jdk17-0-13-later-archive-downloads.html#license-lightbox)
>
> [java 21 x64bit](https://download.oracle.com/graalvm/21/archive/graalvm-jdk-21.0.6_linux-x64_bin.tar.gz)
>
>  - Once you've downloaded the file set a preferred location for you java installation and uncompress the file.
>  - Next set your JAVA_HOME environment variable by opening your terminal and run:
> > $ export JAVA_HOME=/your/jvm/path/java
>  - Next add java to your path
> > $ PATH=\$PATH:\$JAVA_HOME/bin
>  - Test your installation running
> > $ java -version
>  - Finally add java home and path inclusion to your .bashrc file by adding export lines to the end of it using your text editor
> > $ gedit ~/.bashrc
>  - add:
>  - export JAVA_HOME=/your/jvm/path/java
>  - PATH=\$PATH:\$JAVA_HOME/bin
> 
> Alternatively you can install java using openjdk from ubuntu (or similar) app repository
> > $ sudo apt install openjdk-[17|21]-[jre|jdk]
> use one option depending on your preferred installation
> 
> Alternatively you can use the included script to execute this steps for you run 
> > $ ./scripts/install_pyspark.sh --help
> to see instructions


> ### MacOS Installation
> Download java 17 or java 21 zip files from:
>
> [java 17 x64bit](https://www.oracle.com/java/technologies/javase/jdk17-0-13-later-archive-downloads.html#license-lightbox)
>
> [java 21 x64bit](https://download.oracle.com/graalvm/21/archive/graalvm-jdk-21.0.6_macos-x64_bin.tar.gz)
>  - Once you've downloaded the file set a preferred location for you java installation and uncompress the file.
>  - Next set your JAVA_HOME environment variable


## Installing spark

To run spark you'll need to download from:

> ### Windows Installation

> ### Linux Installation

> ### MacOS Installation



## Installing Python and dependencies

To run pyspark you'll need python 3.9 and a few dependencies

> ### Windows Installation

> ### Linux Installation

> ### MacOS Installation
