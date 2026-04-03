# Data Cleaning in MySQL

<p>Full Project completed.</p>

<p>This document is the completion of the data cleaning project made by Alex the Analyst on Youtube, as part of a training with MySQL to become a data analyst.</p>

# Tips
- If you are stuck in 564 rows when loading the .csv, upload it in json. This will work and load the 2000 entries.
- STR_TO_DATE doesn't work for everyone. I had to use this piece of code to make it work:
  
<q>UPDATE layoffs_staging2
SET `date` = CASE
                WHEN `date` IS NOT NULL AND `date` <> 'None' THEN STR_TO_DATE(`date`, '%m/%d/%Y')
                ELSE NULL
            END;</q>

