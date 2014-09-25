### dockerfiles for php-apache

To build, make sure you have Docker installed, clone this repo somewhere, and then run:

	  docker build --rm=true  -t hjue/php-apache .

Pull this repository:

    docker pull hjue/php-apache
        
Run it:
    
	  docker run -d  -p 80:80 hjue/php-apache