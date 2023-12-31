# ping-pong

A simple Flask app running in a Docker container that serves a webpage displaying a simple ping-pong graphic.

This is used as a basic demo to teach Docker basics to users and is mentioned in the 'Docker for DevOps' YouTube video, which is part of the 'DevOps Shop' video series on YouTube.

## Usage

We can create our own dDocker image that will consist of just 3 tiny files and will run as a flask app inside our Docker container, serving a webpage.

There is the [Dockerfile](https://github.com/xanderstevenson/ping-pong/blob/main/Dockerfile), which will be used when we run the 'docker build' command to build the image to our specifications

The second file we will need, and which is referenced in the final line of our Dockerfile is the [app.py](https://github.com/xanderstevenson/ping-pong/blob/main/app.py).

Finally, we have an HTML file we name [pong.html](https://github.com/xanderstevenson/ping-pong/blob/main/static/pong.html) that we’ve created in a directory called ‘static’. Pong.html is referenced in app.py


We build the image (don’t forget the dot at the end of the command to signal to build from the current directory). 

```docker build -t ping-pong .```

<br>

Then, we run the container, built from the image.

```docker run -p 4000:80 ping-pong```

<br>

Because we’ve mapped the host port 4000 to port 80 in the container, when we visit this URL endpoint: http://127.0.0.1:4000/ping, we will be served the HTML from pong.html

![image](https://github.com/xanderstevenson/ping-pong/assets/27918923/f0f0183b-e0f1-4461-b327-bd9c199c8ab6)
