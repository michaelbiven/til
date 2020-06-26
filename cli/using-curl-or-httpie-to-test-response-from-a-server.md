# Using curl or HTTPie to test response from a server

## via `curl`

See how the server responds to just the domain:

`curl --verbose --header 'Host: www.example.com' 'http://1.2.3.4/'`

How it repsonds when given path:

`curl --verbose --header 'Host: www.example.com' 'http://1.2.3.4/forum/questions/'`

You may need to add the port that the server is listening on:

`curl --verbose --header 'Host: www.example.com' 'http://1.2.3.4:8080/forum/questions/'`

## via `HTTPie`

See how the server responds to just the domain:

`http 1.2.3.4 Host:www.example.com`

How it repsonds when given path:

`http 1.2.3.4/forum/questions/ Host:www.example.com`

You may need to add the port that the server is listening on:

`http 1.2.3.4:8080/forum/questions/ Host:www.example.com`

