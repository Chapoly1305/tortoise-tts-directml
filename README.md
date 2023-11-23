# Tortoise-DirectML 


Tortoise is a proof-of-concept project that try to run Tortoise with AMD GPU on Windows by calling DirectML. 


# Environment Requirement 


**Python 3.10** Due to the constrain of DirectML, this version of python is mandatory. 


To mitigate potential environment conflict, it's strongly suggested to have torch, torchaudio, torchvision removed from your site-packages (in case of being carry-over to virtualenv) then use virtualenv for testing this project.

# Setup Virtual Environment

``` CMD
virtualenv venv 
venv\Scripts\activate.bat
pip install torch-directml torchaudio torchvision numba inflect psutil transformers
cd tortoise-tts-directml
python -m pip install .
```


# Available Scenarios
There are some function does not supported by DirectML, which leads to not all feature of Tortoise project can be directly used. At this moment, only the following scenarios are supported. 


**TextToSpeech**


``` CMD
python tortoise/do_tts.py --voice random --preset fast --text "Hello World" 
```
