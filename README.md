This repository presents a way of converting a pdf file to an eps file. Those who want this functionality could execute steps described as follows.

The functionality of this repository works properly for powerpoint files saved in the pdf format, based on the docker (version info is written in docker\_version.txt) installed on my computer (macOS version 12.6.1).

# 1. Download a docker image.
In terminal, run
```
docker pull thomasweise/docker-texlive-full:2.0
```


# 2. Clone repository.
Assume that the root directory of this repository on a local computer is DIR. Then, copy the pdf file to convert to the root directory.



# 3. Create an eps file from a pdf file.
Run the following commands.
```
cd DIR
docker run -it --rm -v $PWD:/workspace thomasweise/docker-texlive-full:2.0 /bin/bash
cd /workspace
./pdf2eps.sh 1 example example_out
exit
```

Note the usage of pdf2eps.sh:
```
pdf2eps <page number> <pdf file without ext> <output file name without ext>
```


# 3. Check the result
In the above example, we need to check <example_out>.eps located in the directory named DIR.

