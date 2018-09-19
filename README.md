# [docker-jsonnet](https://github.com/obitech/docker-jsonnet)

An Alpine based Docker image to run [jsonnet](https://jsonnet.org/). 

Needs about 328MB on disk.

## Run it
Try it out with: 
```bash
$ docker run obitech/docker-jsonnet -e '{ x: 1 , y: self.x + 1 } { x: 10 }'
{
   "x": 10,
   "y": 11
}
```

You can mount your directory into `/workdir` inside the container, then just evaluate the file:
```bash
$ docker run -v $(pwd)/examples:/workdir obitech/docker-jsonnet landingpage.jsonnet
{
   "person1": {
      "name": "Alice",
      "welcome": "Hello Alice!"
   },
   "person2": {
      "name": "Bob",
      "welcome": "Hello Bob!"
   }
}
```
