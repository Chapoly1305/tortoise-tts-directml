# Tortoise-DirectML 


Tortoise is a proof-of-concept project that try to run Tortoise with AMD GPU on Windows by calling DirectML. 

<br>


# Environment Requirement 


**Python 3.10** Due to the constrain of DirectML, this version of python is mandatory. 


To mitigate potential environment conflict, it's strongly suggested to have torch, torchaudio, torchvision removed from your site-packages (in case of being carry-over to virtualenv) then use virtualenv for testing this project.


<br>

# Setup Virtual Environment
``` CMD
virtualenv venv 
venv\Scripts\activate.bat
pip install torch-directml torchaudio torchvision numba inflect psutil transformers
cd tortoise-tts-directml
python -m pip install .
```

I understand environment setup is sometime fastracting, in case your environment can't work as expected. 

[Here is a compressed working venv](https://drive.google.com/file/d/1-zSrs1La-ZNLUTf2aiMjSaAI2JOhdQ2P/view?usp=sharing)

<br>

# Available Scenarios
There are some functions do not supported by DirectML at this moment, which lead to not all feature of Tortoise project can be directly used. Only the following scenarios are supported. Some degree of computation are done by CPU because DirectML compatibility issue, which might reduce performance compares to full CUDA. 
The parameters of **--half**, **--batch-size**, and **--preset** will affect generation speed significantly. It's recommended to use a lower configuration for testing purpose for reducing the wait time. 

**TextToSpeech - Short**


``` CMD
python tortoise\do_tts.py --voice random --preset ultra_fast --text "Hello World" 
```

**TextToSpeech - Long**


``` CMD
python tortoise\read.py --textfile document.txt --voice random --preset ultra_fast
```

**TextToSpeech - Long&Fast**


``` CMD
python tortoise\read_fast.py --textfile document.txt --voice random --preset ultra_fast
```
