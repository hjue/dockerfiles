### JustWriting Docker Repo

[JustWriting](https://github.com/hjue/JustWriting) is simple blog system with markdown.

To build, make sure you have Docker installed, clone this repo somewhere, and then run:

	  docker build --rm=true  -t hjue/justwriting .

Pull this repository:

    docker pull hjue/justwriting
        
Run it:
    
	  docker run -d -p 80:80  hjue/justwriting

Run it with local posts directory:

    docker run -d -p 80:80  --privileged=true -v ~/posts/:/var/www/html/posts:ro  hjue/justwriting