# rasa_nlu
https://rasahq.github.io/rasa_nlu/tutorial.html

 ------------------
| INSTALL RASA_NUL |
 ------------------
git clone https://github.com/himanshuchoudhary/rasa_nlu.git
cd rasa_nlu/rasa_nlu
pip install -r requirements.txt
pip install -e .

pip install rasa_nlu[spacy]
python -m spacy download en_core_web_md
#Do it with Admin permission
python -m spacy link en_core_web_md en

 -------
| TRAIN |
 -------
Online tool for Visualizing https://rasahq.github.io/rasa-nlu-trainer/
python -m rasa_nlu.train -c sample_configs/config_spacy_himan.json


 -----
| RUN |
 -----
python -m rasa_nlu.server -c sample_configs/config_spacy_himan.json

#Windows
curl -X POST "localhost:5000/parse" -d "{\"q\":\"I say american bye \" }" | python -m json.tool

#Linux
curl -X POST localhost:5000/parse -d '{"q":"I am looking for Mexican food"}' | python -m json.tool


By default, the server will look for all projects folders under the path directory specified in the configuration. When no project is specified, as in this example, a “default” one will be used, itself using the latest trained model.
