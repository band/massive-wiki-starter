# wikiStartupJournal

- notes on reviewing and testing the startup instructions for Massive
  Wiki `massive-wiki-starter` repo and for MassiveWikiBuilder  
  
2023-07-20  

1. created my own `mwStarterWiki` repository from a template of the
  `massive-wiki-starter` repo  
  
  - cloned that repo to my local Mac  

2. copied a couple of Markdown files from another wiki, just to have
  some content for basic testing  
  - added this startup journal file to keep notes and also to have some
	wiki content  
  
3. used `git` from the command line to commit and push the new content
  to the repo  

4. next, follow instructions in the README.md for "Getting Started
Locally Quickly" in the "Publishing Wiki To Website" section  

  - note: my local Python version is 3.11.4  
  - breakdown #1: git submodule update does not bring the latest MWB
    code  
	- my solution:  
	```shell
	$ git submodule sync
	$ git submodule update --init --recursive --remote
	```
  - one addition to these steps install Python venv  
  `$ python3 -m venv venv`  
  
  - install the PyPi requirements  
    prerequisites:  
	```shell
	$ source venv/bin/activate
	(venv) $ pip install --upgrade pip
	(venv) $ pip install wheel
	```
	`(venv) $ pip install -r requirements.txt`
	breakdown #2: fails when trying to install PyYAML
	```
	Collecting PyYAML==5.4.1 (from -r requirements.txt (line 6))
  Using cached PyYAML-5.4.1.tar.gz (175 kB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... error
  error: subprocess-exited-with-error
  
  × Getting requirements to build wheel did not run successfully.
  │ exit code: 1
  ╰─> [68 lines of output]
    ```
	install problem solved by setting `PyYAML>=5.4.1` in
  `requirements.txt`, installed version is 6.0.1 (need to update)  
  
  - `npm ci` `npm` needed an update
  
  
  

