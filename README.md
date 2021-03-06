# Image Finder User Study

## Running the app locally on Windows

```shell
git clone git@github.com:schagsim/image_finder.git C:\path\to\project\folder
```

Install [Python 3.9.4](<https://www.python.org/downloads/release/python-394/>)

* You can use [Miniconda](<https://docs.conda.io/en/latest/miniconda.html>) to manage Python versions
* You can also download multiple Python versions and use the specific `python.exe` for 3.9.4

Make sure your Python is a correct version

```shell
> python --version
Python 3.9.4
```

Using the `Python 3.9.4` you installed, create virtual environment in `image_finder` project.

```shell
python -m venv C:\path\to\project\folder\venv
```

This will create a virtual environment for our project in the project folder.

Activate the virtulan environment

```shell
C:\path\to\project\folder\venv\Scripts\activate
```

Install requirements for the project

```shell
python -m pip install -r .\requirements.txt
```

### Running the app in Docker container

Install [docker](<https://docs.docker.com/docker-for-windows/install/>) on you local machine.

Go to web app folder `C:\path\to\project\folder\image_finder_web`

Build the docker image

```shell
docker build -t image_finder_web .
```

Run the docker image

```shell
docker run -d --name image_finder_web_container -p 5000:5000 image_finder_web
```

To stop the docker container, use following command

```shell
docker kill image_finder_web_container
```

### Running the app without Docker container

Go to web app folder `C:\path\to\project\folder\image_finder_web`

```shell
python -m flask run
```

Both for Docker and no-Docker run, you can now go to `http://localhost:5000/` (this address might get outdated eventually) and see the web.
