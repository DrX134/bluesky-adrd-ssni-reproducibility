# Raw source data

Raw Bluesky data are not tracked in this repository. Download the public source dataset cited in the repository root README.

The public notebooks expect, at minimum:

- `user_posts.tar.gz` — source post archive used by Notebook 00
- `followers.csv` — follower edge list used for follower enrichment in Notebook 01

If the downloaded public release uses different filenames, either rename the local files or update the configuration cell at the top of the corresponding notebook. Do not commit the raw source files to GitHub.
