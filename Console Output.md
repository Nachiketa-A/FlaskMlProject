# Console Output:
```
Started by user admin
Obtained Jenkinsfile from git https://github.com/Nachiketa-A/FlaskMlProject
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential 607f3097-d704-4c3c-b94a-0f025985c78c
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/Nachiketa-A/FlaskMlProject # timeout=10
Fetching upstream changes from https://github.com/Nachiketa-A/FlaskMlProject
 > git.exe --version # timeout=10
 > git --version # 'git version 2.42.0.windows.1'
using GIT_ASKPASS to set credentials Github
 > git.exe fetch --tags --force --progress -- https://github.com/Nachiketa-A/FlaskMlProject +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/master^{commit}" # timeout=10
Checking out Revision a17c3700da40b49813b3f03147b9cb9227566b2f (refs/remotes/origin/master)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f a17c3700da40b49813b3f03147b9cb9227566b2f # timeout=10
Commit message: "Jenkinsfile modified"
 > git.exe rev-list --no-walk a7f524650e50786e2cdd8c1117f6eafef4784285 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withCredentials
Masking supported pattern matches of %DOCKER_HUB_CREDENTIALS% or %DOCKER_HUB_CREDENTIALS_PSW%
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Build Image)
[Pipeline] script
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj>docker build -t "nachia2024/boston-housing-predictor:14" . 
2024/05/20 01:09:16 http2: server: error reading preface from client //./pipe/docker_engine: file has already been closed
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 465B done
#1 DONE 0.0s

#2 [auth] library/python:pull token for registry-1.docker.io
#2 DONE 0.0s

#3 [internal] load metadata for docker.io/library/python:3.7.3-stretch
#3 DONE 1.6s

#4 [internal] load .dockerignore
#4 transferring context: 2B done
#4 DONE 0.0s

#5 [1/4] FROM docker.io/library/python:3.7.3-stretch@sha256:205cafadbb7f0c48f2a6d655eb100a9675aa85e6e73958860f488406cce09779
#5 DONE 0.0s

#6 [internal] load build context
#6 transferring context: 1.03MB 0.1s done
#6 DONE 0.1s

#7 [2/4] WORKDIR /app
#7 CACHED

#8 [3/4] COPY . app.py /app/
#8 DONE 0.3s

#9 [4/4] RUN pip install --upgrade pip && pip install -r requirements.txt
#9 2.568 Collecting pip
#9 2.916   Downloading https://files.pythonhosted.org/packages/8a/6a/19e9fe04fca059ccf770861c7d5721ab4c2aebc539889e97c7977528a53b/pip-24.0-py3-none-any.whl (2.1MB)
#9 3.547 Installing collected packages: pip
#9 3.547   Found existing installation: pip 19.1.1
#9 3.679     Uninstalling pip-19.1.1:
#9 3.955       Successfully uninstalled pip-19.1.1
#9 5.559 Successfully installed pip-24.0
#9 6.508 Collecting Flask (from -r requirements.txt (line 1))
#9 6.669   Downloading Flask-2.2.5-py3-none-any.whl.metadata (3.9 kB)
#9 7.063 Collecting numpy (from -r requirements.txt (line 2))
#9 7.099   Downloading numpy-1.21.6-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl.metadata (2.1 kB)
#9 7.393 Collecting pandas (from -r requirements.txt (line 3))
#9 7.426   Downloading pandas-1.3.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (12 kB)
#9 7.629 Collecting scikit-learn==0.20.3 (from -r requirements.txt (line 4))
#9 7.660   Downloading scikit_learn-0.20.3-cp37-cp37m-manylinux1_x86_64.whl.metadata (7.4 kB)
#9 7.792 Collecting pylint (from -r requirements.txt (line 5))
#9 7.830   Downloading pylint-2.17.7-py3-none-any.whl.metadata (12 kB)
#9 8.308 Collecting scipy>=0.13.3 (from scikit-learn==0.20.3->-r requirements.txt (line 4))
#9 8.358   Downloading scipy-1.7.3-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl.metadata (2.2 kB)
#9 8.509 Collecting Werkzeug>=2.2.2 (from Flask->-r requirements.txt (line 1))
#9 8.544   Downloading Werkzeug-2.2.3-py3-none-any.whl.metadata (4.4 kB)
#9 8.611 Collecting Jinja2>=3.0 (from Flask->-r requirements.txt (line 1))
#9 8.644   Downloading jinja2-3.1.4-py3-none-any.whl.metadata (2.6 kB)
#9 8.702 Collecting itsdangerous>=2.0 (from Flask->-r requirements.txt (line 1))
#9 8.735   Downloading itsdangerous-2.1.2-py3-none-any.whl.metadata (2.9 kB)
#9 8.802 Collecting click>=8.0 (from Flask->-r requirements.txt (line 1))
#9 8.839   Downloading click-8.1.7-py3-none-any.whl.metadata (3.0 kB)
#9 8.995 Collecting importlib-metadata>=3.6.0 (from Flask->-r requirements.txt (line 1))
#9 9.044   Downloading importlib_metadata-6.7.0-py3-none-any.whl.metadata (4.9 kB)
#9 9.130 Collecting python-dateutil>=2.7.3 (from pandas->-r requirements.txt (line 3))
#9 9.162   Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl.metadata (8.4 kB)
#9 9.311 Collecting pytz>=2017.3 (from pandas->-r requirements.txt (line 3))
#9 9.357   Downloading pytz-2024.1-py2.py3-none-any.whl.metadata (22 kB)
#9 9.513 Collecting platformdirs>=2.2.0 (from pylint->-r requirements.txt (line 5))
#9 9.546   Downloading platformdirs-4.0.0-py3-none-any.whl.metadata (11 kB)
#9 9.774 Collecting astroid<=2.17.0-dev0,>=2.15.8 (from pylint->-r requirements.txt (line 5))
#9 9.818   Downloading astroid-2.15.8-py3-none-any.whl.metadata (4.7 kB)
#9 9.961 Collecting isort<6,>=4.2.5 (from pylint->-r requirements.txt (line 5))
#9 10.000   Downloading isort-5.11.5-py3-none-any.whl.metadata (13 kB)
#9 10.10 Collecting mccabe<0.8,>=0.6 (from pylint->-r requirements.txt (line 5))
#9 10.16   Downloading mccabe-0.7.0-py2.py3-none-any.whl.metadata (5.0 kB)
#9 10.33 Collecting tomlkit>=0.10.1 (from pylint->-r requirements.txt (line 5))
#9 10.37   Downloading tomlkit-0.12.5-py3-none-any.whl.metadata (2.7 kB)
#9 10.46 Collecting typing-extensions>=3.10.0 (from pylint->-r requirements.txt (line 5))
#9 10.50   Downloading typing_extensions-4.7.1-py3-none-any.whl.metadata (3.1 kB)
#9 10.61 Collecting dill>=0.2 (from pylint->-r requirements.txt (line 5))
#9 10.65   Downloading dill-0.3.7-py3-none-any.whl.metadata (9.9 kB)
#9 10.75 Collecting tomli>=1.1.0 (from pylint->-r requirements.txt (line 5))
#9 10.78   Downloading tomli-2.0.1-py3-none-any.whl.metadata (8.9 kB)
#9 10.97 Collecting lazy-object-proxy>=1.4.0 (from astroid<=2.17.0-dev0,>=2.15.8->pylint->-r requirements.txt (line 5))
#9 11.01   Downloading lazy_object_proxy-1.9.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (7.6 kB)
#9 11.15 Collecting typed-ast<2.0,>=1.4.0 (from astroid<=2.17.0-dev0,>=2.15.8->pylint->-r requirements.txt (line 5))
#9 11.19   Downloading typed_ast-1.5.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (1.7 kB)
#9 11.43 Collecting wrapt<2,>=1.11 (from astroid<=2.17.0-dev0,>=2.15.8->pylint->-r requirements.txt (line 5))
#9 11.46   Downloading wrapt-1.16.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (6.6 kB)
#9 11.65 Collecting zipp>=0.5 (from importlib-metadata>=3.6.0->Flask->-r requirements.txt (line 1))
#9 11.68   Downloading zipp-3.15.0-py3-none-any.whl.metadata (3.7 kB)
#9 11.85 Collecting MarkupSafe>=2.0 (from Jinja2>=3.0->Flask->-r requirements.txt (line 1))
#9 11.89   Downloading MarkupSafe-2.1.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.0 kB)
#9 11.98 Collecting six>=1.5 (from python-dateutil>=2.7.3->pandas->-r requirements.txt (line 3))
#9 12.02   Downloading six-1.16.0-py2.py3-none-any.whl.metadata (1.8 kB)
#9 12.25 Downloading scikit_learn-0.20.3-cp37-cp37m-manylinux1_x86_64.whl (5.4 MB)
#9 13.16    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 5.4/5.4 MB 5.9 MB/s eta 0:00:00
#9 13.19 Downloading Flask-2.2.5-py3-none-any.whl (101 kB)
#9 13.22    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 101.8/101.8 kB 4.3 MB/s eta 0:00:00
#9 13.25 Downloading numpy-1.21.6-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (15.7 MB)
#9 17.01    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 15.7/15.7 MB 3.5 MB/s eta 0:00:00
#9 17.05 Downloading pandas-1.3.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (11.3 MB)
#9 19.42    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 11.3/11.3 MB 4.7 MB/s eta 0:00:00
#9 19.46 Downloading pylint-2.17.7-py3-none-any.whl (537 kB)
#9 19.55    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 537.2/537.2 kB 6.6 MB/s eta 0:00:00
#9 19.58 Downloading astroid-2.15.8-py3-none-any.whl (278 kB)
#9 19.63    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 278.3/278.3 kB 5.9 MB/s eta 0:00:00
#9 19.66 Downloading click-8.1.7-py3-none-any.whl (97 kB)
#9 19.69    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 97.9/97.9 kB 4.6 MB/s eta 0:00:00
#9 19.73 Downloading dill-0.3.7-py3-none-any.whl (115 kB)
#9 19.75    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 115.3/115.3 kB 6.2 MB/s eta 0:00:00
#9 19.78 Downloading importlib_metadata-6.7.0-py3-none-any.whl (22 kB)
#9 19.83 Downloading isort-5.11.5-py3-none-any.whl (104 kB)
#9 19.86    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 104.1/104.1 kB 4.0 MB/s eta 0:00:00
#9 19.89 Downloading itsdangerous-2.1.2-py3-none-any.whl (15 kB)
#9 19.94 Downloading jinja2-3.1.4-py3-none-any.whl (133 kB)
#9 19.98    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 133.3/133.3 kB 5.1 MB/s eta 0:00:00
#9 20.01 Downloading mccabe-0.7.0-py2.py3-none-any.whl (7.3 kB)
#9 20.06 Downloading platformdirs-4.0.0-py3-none-any.whl (17 kB)
#9 20.11 Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
#9 20.16    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 229.9/229.9 kB 5.5 MB/s eta 0:00:00
#9 20.19 Downloading pytz-2024.1-py2.py3-none-any.whl (505 kB)
#9 20.28    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 505.5/505.5 kB 6.3 MB/s eta 0:00:00
#9 20.32 Downloading scipy-1.7.3-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (38.1 MB)
#9 27.20    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 38.1/38.1 MB 4.2 MB/s eta 0:00:00
#9 27.23 Downloading tomli-2.0.1-py3-none-any.whl (12 kB)
#9 27.27 Downloading tomlkit-0.12.5-py3-none-any.whl (37 kB)
#9 27.32 Downloading typing_extensions-4.7.1-py3-none-any.whl (33 kB)
#9 27.36 Downloading Werkzeug-2.2.3-py3-none-any.whl (233 kB)
#9 27.39    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 233.6/233.6 kB 7.9 MB/s eta 0:00:00
#9 27.43 Downloading lazy_object_proxy-1.9.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (58 kB)
#9 27.46    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 58.5/58.5 kB 3.2 MB/s eta 0:00:00
#9 27.50 Downloading MarkupSafe-2.1.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (25 kB)
#9 27.55 Downloading six-1.16.0-py2.py3-none-any.whl (11 kB)
#9 27.60 Downloading typed_ast-1.5.5-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (778 kB)
#9 27.69    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 778.3/778.3 kB 8.8 MB/s eta 0:00:00
#9 27.72 Downloading wrapt-1.16.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (77 kB)
#9 27.74    â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”�â”� 77.5/77.5 kB 5.1 MB/s eta 0:00:00
#9 27.77 Downloading zipp-3.15.0-py3-none-any.whl (6.8 kB)
#9 28.39 Installing collected packages: pytz, zipp, wrapt, typing-extensions, typed-ast, tomlkit, tomli, six, numpy, mccabe, MarkupSafe, lazy-object-proxy, itsdangerous, isort, dill, Werkzeug, scipy, python-dateutil, platformdirs, Jinja2, importlib-metadata, astroid, scikit-learn, pylint, pandas, click, Flask
#9 44.17 Successfully installed Flask-2.2.5 Jinja2-3.1.4 MarkupSafe-2.1.5 Werkzeug-2.2.3 astroid-2.15.8 click-8.1.7 dill-0.3.7 importlib-metadata-6.7.0 isort-5.11.5 itsdangerous-2.1.2 lazy-object-proxy-1.9.0 mccabe-0.7.0 numpy-1.21.6 pandas-1.3.5 platformdirs-4.0.0 pylint-2.17.7 python-dateutil-2.9.0.post0 pytz-2024.1 scikit-learn-0.20.3 scipy-1.7.3 six-1.16.0 tomli-2.0.1 tomlkit-0.12.5 typed-ast-1.5.5 typing-extensions-4.7.1 wrapt-1.16.0 zipp-3.15.0
#9 44.17 WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
#9 DONE 44.9s

#10 exporting to image
#10 exporting layers
#10 exporting layers 3.3s done
#10 writing image sha256:c1b1efdbf3d3ddec7c7da6aa3b83645998774cda977f8497aaf306a41e9b647e 0.1s done
#10 naming to docker.io/nachia2024/boston-housing-predictor:14 done
#10 DONE 3.6s

What's Next?
  View a summary of image vulnerabilities and recommendations â†’ docker scout quickview
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Publish Image)
[Pipeline] script
[Pipeline] {
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withDockerRegistry
$ docker login -u nachia2609@gmail.com -p ******** https://index.docker.io/v1/
WARNING! Using --password via the CLI is insecure. Use --password-stdin.
Login Succeeded
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj>docker tag "nachia2024/boston-housing-predictor:14" "index.docker.io/nachia2024/boston-housing-predictor:14" 
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj>docker push "index.docker.io/nachia2024/boston-housing-predictor:14" 
The push refers to repository [docker.io/nachia2024/boston-housing-predictor]
f6d8e473a913: Preparing
f54da7f1121d: Preparing
370486eff12d: Preparing
799a7872c8c7: Preparing
715450468940: Preparing
c9d608035aef: Preparing
bb9c02680a15: Preparing
c9d608035aef: Waiting
a637c551a0da: Preparing
2c8d31157b81: Preparing
bb9c02680a15: Waiting
a637c551a0da: Waiting
7b76d801397d: Preparing
f32868cde90b: Preparing
0db06dff9d9a: Preparing
2c8d31157b81: Waiting
7b76d801397d: Waiting
f32868cde90b: Waiting
0db06dff9d9a: Waiting
799a7872c8c7: Pushed
370486eff12d: Pushed
715450468940: Pushed
f54da7f1121d: Pushed
bb9c02680a15: Pushed
7b76d801397d: Pushed
c9d608035aef: Pushed
f32868cde90b: Pushed
2c8d31157b81: Pushed
f6d8e473a913: Pushed
a637c551a0da: Pushed
0db06dff9d9a: Pushed
14: digest: sha256:f00ec13678433b307bcb793f66d4dc7c4e2374b7f97740a7d4f280e07b5d7bf5 size: 2847
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj>docker tag "nachia2024/boston-housing-predictor:14" "index.docker.io/nachia2024/boston-housing-predictor:latest" 
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\FlaskPrj>docker push "index.docker.io/nachia2024/boston-housing-predictor:latest" 
The push refers to repository [docker.io/nachia2024/boston-housing-predictor]
f6d8e473a913: Preparing
f54da7f1121d: Preparing
370486eff12d: Preparing
799a7872c8c7: Preparing
715450468940: Preparing
c9d608035aef: Preparing
bb9c02680a15: Preparing
a637c551a0da: Preparing
2c8d31157b81: Preparing
7b76d801397d: Preparing
f32868cde90b: Preparing
0db06dff9d9a: Preparing
c9d608035aef: Waiting
bb9c02680a15: Waiting
a637c551a0da: Waiting
2c8d31157b81: Waiting
7b76d801397d: Waiting
f32868cde90b: Waiting
0db06dff9d9a: Waiting
715450468940: Layer already exists
370486eff12d: Layer already exists
c9d608035aef: Layer already exists
f54da7f1121d: Layer already exists
799a7872c8c7: Layer already exists
2c8d31157b81: Layer already exists
7b76d801397d: Layer already exists
f6d8e473a913: Layer already exists
a637c551a0da: Layer already exists
0db06dff9d9a: Layer already exists
bb9c02680a15: Layer already exists
f32868cde90b: Layer already exists
latest: digest: sha256:f00ec13678433b307bcb793f66d4dc7c4e2374b7f97740a7d4f280e07b5d7bf5 size: 2847
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withDockerRegistry
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withCredentials
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
...
