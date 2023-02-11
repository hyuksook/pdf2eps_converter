This repository provides a way to convert a pdf file to an eps file. Those who want this functionality could execute steps described below.

The functionality of this repository works properly for powerpoint files that are exported in the pdf format, based on the docker (version information of the docker is written in docker\_version.txt) installed on my computer (macOS version 12.6.1).

# Step 1. Download a docker image.
In terminal, run
```
docker pull thomasweise/docker-texlive-full:2.0
```


# Step 2. Clone this repository.
Assume that the root directory of this repository on a local computer is DIR.
Copy the pdf file that we want to convert into the root directory.



# Step 3. Convert a given pdf file to an eps file.
Run the following commands in terminal.
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


# Step 4. Check the result
In the above example, we need to check if the `example_out.eps` file located in the directory named DIR is created properly.
