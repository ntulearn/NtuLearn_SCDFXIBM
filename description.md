# APA (Aging Population Assistant)
Singapore has a rapidly growing agin population. Its median age increased from 34 years in 2000 to 40 years in 2015 (United Nations, 2017b). Moreover, the proportion of residents aged at least 65 years grew from 7% in 2000 to 13% in 2017 (Department of Statistics, 2017a). With this demographic shift, there is an increasing importance to look after them especially those who are more vulnerable such as elderlies who have no next-of-kin. As such, our solution hopes to address this problem by having them taken care of by the community through the use of a home system and seeks immediate attention for them when it is needed.

## How it works
Our solution is installing a home system (APA) for detecting accidents. This home system is always ready to detect for any distress signals that the elderly would sound off.

Firstly, when the elderly calls APA for help, it will be activated and will start audio recording. The audio will then be translated to English through IBM cloud and Watson Assistant will then convert the speech to text. Afterwards, this data will be sent to our Natural Language Processing (NLP) platform which then classifies the following message as either emergency or non-emergency cases. 

Incidents with emergency labels will be immediately sent to SCDF and a call will be immediately linked between SCDF and the elderly for contact and quick action.

For non-emergency cases, CFRs around the vicinity will be contacted via the myResponder app to provide help to the elderly.

After classification, NER can be performed to sieve out important entities within each text (e.g. incident, people involved). These entities will be used to form a report that will be uploaded to the database. For emergency cases, these reports will be sent to SCDF's database immediately.

Important information such as the name of elderly, location and time of incident will be automatically included in the report sent to the database through the APA application, thus allowing for quick response by SCDF if aid is required.

For non-emergency cases, these reports serve as a form of monitoring and SCDF can act quickly on the incident if there is any escalation to emergency levels.


## An example of a situation
An elderly may have happened to fall down in his/her home and calls for help through the system. The elderly describes the accident to the system. With the information obtained, the information is sent to the cloud where it is processed to determine the type of injury and the level of emergency required. 

If the injury is deemed non-threatening, the system would send a request for a CFR or any civilian via the myResponder app to help the elderly. However if the injury is critical, it would immediately alert the SCDF while also seeking immediate help from any CFR in the vicinity.

In the meantime, the elderly's details will be processed with NER to form a summarised report for SCDF, hence the elderly does not have to spend time reading out such info, which allows for quick action.

## Explanation of Tech
For NLP, we made use of Twitter's emergency tweets for classification. However, in practical implementation, we would require a small sample of emergency/ non-emergency calls from elderly or any other targeted groups for better training of the model.

After tokenization and cleaning of words, the list of words will be passed into a Tf-idf vectorizer to transform the words into vectors with importance within each sentence, which allows the machine to use these vectors to classify into emergency/ non-emergency cases.

With the database in place, faster classification methods through deep learning such as ALBERT could be used to perform classification within the shortest time possible.

After classification, NER can be performed with SpaCy to sieve out important entities within each text (e.g. incident, people involved). These entities will be used to form a report that will be uploaded to the database. For emergency cases, these reports will be sent to SCDF's database.

With the database in place, our own NER can be built on relevant data to find more specific topics related to emergency incidents, which will help to build greater clarity within the report.
