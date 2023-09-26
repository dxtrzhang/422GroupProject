# Code
There are three Juputer notebooks, each notebook does some part of the job:
  * scrape.ipynb: scrape the data from All Music using R

# Data
The original data scraped from AllMusic is stored in the "original" folder and the wrangled data are stored in the "wrangled" folder.

## Original data
For the original data, it will be stored as the structure shown below:
```
.
├── original
    ├── genre.csv
    ├── mood.csv
    ├── style.csv
    ├── theme.csv
    ├── 2022
    │   ├── 1
    │   │   ├── albums.csv
    │   │   └── tracks.csv
    │   ├── 2
    │   │   ├── albums.csv
    │   │   └── tracks.csv
    │   ├── ...
    ├── 2023
    │   ├── ...
    ├── ...
```
"genre", "style", "mood" and "theme" are stored seperately, each csv file contains all the data of these four attributes.  

"albums" and "tracks" are splited by release year and page number. The reason is that we should save the data we scraped ASAP, so here we save the data locally after scraping every page.

### Column definations for table `genre`
* `id`: the id of the genre;  
* `genre`: the name of the genre;  

### Column definations for table `style`
* `id`: the id of the style;  
* `style`: the name of the style;  
* `genre_id`: styles are extensions of genres, it's the column indicates which genre a style belongs to;  

### Column definations for table `mood`
* `id`: the id of the mood;  
* `mood`: the name of the mood;  

### Column definations for table `theme`
* `id`: the id of the theme;  
* `theme`: the name of the theme;  

### Column definations for table `album`
* `album`: the title of the album;  
* `duration`: the duration of the album;  
* `release_date`: the release date of the album;  
* `all_music_rating`: the rating released by All Music, it's a integer * bewteen [0, 10];  
* `recording_data`: the recording date of the album, it's actually a * string, which may be a period of time;  
* `recording_location`: the recording location of the album, it's a * string, if there are more than one recording locations, locations will * be seperated by `;`;  
* `genre_names`: the genres' names of the album. It's a string, if there * are more than one genres, genres' names will be seperated by `;`;  
* `genre_urls`: the genres' urls of the album. It's a string, if there are * more than one genres, genres' urls will be seperated by `;`;  
* `style_names`: the styles' names of the album. It's a string, if there * are more than one styles, styles' names will be seperated by `;`;  
* `style_urls`: the styles' urls of the album. It's a string, if there are * more than one styles, styles' urls will be seperated by `;`;  
* `mood_names`: the moods' names of the album. It's a string, if there are * more than one moods, moods' names will be seperated by `;`;  
* `mood_urls`: the moods' urls of the album. It's a string, if there are * more than one moods, moods' urls will be seperated by `;`;  
* `theme_names`: the themes' names of the album. It's a string, if there * are more than one themes, themes' names will be seperated by `;`;  
* `theme_urls`: the themes' urls of the album. It's a string, if there are * more than one themes, themes' urls will be seperated by `;`;  
* `url`: the url of the album;  

### Column definations for table `track`
* `num`: the number of the track in an album;  
* `title`: the title of the track;  
* `duration`: the duration of the track;  
* `url`: the url of the track;  
* `composer_urls`: the composers' urls of the track. It's a string, if there are * more than one composers, composers' urls will be seperated by `;`;  
* `composer_names`: the composers' names of the track. It's a string, if there * are more than one composers, composers' names will be seperated by `;`;  
* `performer_urls`: the performers' urls of the track. It's a string, if there * are more than one performers, performers' urls will be seperated by `;`;  
* `performer_names`: the performers' names of the track. It's a string, if there * are more than one performers, performers' names will be seperated by `;`;  
* `album_url`: the url of the album that this track belongs to;  

## Wrangled data