# THE WILD PROJECT

Simple data analysis for wild life insights org.

## Initial Steps

1. Get the dataset.
2. Create a repository and upload the dataset to GIT LFS.
3. Create a virtual environment with Conda.

### 1. Get the dataset.

[Wildlife Insights](https://www.wildlifeinsights.org/) is a is a cloud-based platform that use camera trap images and provides data to make better decisions and help wildlife thrive.

Through the platform signup, explore and filter, then request a dataset of some interest. The only restriction is that we are only allowed to download 500,000 records or less.

### 2. Create a repository and upload the dataset to GIT LFS.

* Install [Git LFS](https://git-lfs.github.com/) `sudo apt install git-lfs` for Linux Ubuntu (To get the LFS up and working in your machine).
* Create a new GitHub repository and clone it to your machine ([How to Get and Configure Your Git and GitHub SSH Keys](https://www.freecodecamp.org/news/git-ssh-how-to/)).
* Add your csv files into the dataset directory and track them with LFS for your repo as follows.
> ```bash
> git lfs install
> git lfs migrate import --include="*.csv"
> git lfs track "dataset/*.csv"
> git add .
> git commit -m "Dataset loadup with git-lfs"
> git push origin main
> ```

### 3. Create a virtual environment with Conda.
* Create a env using [conda](https://docs.conda.io/en/latest/). For this project e.g. `conda create --name ntp python==3.10 pandas numpy jupyter`.
* Some packages may cause problems to install. For this, we use pip and a python code formatter like [black](https://pypi.org/project/black/). `pip install nb-black`.
* For activate your enviroment just use `conda activate ntp`.
* To export the requirements `pip list --format=freeze > requirements.txt`.
* To deactivate the enviroments `conda deactivate`
* If you clone the repository just install and like to replicate the same enviroment as the host repo just use `conda create --name <environment_name> --file requirements.txt` 

### + Info
* [How to create a virtual enviroment in python](https://www.machinelearningplus.com/deployment/conda-create-environment-and-everything-you-need-to-know-to-manage-conda-virtual-environment/)
* [How to load more than 100mb and csv files to Git LFS](https://stackoverflow.com/questions/33330771/git-lfs-this-exceeds-githubs-file-size-limit-of-100-00-mb)
* [How to install Git LFS to ubuntu](https://askubuntu.com/questions/799341/how-to-install-git-lfs-on-ubuntu-16-04)