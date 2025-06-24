# My Thoughts On the Data Science Piscine at 42

At 42 Berlin, we just completed a week-long Data Science "piscine". In the 42 network, 42 Berlin is quite unique in the sense that it has already twice organized a week-long piscine where international students were invited. There were quite a few of us, including students from other campuses like Abu Dhabi, Porto, Madrid, Antwerp, and Brussels.

The way these piscines are structured is with modules of increasing difficulty.

The first module had us create a PostgreSQL database in a Docker container and populate it with data from a fictional e-commerce site. There are no teachers, of course, as this is the approach of 42 schools where students work independently on projects following rigid quality guidelines and are evaluated by their peers. Even within the project requirements, there were many diverse approaches among students. Some participants were already working with data or had experience in this field. It's a great way to learn from your peers, as discussing different approaches provides insights and cements the knowledge acquired.

For instance, while the files we were given weren't enormous, dealing with over a gigabyte of CSV data presented some interesting challenges, especially in the execution times of the scripts we used. 

One common approach was using Python to connect with the Docker PostgreSQL container. Some of us used Jupyter notebooks, others used virtual Python environments on their machines - either `venv` or the newer `uv` package (written in Rust), which is proving to be a strong contender to `venv` due to its ease of use.

Makefiles were used to automate container management and PostgreSQL connections. While Python scripts were convenient for creating database tables, they faced performance challenges with data imports. The shell-based approach, using PostgreSQL's native `COPY` command through a bash script, proved significantly faster: what took 4-20 minutes with Python was reduced to under a minute using SQL commands directly.

While this might not always be the case in production environments, during development it's great to rediscover the command line's power. It's extremely fast, especially when combined with native PostgreSQL commands.

Python and the Pandas framework excel at visualizing data in a Jupyter notebook using libraries like Matplotlib. Some students used Plotly and achieved nice 3D visualizations of data clustering with K-means (this was part of the third module).

The last two modules explored more advanced concepts like training and visualizing machine learning parameters, and building predictive models.

On average, most of us completed three modules, while just a handful of students managed all five. For those who couldn't complete everything (due to part-time work or other obligations), it was valuable to get a preview of what's coming. From a pedagogical perspective, this is the right way to approach a new subject: first getting early exposure to new concepts, then returning later to deepen understanding.

I only managed to complete up to the third module since I couldn't attend every day. However, I was very satisfied with my progress. Sometimes it's better to dive deeper into a topic rather than just skimming through. The lower-level machine learning algorithms implemented in the later modules (like Random Forests and Decision Trees) deserve a closer look, even if I don't need them right now. It's important to understand what AI actually is under the hood. While some might think these traditional techniques are less relevant today, a visit to Kaggle.com shows otherwise. It's always good to have multiple tools in your arsenal.

The key takeaway: don't rely solely on abstractions - observe and understand your data, leverage SQL (which is a powerful language), and master the UNIX command line.