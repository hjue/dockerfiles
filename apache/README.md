### dockerfiles for centos6

To build, make sure you have Docker installed, clone this repo somewhere, and then run:

	  docker build --rm=true  -t hjue/apache .

Pull this repository:

    docker pull hjue/apache
        
Run it:
    
	  docker run -d  -p 80:80 hjue/apache