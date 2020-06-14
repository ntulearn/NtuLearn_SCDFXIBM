# APA (Aging Population Assistant)
Singapore has a rapidly growing agin population. Its median age increased from 34 years in 2000 to 40 years in 2015 (United Nations, 2017b). Moreover, the proportion of residents aged at least 65 years grew from 7% in 2000 to 13% in 2017 (Department of Statistics, 2017a). With this demographic shift, there is an increasing importance to look after them especially those who are more vulnerable such as elderlies who have no next-of-kin. As such, our solution hopes to address this problem by having them taken care of by the community through the use of a home system and seeks immediate attention for them when it is needed.

## How it works
Our solution is installing a home system (APA) for detecting accidents. This home system is always ready to detect for any distress signals that the elderly would sound off.

Firstly, when the elderly calls APA for help, it will be activated and will start audio recording. The audio will then be translated to English through IBM cloud and Watson Assistant will then convert the speech to text. Afterwards, this data will be sent to our Natural Language Processing (NLP) platform which then classifies the following message as either emergency or non-emergency cases. Regardless of the classification, Named Entity Recognition (NER) will also be performed to sieve out entities within the message (e.g. incident, person involved) and send a report to our database. 

For emergency cases classified by NLP, a direct call will be linked to SCDF with the report sent directly to their database, allowing for quick action and contact with the elderly involved.

For non-emergency cases, CFRs around the vicinity will be contacted via the Responder app to provide help to the elderly.

Important information such as the name of elderly, location and time of incident will be automatically included in the report sent to the database through application, thus allowing for quick response by SCDF if aid is required.


## An example of a situation
An elderly may have happened to fall down in his/her home and calls for help through the system. The elderly describes the accident to the system. With the information obtained, the information is sent to the cloud where it is processed to determine the type of injury and the level of emergency required. 

If the injury is deemed non-threatening, the system would send a request for a CFR or any civilian via the myResponder app to help the elderly. However if the injury is critical, it would immediately alert the SCDF while also seeking immediate help from any CFR in the vicinity.

In the meantime, the elderly's details will be processed with NER to form a summarised report for SCDF, hence the elderly does not have to spend time reading out such info, which allows for quick action.

