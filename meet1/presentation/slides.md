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

Copy of slides & setup instructions:
<pre>
https://github.com/rjbergerud/vic-machine-learning/blob/master/meet1/presentation/slides.md
</pre>

<pre>
# mac osx:
wget https://repo.continuum.io/archive/Anaconda3-4.3.1-Linux-x86_64.sh
bash Anaconda3-4.3.1-Linux-x86_64.sh
# linux:
wget https://repo.continuum.io/archive/Anaconda3-4.3.1-MacOSX-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
</pre>

<pre>
git clone https://github.com/rjbergerud/vic-machine-learning.git
cd vic-machine-learning/meet1
conda create -n zoo-animals python=3
source activate zoo-animals
pip install -r requirements.txt
jupyter notebook zoo-animals.ipynb
</pre>

---
title: Welcome

Wow, 21 RSVPs!
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
- Brainstorm
- Hang out!  Eat, talk, listen, laugh...


---
title: Pandas

*What is a dataframe?*

---
title:
build_lists: true

Pandas takes (originally) numpy arrays, and adds a index or labelled index to it.

- Some motivation:

<pre class="prettyprint" data-lang="python">
  import numpy as np

  lunar_phase = [0.1 0.2, 0.3, 0.4, 0.5, 0.6]
  low_tides = [0.4, 0.0, -0.5, 0.1, 0.3, 1.1]

  observations = zip(lunar_phase, low_tides)

  data = np.array(observations)
  isinstance(data, np.ndarray) # True
  isinstance(data[0], np.ndarray) # True

  # Wouldn't it be nice be able to access as a column
  # data['low_tides']

</pre>
---

Want to access data as if it were a table?
Want to index data by date?
Want to easily create sub-tables by selecting certain columns?

---
title: The pandas way
subtitle: ...with dataframes
class: segue dark nobackground
 ---
<!-- Live code this -->
---

<pre class="prettyprint" data-lang=python>

columns = ('Lunar Phase', 'Low Tides')
observations = zip(lunar_phase, low_tides)


data = np.array(observations)

print(pd.DataFrame(data=data,
                  columns=columns))
Lunar Phase  Low Tides
0          0.1        0.4
1          0.2        0.0
2          0.3       -0.5
3          0.4        0.1
4          0.5        0.3
5          0.6        1.1
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
title: classifiers

## What's a Classifier?

---
title: examples of classifiers
build_lists: true

Let's hear some examples!
### Examples of classifiers:
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
