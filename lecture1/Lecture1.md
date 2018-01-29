[Go here for slides](https://docs.google.com/presentation/d/1tOZQVTZCP1eDgXEh1isQjrQF01DRNgKyvKVT9UPRlJM/edit) for the "theory" portion of class.

This is a gentle introduction to Carto, a web mapping platform that we will rely on for this course. We will first offer a few examples of what we can do with this web mapping platform, accessing the examples through this GitHub repository. We will then focus on a particular application: mapping election results for New Hampshire.  Finally, we will discuss the interests of the class, both topical and methodological.  Web mapping is a broad topic which could encompass data science, programming, journalism, design, and many other disciplines across many different topic areas.  We will narrow in on the minimally sufficient set of topics to make the course as broadly interesting as possible.

## Interesting applications

1. San Francisco [Ellis Act Evictions](http://www.antievictionmappingproject.net/ellis.html) (1997-2017)
2. Philadelphia [bike crashes](http://azavea.cartodb.com/viz/16ea1d8e-2481-11e3-aabf-3085a9a956e8/embed_map) (2007-2012)
3. New York City [median days on AirBnB to make rent](https://observatory.cartodb.com/viz/b2cb3416-dbdd-11e5-bbb3-0ea31932ec1d/embed_map), a reaggregation of [this other web map](http://insideairbnb.com/new-york-city/index.html) that relies on Mapbox and D3 (2015-2016)
4. [Global Forest Watch](http://www.globalforestwatch.org) forest cover loss (2000-2016)
5. [Global water detection](http://water.earthgenome.org) (1999-2012)
6. [Twitter reaction to Super Bowl](http://srogers.cartodb.com/viz/1b9b0670-8d15-11e3-8ddf-0edd25b1ac90/embed_map) (February 2, 2014)
7. [Tweets mentioning "sunrise"](http://cartodb.s3.amazonaws.com/static_vizz/sunrise.html?title=true&description=true) (April 6, 2014)
8. [Alcatraz escape](https://carto.com/blog/dev-interview-fedor/) (June 11, 1962)

## Guided tutorial: get started with styling

1. **Get the data**.  Navigate to the [Harvard Election Data Archive](https://dataverse.harvard.edu/dataverse/eda) and download [`NH_Shapefile.zip`](https://www.dropbox.com/s/wzwqi70xg6qcbwi/NH_Shapefile.zip?dl=1), also found [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/16219).  Click the link and accept the terms of use to save it locally.  The compressed archive (the `.zip` file) has all of the geospatial and metadata associated with a shapefile. You can check out [this readme file](https://www.dropbox.com/s/h2aliissb2941f3/NH-notes.rtf?dl=0) for info about the files in the data set.

2. **Sign up for CartoDB**.  Navigate to [carto.com](http://www.carto.com).  Click `Sign Up`. (*Note: It may be worth investing in a password manager, like [1Password](https://1password.com/).*)

3. **Connect the dataset**.  Follow the instructions found [here](http://docs.cartodb.com/cartodb-editor/datasets/#connect-dataset) to connect the `NH_Shapefile.zip` dataset.

4. **Style the map**.  The objective is to communicate information that is distributed spatially.  How would we communicate the counties where Democrats constituted more than 50% of the vote in 2008?  What about those counties that are relatively small (with respect to land area)?

## Guided tutorial: get started with animated maps

1. **Get the data**.  Download active fires from [this repository](https://github.com/robinkraft/web-mapping/blob/master/lecture1/active_fires.csv), and add it to Carto as a dataset. Better yet, connect the dataset rather than uploading it from your computer.

2. **Examine the data**. What is the date range of this dataset? (Use the sorting options in the dataset view. We will write SQL queries later to directly answer this questions.) What is the geographic extent?

3. **Create the map**. Click the `CREATE MAP` button.

4. **Style the map**.  Select ANIMATED as the aggregation option for the active fires later, and then select Heatmap as the animated type.  Ensure that the animation occurs, and that the size makes sense.  We will review the additional options in class.

## Account Hygiene

Go to `<username>.carto.com/dashboard/` to view all of your maps. Switch to data sets to view the data sets. If you start running out of space in your account, you can delete the maps and data sets from these views.

## What do you want to learn?

The topic of web mapping is broad.  We will cover the core skills for functional competence.  These skills can be applied to a number of different topics with a variety of concentrations.  I want to ensure that this course is not only useful, but also interesting to the broadest set of students possible.  With that, consider the following topics and methods that we can ensure we touch in this course.  What would be most interesting?  What are your backgrounds?  How can web mapping be used to further your studies?

Here are a few options for the **methods**:

1. Satellite image processing
2. Data formats
3. API calls
4. Spatial filtering queries (SQL coding)

Here are a few options for the **topics**:

1. Environment
2. Politics
3. Journalism
4. Finance/Economics

## Queries from class
`SELECT * FROM active_fires`  
`SELECT COUNT(*) FROM active_fires WHERE date > '2016-06-01'`  
`SELECT AVG(p_08) FROM nh_final`  
`SELECT * FROM nh_final WHERE p_08 > 0.5`  

## Maps from class
* [NYT map of the Santa Rosa fires](https://flowingdata.com/2017/10/16/map-of-santa-rosa-fires/)
* [Smoke map animation](https://twitter.com/stamen/status/918210924615426049)
* [Stories behind a line - migrant paths to Italy](http://www.storiesbehindaline.com/)

## Slides from class
[Slides in Google Docs](https://docs.google.com/presentation/d/1tOZQVTZCP1eDgXEh1isQjrQF01DRNgKyvKVT9UPRlJM/edit)

## Readings for week 2

[Why map portals don't work](http://mapbrief.com/2013/02/05/why-map-portals-dont-work-part-i/)  
[Paralysis of choice - Why map portals don't work part II](http://mapbrief.com/2013/02/07/paralysis-of-choice-why-map-portals-dont-work-part-ii/)  
[The tyranny of requirements - Why map portals don't work part III](http://mapbrief.com/2013/02/11/the-tyranny-of-requirements-why-map-portals-dont-work-part-iii/)  
[An iconography of confusion - Why map portals don't work part IV](http://mapbrief.com/2013/02/19/an-iconography-of-confusion-why-map-portals-dont-work-part-iv/)  
[The waiting is the hardest part - Why map portals don't work part V](http://mapbrief.com/2013/02/21/the-waiting-is-the-hardest-part-why-map-portals-dont-work-part-v/)  

## Assignment
For a topic that interests you, find relevant data and make a map in Carto that tells a particular story for a particular audience. You should style your map as appropriate. For example you could use the heatmap style (points), or multi-colored choropleth (polygons), or create an animation. Then write SQL queries to describe key columns in the data set - get the minimum, maximum, and average.

Publish your map (be sure to update the permissions so I can see it), and use Canvas to submit the URL along with answers to the following questions:  
* What is in this data set, and why did you choose it?  
* Who is your audience?  
* What story are you trying to tell? Or what do you want your user to be able to learn from your map?  
* Who is one person in that audience that you could ask for feedback. Why did you choose them? If you can, get their feedback on the map and include it here.  
* For one column of your choosing, what are the minimum, maximum, and average values for that column? Include your SQL queries in your response [This page may be helpful](https://www.postgresql.org/docs/8.0/static/functions-aggregate.html).
