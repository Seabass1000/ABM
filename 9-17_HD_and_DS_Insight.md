It is not surprising that in order for applied data science to reach positive outcomes in
human development, reliable data is a necessity. However, reliable data in developing countries
is difficult to attain because, among other problems, it involves navigating through  government
bureaucracies, is expensive, and can take over 10 years. For my insight, I decided to investigate
a solution to this data collection problem that I came across in  “Towards Data Science” article,
An Approach to Tracking Human Development through Satellite Imagery in India, by Adhya Dagar, a
researcher at the Indian Institute of Technology New Delhi (IIT Delhi). Students at a lab in IIT
Delhi trained a convolutional neural network using 7 variables as developmental indicators and
satellite images to observe and predict socio-economic Development in India without the need of
traditional methods of data collection.

Traditional methods of data collection such as a government administered census, fail to
provide reliable data as they require so much work that they happen infrequently and take a long
time to carry out. Furthermore, scientists have used satellite imagery to predict socio-economic
status in developing areas in the past by measuring light intensity at night. However, solely using
the satellite data has proved problematic since it tended to overestimate GDP and effects in the
images like the blooming effect would diffuse nightlight towards rural areas obscuring the data.
To address these concerns, IIT Delhi used satellite imagery along with machine learning to classify
areas in India with different levels of socio-economic status.

The convolutional neural network that was used is a supervised classification model. This means
that the neural network observes satellite images of an area and uses them, along with information
from previous images the model observed, to classify it as having a certain level of development.
To indicate an area’s development the researchers used 7 attributes: assets, bathroom facilities,
condition of households, fuel for cooking, main source of light, main source of water, and literacy.
Each attribute was assigned a value of 1, 2, or 3 to express the level of development it represents.
Thousands of satellite images of different areas in India were used to train the neural network.
This method works across a range of spatial dimensions and it can be applied to a small village
and a populous city alike.

Models like IIT Delhi’s convolutional neural network are indicative of good things for the
future of data science and human development as widespread use of these methods could enable
faster and more efficient data science applications when compared to current methods of data
collection such as a census.

Work Cited.

Dagar, A. (2020, September 07). An Approach to Tracking Human Development through 
	Satellite Imagery in India. Retrieved from
	https://towardsdatascience.com/an-approach-to-tracking-human-development-through-satellite-imagery-in-india-7e750b85dc90
	









