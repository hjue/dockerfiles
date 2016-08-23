### Spark Jobserver Docker Repo

Build:

	  docker build --rm=true  -t hjue/jobserver .

Pull this repository:

    docker pull hjue/jobserver

Run it:

    docker run -d -p 8090:8090 --add-host spark001:xxx.xxx.xxx.xxx -e SPARK_MASTER=spark://spark001:7077 hjue/jobserver
