<h1 align="center">🎬 Netflix Shows and Movies Project</h1>

<p align="center">
  <img src="https://cdn.dribbble.com/userupload/34116929/file/original-26e501e97684a115bfff294b1f1d41b0.png" width="600">
</p>

<br>

<p align="center">
  🧰 <b>Tools Used:</b> MySQL, Python
</p>

<p align="center">
  📂 <b>Dataset Used:</b>
  <a href="https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies?select=titles.csv" target="_blank">
    Netflix TV Shows and Movies (Kaggle)
  </a>
</p>

<p align="center">
  🧾 <b>SQL Analysis:</b>
  <a href="https://github.com/HeyChamp29/Netflix-Shows-and-Movies-SQL/blob/main/NetflixProj.sql" target="_blank">
    View SQL Script
  </a>
</p>

<br>

<div align="center" style="max-width:800px;">
  <p>
    <b>Business Problem:</b> 🎯 Netflix wants to gain a deeper understanding of subscriber preferences and content performance across its vast library of shows and movies. With over 82,000 records spanning multiple genres, countries, and years, manually analyzing this data is nearly impossible. Without proper insights, it becomes challenging to make data-driven decisions for content strategy, marketing, and viewer engagement. Netflix needs a robust, scalable method to extract meaningful patterns that highlight popular genres, trending releases, and regional preferences.
  </p>

  <p>
    <b>Solution Approach:</b> 🛠️ I will leverage SQL to process and analyze the large dataset efficiently, enabling the extraction of key metrics such as average viewer ratings, genre distribution, release trends, and country-wise popularity. Once the data is prepared, I will use Tableau to create interactive dashboards and visualizations that allow Netflix stakeholders to explore the insights dynamically. This approach ensures that trends and patterns are easily understandable, actionable, and can directly inform Netflix’s content acquisition, recommendation systems, and marketing strategies.
  </p>
</div>

<br>

<h2>❓ Questions I Wanted To Answer From the Dataset:</h2>

<br>
<h2>1. Which movies and shows on Netflix ranked in the top 10 and bottom 10 based on their IMDB scores?</h2>
<br>

<h3>🎥 Top 10 Movies</h3>

<h3>🎥 Top 10 Movies</h3>

<ul>
  <li>
    <b>SQL Query:</b>
    <pre><code>
CREATE VIEW TOP10_MOVIES AS 
SELECT 
  TITLE,
  TYPE,
  IMDB_SCORE
FROM netflix_titles
WHERE TYPE = 'MOVIE'
ORDER BY IMDB_SCORE DESC
LIMIT 10;

SELECT * FROM TOP10_MOVIES;
    </code></pre>
  </li>

  <li>
    <b>Result:</b>
    <br><br>
    <p align="center">
      <img src="https://github.com/HeyChamp29/Netflix-Shows-and-Movies-SQL/blob/main/Question1.png" width="700">
    </p>
  </li>
</ul>

<br>

<h3>📺 Top 10 Shows</h3>

<ul>
  <li>
    <b>SQL Query:</b>
    <pre><code>
CREATE VIEW TOP10_SHOWS AS 
SELECT 
  TITLE,
  TYPE,
  DESCRIPTION,
  RELEASE_YEAR,
  IMDB_SCORE
FROM netflix_titles
WHERE TYPE = 'SHOW'
ORDER BY IMDB_SCORE DESC
LIMIT 10;

SELECT * FROM TOP10_SHOWS;
    </code></pre>
  </li>

  <li>
    <b>Result:</b>
    <br><br>
    <p align="center">
      <img src="https://github.com/HeyChamp29/Netflix-Shows-and-Movies-SQL/blob/main/Question2.png" width="700">
    </p>
  </li>
</ul>

<h3>🎞️ Bottom 10 Movies</h3>

<ul>
  <li>
    <b>SQL Query:</b>
    <pre><code>
CREATE VIEW BOTTOM10_MOVIES AS
SELECT 
  TITLE, 
  TYPE, 
  IMDB_SCORE
FROM netflix_titles
WHERE TYPE = 'MOVIE' 
  AND IMDB_SCORE IS NOT NULL
ORDER BY IMDB_SCORE ASC
LIMIT 10;

SELECT * FROM BOTTOM10_MOVIES;
    </code></pre>
  </li>

  <li>
    <b>Result:</b>
    <br><br>
    <p align="center">
      <img src="https://github.com/HeyChamp29/Netflix-Shows-and-Movies-SQL/blob/main/Question3.png" width="700">
    </p>
  </li>
</ul>

<br>

<h3>📉 Bottom 10 Shows</h3>

<ul>
  <li>
    <b>SQL Query:</b>
    <pre><code>
CREATE VIEW BOTTOM10_SHOWS AS 
SELECT 
  TITLE,
  TYPE,
  DESCRIPTION,
  RELEASE_YEAR,
  IMDB_SCORE
FROM netflix_titles
WHERE TYPE = 'SHOW' 
  AND IMDB_SCORE IS NOT NULL
ORDER BY IMDB_SCORE ASC
LIMIT 10;

SELECT * FROM BOTTOM10_SHOWS;
    </code></pre>
  </li>

  <li>
    <b>Result:</b>
    <br><br>
    <p align="center">
      <img src="https://github.com/HeyChamp29/Netflix-Shows-and-Movies-SQL/blob/main/Question4.png" width="700">
    </p>
  </li>
</ul>

<p>The IMDb score serves as a trusted benchmark for gauging the popularity, impact, and overall quality of movies and shows. The top 10 titles in this analysis reflect content that resonated strongly with audiences — receiving widespread praise for storytelling, performances, and production value. These high-performing titles represent the kind of content that keeps viewers engaged and enhances Netflix’s reputation for premium entertainment. Conversely, the bottom 10 titles reveal the less successful side of the spectrum. Their lower IMDb scores suggest weaker audience reception, which could be attributed to shortcomings in direction, narrative strength, or viewer relatability. Analyzing both extremes allows for a balanced understanding of audience sentiment. It not only identifies the standout titles that drive engagement but also highlights areas where Netflix can refine its content strategy — such as improving curation, promoting diverse genres, or re-evaluating underperforming productions. Ultimately, this comparison provides a meaningful glimpse into what viewers truly value and how their preferences shape the success of Netflix’s catalog.</p>




