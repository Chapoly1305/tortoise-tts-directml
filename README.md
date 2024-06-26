# Tortoise-DirectML 


Tortoise-DirectML is a proof-of-concept project that try to run Tortoise with AMD GPU on Windows by calling DirectML. 

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

[Here is a compressed working venv](https://drive.google.com/drive/folders/1mbOumQ4EH3Hjm3N4ieoUvPHV1kQle2gn?usp=drive_link)

<br>

# Available Scenarios
There are some functions do not supported by DirectML at this moment, which lead to not all feature of Tortoise project can be directly used. Only the following scenarios are supported. Some degree of computation are done by CPU because DirectML compatibility issue, which might reduce performance compares to full CUDA. 
The parameters of **--half**, **--batch-size**, and **--preset** will affect generation speed significantly. It's recommended to use a lower configuration for testing purpose for reducing the wait time. 

**The functionality somehow partially broken overtime, please temporary use --candidates 1 to workaround.**


**TextToSpeech - Short**


``` CMD
#The functionality somehow partially broken overtime, please temporary use --candidates 1 to workaround.
python tortoise\do_tts.py --candidates 1 --voice random --preset ultra_fast --text "Hello World" 
```

**TextToSpeech - Long**


``` CMD
#The functionality somehow partially broken overtime, please temporary use --candidates 1 to workaround.
python tortoise\read.py --candidates 1 --textfile document.txt --voice random --preset ultra_fast
```

**TextToSpeech - Long&Fast**


``` CMD
#The functionality somehow partially broken overtime, please temporary use --candidates 1 to workaround.
python tortoise\read_fast.py --candidates 1 --textfile document.txt --voice random --preset ultra_fast
```
