# Pulse Monitoring and Analysis (PMA)

Pacemaker implants are increasingly common. Good candidates for pacemakers are people with irregular, slow, or fast heartbeats.In the United States alone, pacemaker implants have risen 56% in the last two decades, but many people with cardiovascular issues fail to recognize the symptoms at first. After receiving a pacemaker implant, patients often report feeling clearer headed and more energetic. 


## Who needs a pacemaker?

Pacemaker users are not automatically unhealthy. Lifelong endurance athletes sometimes require a pacemaker to keep their resting heart rate high enough. Otherwise healthy people with irregular heart rhythms may need a pacemaker to normalize their heart rhythms. Heart disease, aging, or taking heart-slowing medications called beta blockers can also lead to pacemaker use.


## Project Requirements

Heart patients who are candidates for pacemakers often need to examined thoroughly over the period of a few months to ascertain its need. This can be recorded and transmitted by commonly available EKG devices or through a specialized cardiac monitoring device that allows for higher accuracy. The latter typically requires an incision. Both patients and doctors require heart rate data presented to them in a lucid report. 


## Data Generation

A simple abstraction of a heart beat would be to use timestamps to represent each pulse. For this project, data generation was achieved through an incremental date function that outputs timestamps based on a gaussian probability distribution. For the sake of simiplicity, it does not reperesent periods of strenuous activity (like cycling, running, lifting etc.), but it does account for abnormal heart rates occuring at certain hours of the night. This was achieved by a hard-coding a higher standard deviation value for each pulse.    


## Data Representation

The generated timestamps are stored in a dictionary with the dates as the keys and a list of timestamps as the corresponding value. This dictionary is used as one of two steps to ensure data permanence as the data generated for each patient can be pickled and stored on disk. 

The data from this dictionary is imported onto a pandas frame that is used to measure and represent important metrics such as:

* Average BPM across a week 
* Average BPM across a day 

## Planned functionality

* Longest gap between two consecutive pulses

## Packages used

* datetime - to represent pulses as timestamps
* random - to generate pulses after every 'x' seconds
* gzip - to compress and store generated data
* pickle - data permanence and serialization
* pandas - to split and manipulate timestamps from the dictionary
* matplotlib - representing pulses across hours/days on a graph
* seaborn - visualizing data


## Usage 

It is advised to change the input parameters to the setAttributes() and setHealthAttributes methods depending on the patient. After this the code generates timestamps representing Heartbeats, the getData method can be modified if using Pace Maker or other devicces to get the data.

When the script runs completely, it gives the line chart and box plot visualizations for average heartbeat per day and per hour basis which is really helpful for doctors to study the heartbeat rythm and for further analysis.


## Usage Notes

Users are advised to refrain from displaying the contents of the dictionary for more than ~200000 timestamps. This may cause the notebook to crash. Alternatively, you may change the IOPub data rate to view the contents of the dictionary. 


## Authors

* Chetas Das - Documentation, data generation and permanence
* Jeevash Mutreja - Framing classes, integrating functions  
* Niharika Rajwadha - Data extraction, manipulation and graph representation


## Acknowledgements

* [GetQardio](https://www.getqardio.com/healthy-heart-blog/how-do-you-know-if-you-need-a-pacemaker/) for helping us better understand our project requirements
* [National heart lung blood institute](https://www.nhlbi.nih.gov/health-topics/pacemakers) 
* user4179775 on stackoverflow to help us get started with data generation
* Prof. Brian Chapman for showing us that coding in Python is fun!


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
