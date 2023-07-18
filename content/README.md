# Overview of how to use this template


1) Set up the environment

More information can be found on the sphinx webpage (https://github.com/coderefinery/sphinx-lesson) but the basic workflow is as follows:

a) Create a python virtual environment: `python -m venv venv`

b) Activate the virtual environment: `source activate venv/bin/activate`

c) Install required packages: `pip install -r requirements.txt`

d) Build local files (this can also be used for deployment):

`make html` (Output in `_build/html/`)

e) To make clean and do a full rebuild:

`make clean html`


2) Start the web page

   Run `make livehtml`

3) View your webpage

   Open a web browswer and navigate to http://localhost:8000 (or follow the link in your console).

3) Develop your webpage

   Write markdown files in this (the content) directory making sure to add a index.md file to each new subdirectory to set the hierarchy of your website.

   The index can contain markdown but needs to also contain a contents page for that directory:

   ```
	## Contents

	```{toctree}
	---
	maxdepth: 2
	---
        File1
	File2
	File3
	\```
    ```

More complex nested directroy structures can also be contructed:

   ```
   ## Contents

	```{toctree}
	---
	maxdepth: 2
	---
	Dir1/index
	File1
	Dir2/index
	File2
	\```

   ```

4) Save your changes to github:

   In order to deploy your website on githubpages you will need to:

   a) Commit your changes.
   b) Push the commits back to your repository.
   c) If the branch being targeted in `$GitRootDir/.github/workflows/sphinx.yml` (look for tag `DEFAULT_BRANCH` at the top of the file) is updated then github will kick off an `Action` to redeploy the website. 

5) Accessing your deployed github pages website

   To find the link to your now deployed webpage go to github => Actions tab => look for a workflow called "pages build and deployment" click on this and in the central workflow area of the webpage there should be a link of the format `https://epcced.github.io/@ThisRepoName@/`. This is the address of the deployed webpage.



# Writing substitutions for multiple machines

One nice feature of the sphinx system is the ability to substitue sections of the website depending on a set of conditionals making the webpage flexible.

The obvious usecase here for EPCC is the ability to tailor the course for each machine the course is used for.

To do this place the replaceable section in a file in the directory `$GitRepoRootDir/content/substitutions/substitutions_@machine_name@/filename`.

Then if the content file where you would like dynamic-deployment of the webpage put the code:

`{{ '{include} ../../substitutions/substitutions_REPLACE/filename.md\n'.replace("REPLACE",machine_name) }}`

The `machine_name` is set in `$GitRepoRootDir/content/conf.py`. You can add other parameters to this config file to produce additional variation.



# Inserting media into markdown

Images:

```
   ```{figure} ./images/YOUR_IMAGE.jpg
	CAPTION GOES HERE
   \```
```

Video:

```
   ```{raw} html
   <iframe width="700" height="400" src="https://www.youtube.com/embed/NEgbVNIo560" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   \```
```

