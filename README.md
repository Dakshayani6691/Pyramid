PYRAMID

Pyramid is a small, fast, down-to-earth, open source Python web framework. It makes real-world web application development and deployment more fun, more predictable, and more productive.
Pyramid is much like Flask which takes very little effort to install and run.

Follow the below commands to create a simple pyramid application :

PREREQUISITES :

   1. Set up your Python environment:
 To install Python on your system, you can use the following command:
          sudo apt install python3
      
On Windows, make sure the location of our Python interpreter is included in your PATH environment variable. You can check the location by running path at the command prompt. If the Python interpreter's folder isn't included, open Windows Settings, search for "environment", select Edit environment variables for your account, then edit the Path variable to include that folder.
   
    1. On your file system, create a project folder, named "pyramid".
    
    2. Create a virtual environment
    
           python -m venv venv 
            
    3. Activating a virtual environment
    
           venv\Scripts\activate 
          
    4. Install Pyramid
       With the virtual environment activated, install Pyramid using the following command:

           pip install pyramid
    5. Create a new Pyramid project 
       In VS Code, open the terminal and navigate to your desired project directory. Then run the following command to create a new Pyramid project:

           pcreate -s starter myproject

    6. Install project dependencies 
      Move into the project directory by running cd myproject and install the project dependencies using the following command:

           pip install -e .

    7. Start the development server
      To start the development server and run your web application, execute the following command:

           pserve development.ini --reload

     
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
    



