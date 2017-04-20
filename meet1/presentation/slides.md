% title: Introduction to ML
% subtitle: with Zoo Animals
% author: Victoria Machine Learning Meet

---
title: Presentation Directions

- pressing 'f' toggle fullscreen
- pressing 'w' toggles widescreen
- 'o' toggles overview mode

---
title: Installation & Setup

<pre>
#Copy of slides & setup instructions:
https://github.com/rjbergerud/vic-machine-learning/blob/master/meet1/presentation/slides.md
</pre>
<pre>
# linux:
wget Miniconda3-latest-Linux-x86_64
bash Miniconda3-latest-Linux-x86_64
# mac osx:
wget https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh

# When prompted to add miniconda to your path in .bashrc, say yes.
# Open a new terminal session, then:
git clone https://github.com/rjbergerud/vic-machine-learning.git
cd vic-machine-learning/meet1
conda create -n zoo-animals python=3
source activate zoo-animals
pip install -r requirements.txt
jupyter notebook zoo-animals.ipynb
</pre>

---
title: Welcome

Wow, <del>21</del> 30+ RSVPs!
---
title: Around the room
build_lists: false

- Name?
- What brought you out tonight?

<!-- Slides for Zoo animals tutorial -->
---
title: Keeping it simple :)
class: segue dark

---
title: Roadmap
build_lists: true

- Around the room
- Setup
- Pandas
- Zoo-Animals
  - Exploring the data
  - Build some classifiers!
  - Testing (time-permitting)
- Brainstorm
- Hang out!  Eat, talk, listen, laugh...


---
title: Pandas

*What is a dataframe?*

---
title:

Pandas takes (originally) numpy arrays, and adds accessor methods and an index.

- Some motivation:

<pre class="prettyprint" data-lang="python">
import numpy as np

lunar_phase = [0.1, 0.2, 0.3, 0.4, 0.5, 0.6]
low_tides = [0.4, 0.0, -0.5, 0.1, 0.3, 1.1]

observations = { 'lunar_phase': lunar_phase, 'low_tides': low_tides }

  # Wouldn't it be nice be able to access as a column?
  # data['low_tides']
  # And by row?
  # data.ix[0]

</pre>
---
title: Pandas makes these actions easy:

- Want to access data as if it were a table?
- Want to easily join tables?  Select sub-tables?  
- Want to index data by date?

---
title: The pandas way
subtitle: ...with dataframes
class: segue dark nobackground

<!-- Live code this -->
---
- **Want to access data as if it were a table?**

<pre class="prettyprint" data-lang=python>

observations = { 'lunar phase': lunar_phase, 'low tides': low_tides }

df_observations = pd.DataFrame(data)
print(df_observations)
Lunar Phase  Low Tides
0          0.1        0.4
1          0.2        0.0
2          0.3       -0.5
3          0.4        0.1
4          0.5        0.3
5          0.6        1.1

#Just look at one column's data
print(df_observations['Low Tides'])
</pre>
---


** -- Want to join dataframes?**

<pre class="prettyprint" data-lang=python>
data = {'date':[
'2014-05-01 18:47:05',
'2014-05-02 18:47:05',
'2014-05-03 18:47:05',
'2014-05-04 18:47:05',
'2014-05-05 18:47:05',
'2014-05-06 18:47:05',
], 'lunar_distance': [34, 34, 34, 33, 33,33]}
df_observations2 = pd.DataFrame(data)
df_observations = df_observations.join(df_observations2)
</pre>

---


**- Want to index data by date?**
<pre class="prettyprint" data-lang=python>
df_observations['date'] = pd.to_datetime(df_observations['date'])
df_observations.index = df_observations['date']
del df_observations['date']
print(df_observations)

date                 Lunar Phase  Low Tides lunar_distance                                       
2014-05-01 18:47:05   0.1         0.4       34  (...)
</pre>

---
title: Pandas in a zoo
build_lists: true

- Pandas also has many useful utilities for importing  data
- Let's load our zoo-dataset using pandas!

---
title: Sharing notebooks

https://nbviewer.jupyter.org

---
title: Data exploration
build_lists: true

Take 5 minutes to poke around. Try using pandas and matplotlib to explore some of these questions (or come up with your own):

- What are the most common, least common features?
- Which values often occur together? (hair, milk)
- Which values never occur together? (feathers, milk)
- Which data points are outliers?  
  - i.e. are an unusual combination of values,
  - e.g. flying squirrel.

---


## What is a Classifier?

---
title: Examples of Classifiers
build_lists: true

Let's hear some examples!

- Trees
- Logistic Regression
- Naive Bayes
- Support Vector Machine (SVM)
- Boosting algorithms
- Neural Networks

---
title:

Let's try out some classifiers with our zoo-animals.

---
title: Problems...
build_lists: true

Question: What are some issues that could come up with our new classifier?
- Don't know how it generalizes
- Not enough training data to generalize
- Too little training data, to complicated a model = overfitting

---
title: Testing

We'll do it anyways...

<!--  Have extra "stretch" slides in case this goes quickly -->
---
title: Brainstorm
subtitle:
class: img-top-center

Ideas for topics and workshops for future meets

---
title: Feedback
class: segue dark


---
title: Keep in touch

Post to our machine-learning channel on yyjtech slack w/ more ideas!

---
title: Thanks

Thank you to Limbic Media and Consulting for hosting!

Thanks to Jorge, Chris, Charles, Nate, and Tana!
