1. Create a folder `share`
2. Download the model file to `share` folder, e.g. `wget https://hanlab.mit.edu/projects/data-efficient-gans/models/stylegan2-cifar10.pkl -P share`
3. `docker build -t das .`
4. `docker run --gpus '"device=6,7"' -it --rm  -u $(id -u):$(id -g) -v $(realpath share):/tf/share das`
5. Once in the docker container, follow the instructions in README.  Replace the `--resume` model name to local file downloaded in step 2. `python run_cifar.py --dataset=cifar10 --resume=share/stylegan2-cifar10.pkl --eval` 