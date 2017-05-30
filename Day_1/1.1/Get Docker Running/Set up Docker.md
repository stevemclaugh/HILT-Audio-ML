### Set up Docker



```bash
`mkdir /Desktop/sharedfolder

cd /path/to/Dockers

docker build -t audioml ./

docker run -it --name audio_ml_container -p 8888:8888 -v /Desktop/sharedfolder:/home/sharedfolder audioml
```
`

`audioml` is the name of the container instance we're launching.


In the Docker shell:

```bash
`jupyter notebook --ip 0.0.0.0 --no-browser --allow-root
```
`







