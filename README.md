PYRAMID

Pyramid is a small, fast, down-to-earth, open source Python web framework. It makes real-world web application development and deployment more fun, more predictable, and more productive.
Pyramid is much like Flask which takes very little effort to install and run.

Following are the steps to create pyramid framework environment 
            1. create a project directory.
            2. Next, create a virtual environment where you will install all the project specific dependencies.
            3. Then, install the pyramid with "pip install pyramid".
            
The simplest program we can think after installing pyramid framework to check if everything is working fine, is to run a simple “Hello, World” or “Hello, Pyramid” program.
Below is my pyramid “Hello, Pyramid” program on 8000 port number −

from wsgiref.simple_server import make_server
from pyramid.config import Configurator
from pyramid.response import Response

def hello_Pyramid(request):
    return Response('Hello Pyramid!')

if __name__ == '__main__':
    with Configurator() as config:
        config.add_route('hello', '/')
        config.add_view(hello_world, route_name='hello')
        app = config.make_wsgi_app()
    server = make_server('0.0.0.0', 6543, app)
    server.serve_forever()
    



