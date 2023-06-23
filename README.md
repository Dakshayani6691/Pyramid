PYRAMID

Pyramid is a small, fast, down-to-earth, open source Python web framework. It makes real-world web application development and deployment more fun, more predictable, and more productive. 
Try Pyramid, browse its add-ons and documentation, and get an overview.



The simplest program we can think after installing pyramid framework to check if everything is working fine, is to run a simple “Hello, World” or “Hello, Pyramid” program.
Below is my pyramid “Hello, Pyramid” program on 8000 port number −

from wsgiref.simple_server import make_server
from pyramid.config import Configurator
from pyramid.response import Response

def hello_Python(request):
    return Response('Hello Python!')

if __name__ == '__main__':
    with Configurator() as config:
        config.add_route('hello', '/')
        config.add_view(hello_world, route_name='hello')
        app = config.make_wsgi_app()
    server = make_server('0.0.0.0', 6543, app)
    server.serve_forever()



