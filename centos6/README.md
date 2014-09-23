### dockerfiles for centos6

To build, make sure you have Docker installed, clone this repo somewhere, and then run:

	  docker build --rm=true  -t hjue/centos6 .

Pull this repository:

    docker pull hjue/centos6
        
Run it:
    
	  docker run -d  -p 22022:22 hjue/centos6


Login with SSH,The password is hjue.

    ssh -p 22022 user@localhost