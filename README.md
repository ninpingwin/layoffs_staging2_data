# Data Cleaning in MySQL

<p>Full Project completed.</p>

<p>This document is the completion of the data cleaning project made by Alex the Analyst on Youtube, as part of a training with MySQL to become a data analyst.</p>

# Tips
- If you are stuck with only 564 rows when uploading the .csv, upload it in a json format. This will work and load the 2000 entries.
- STR_TO_DATE doesn't work for everyone. I had to use this piece of code to make it work:

 ```sql
UPDATE layoffs_staging2 
SET `date` = CASE
              WHEN `date` IS NOT NULL AND `date` <> 'None'
                THEN STR_TO_DATE(`date`, '%m/%d/%Y')
              ELSE NULL
             END;
```
- for some of you having the 'None' String instead of NULL, here's how to fix it:
```sql
update layoffs_staging2
set stage = NULL
where stage = 'None';
```
- in case you uploaded the original data as texts and wanna turn a column into integer, do that:
```sql
ALTER TABLE layoffs_staging2
MODIFY COLUMN total_laid_off INT; 
```
