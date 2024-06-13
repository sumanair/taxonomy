**Note:** This is just a quick cheatsheet for the Austin/Coppell Instructlab micro-workshop. 
*Consider [ilab](https://github.com/instructlab/instructlab/blob/main/README.md) the source of truth

#For M series Macs

## Prep
In terminal window - folder of choice
* Terminal 1
    * xcode-select --install
    * mkdir instructlab
    * cd instructlab
    * python3 -m venv --upgrade-deps venv
    * source venv/bin/activate
    * (venv) $ pip cache remove llama_cpp_python
    * (venv) $ pip install instructlab
    * ilab
    * ilab init
    * ilab download
    * ls models
    * ilab serve
* Terminal 2
    * source venv/bin/activate
    * same new tab : ilab chat

## Workshop
| Terminal1    | Terminal 2 |
| -------- | ------- |
|  cd instructlab  |  cd instructlab   |
|  source venv/bin/activate  |  source venv/bin/activate   |

* Check model (optional)  `ls models`
* Check taxonomy (optional)  `ls taxonomy`

### Finding a knowledge or skills gap
| Terminal1    | Terminal 2 |
| -------- | ------- |
|  ilab serve  |     |
|    |  ilab chat   |

* Chat and find a good topic
* Fork instructlab/taxonomy. Your changes should go to your fork only.
* Use VC code to create contributions
* For knowledge contributions, you need an extra repo. [This](https://developer.ibm.com/tutorials/awb-contributing-knowledge-open-source-llms-instructlab/) or other similar resources can help
* https://www.yamllint.com/ for extra linting goodness

| Terminal1    | Terminal 2 |
| -------- | ------- |
| |Exit chat (just type `exit`)|
| |ilab diff|

* Fix issues, likely yaml, till diff is happy

| Terminal1    | Terminal 2 |
| -------- | ------- |
| |ilab generate|
| |ls generated/|

#### Training
Training may not run on some machines, since it takes a lot of resources. For this reason, training is considered optional It is fun to do, though. Lets jump right in!
| Terminal1    | Terminal 2 |
| -------- | ------- |
|Ctrl+C to kill the ilab server to save resources ||

The following can be done on either terminal
* ilab train 
* ilab test (only for M series)
* ilab convert (only for M series)
**Note:** If you do convert, your old model may get repalced with the new one.
* ls models

| Terminal1 | Terminal 2 |
| -------- | ------- |
|ilab serve --model-path <new model path> ||
| |ilab chat -m <New model name> | 

**Note: ** Expect your local model to hallucinate. Remember, this is a quantized model and is less accurate. 
Committing
* Push yur changes 
In your fork of the taxonomy:
``` 
git add .
git commit -s -m <commit message>
git push origin <main / branch>
```
**Note:** Signing your commit is important. (the `-s` above)
* Raise a Pull request to instructlab/taxnonmy
* Watch if the PR fails checks and you are asked to make corrections, if so do it

**Congrtulations!! You did it!!**

    





