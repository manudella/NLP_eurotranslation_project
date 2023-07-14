\# EuroTranslation

EuroTranslation is a NLP project for the comparison between translators
and linguistic considerations.

REPOSITORY WITH ALL DATA AND THE TRAINED MODELS:
https://drive.google.com/drive/folders/15ST_GbtQNVxa6lxoGBZxd99QBIwzy53D?usp=drive_link

\## Installation

Use the package manager \[pip\](https://pip.pypa.io/en/stable/) to
install OpenNMT-py.

\`\`\`bash pip install OpenNMT-py git clone
https://github.com/ymoslem/MT-Preparation.git wget
https://raw.githubusercontent.com/ymoslem/MT-Evaluation/main/BLEU/compute-bleu.py
pip install sacrebleu \`\`\`

\## Usage \### calculation of BLUE score of a trained model

\`\`\`bash #download the models from the shared Google Drive \#
Translate the \"subworded\" source file of the test dataset \# Change
the model name, if needed. onmt_translate -model
models/model.fren_step_5000.pt -src
Europarl.de-it.it-filtered.it.subword.test -output
Europarl.de.translated -gpu 0 -min_length 1

python3 MT-Preparation/subwording/3-desubword.py target.model
Europarl.de.translated

python3 MT-Preparation/subwording/3-desubword.py target.model
Europarl.de-it.de-filtered.de.subword.test

python3 compute-bleu.py
Europarl.de-it.de-filtered.de.subword.test.desubword
Europarl.de.translated.desubword \`\`\` \## Authors Manuel Dellabona
503086 Alberto Roggero 509588
