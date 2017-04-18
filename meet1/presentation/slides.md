% title: Introduction to ML
% subtitle: with Zoo Animals
% author: Victoria Machine Learning Meet

---
title: Presentation Directions

- pressing 'f' toggle fullscreen
- pressing 'w' toggles widescreen
- 'o' toggles overview mode


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
title: Installation

<pre>
wget https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
# or
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
</pre>

---
title: Setup

<pre>
conda create -n zoo-animals python=3
source activate zoo-animals
git clone https://github.com/rjbergerud/vic-machine-learning.git
cd vic-machine-learning
jupyter notebook zoo-animals.ipynb
</pre>
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

<!--  Have extra "stretch" slides in case this goes quickly -->
---
title: Brainstorm
subtitle:
class: img-top-center

Ideas for topics and workshops for future meets

---
title: Keep in touch

Post to our machine-learning channel on yyjtech slack w/ more ideas!

---
title: Thanks

Thank you to Limbic Media and Consulting for hosting!
