# Take Image XMP Keywords and Get Clustered Folders of Similar Images

This notebook takes images that have had keywords embedded into each file's XMP tags (see this [precursor notebook](https://github.com/munsonbh/text-to-xmp-keywords) to first get keywords into XMP), runs those keywords through a k-means clustering algo, and then copies the images into subfolders that correspond to the clustering output.

This is useful to be able to split a large corpus of images into groups that can then be trained to match a given theme (think Stable Diffusion LoRAs).

## Dependencies
CLI
- [EXIFtool](https://github.com/exiftool/exiftool)

Python Libraries (pip install)
- [jupyter](https://github.com/jupyter/notebook) or [jupyter-lab](https://github.com/jupyterlab/jupyterlab)
- os
- subprocess
- scikit-learn
- shutil
- re

## Howto
1. Make sure your folder of images have keywords (images that don't won't block progress)
1. Add the folder path to the top block
1. Optionally adjust the number of clusters. It defaults to 20, but don't be afraid to run it for a lower number, then run it again inside folders if you need more fidelity with less horsepower.
1. Image folders go brrrt inside the main folder with the naming convention `Cluster_[n]`.
1. These top ten keywords found in each cluster are saved into a text file that is added to the top folder named `cluster_top_keywords.txt`. The list will help define if you want to tweak the number of clusters. Don't be alarmed if the same keyword is used in multiple clusters—it just means it is "popular" in your image set.

## 99% made by AI
I simply interrogated the JupyterLab OpenAI plug-in until it worked, then moved the folder path to an easier place to change. I'm a dumb-but-tenacious designer. Enjoy!