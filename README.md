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
<br>

# Available Scenarios
There are some functions do not supported by DirectML at this moment, which lead to not all feature of Tortoise project can be directly used. Only the following scenarios are supported. 


**TextToSpeech**


``` CMD
python tortoise/do_tts.py --voice random --preset fast --text "Hello World" 
```
