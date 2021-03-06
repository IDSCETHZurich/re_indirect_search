## re_indirect_search

Indirect Object Search Algorithm for RoboEarth final demonstrator.

### Installation 

Before rosmake you may nedd to install the python module scikit-learn

	sudo apt-get install build-essential python-dev python-numpy python-setuptools python-scipy libatlas-dev libatlas3-base
	sudo pip install -U scikit-learn 
	sudo pip install -U jsonpickle
	sudo pip install simplejson

###Usage

#### Batch Learning
-	Learn all GMM models (and go for a coffee)

		rosrun re_indirect_search learner.py learn
	Note that the learning has to be done when you install the package for the first time
-	Get a dump of all the GMM models

		rosrun re_indirect_search learner.py dump <filename>

#### Inference 
-	Run the indirect_search node 

		rosrun re_indirect_search indirect_search.py
-	Test by running

		cd tests/
		./sample-inference.py
	This script uses the InferenceQuery.srv defined in this package. See script for more details.

#### One Shot Learning (For RoboEarth Demos Only)
-	Run the indirect_search node 

		rosrun re_indirect_search indirect_search.py
-	Test by running

		cd tests/
		./single-sample-learning.py
	This script uses the LearnQuery.srv defined in this package. See script for more details.

#### Uploading to RoboEarth DB
-	The following command publishes the [SemMap.msg](https://github.com/knowrob/knowrob_addons/blob/master/mod_semantic_map/msg/SemMap.msg) topics to be uploaded to the RoboEarth (~1449 SemMaps)
	
		rosrun re_indirect_search uploader.py <optional time[s] to sleep in between>
	Default value for the time option 1.0 [s]

### Notes for RoboEarth Final Demonstrator
-	For naming convensions see data/objectDefinitions.txt. This file has a one-to-one mapping between KnowRob definitions and the names used in the NYU dataset. 





	
 


 

