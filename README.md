# MeteoriteDataPoster
Poster Datavisualization of Meteorite Landings on Earth

# Synopsis
This page explains the visualization of open source data in PlotDevice (a Python-based graphics language).<br>

# Data
The data that is used is found on the Open Nasa - open data website. This comprehensive data set from The Meteoritical Society contains information on all of the known meteorite landings. The Fusion Table is collected by Javier de la Torre and they've also provided an XLS file that consists of 34,513 meteorites.
<br>
<br>
Source of data:
https://open.nasa.gov/open-data/ <br>
--> https://data.nasa.gov/Space-Science/Meteorite-Landings/gh4g-9sfh
<br>
<br>
The JSON file that they provide was a browser version that I couldn't really work with, so I downloaded the CSV file and converted it into a JSON file by using Mr. Data Converter (https://shancarter.github.io/mr-data-converter/) and I cleaned the file up by using a beautifier (http://jsbeautifier.org/).

<h3> Data in the File </h3>
The file includes the following fields:<br>
<br>
_ name<br>
_ id<br>
_ nametype<br>
_ recclass<br>
_ mass (g)<br>
_ fall<br>
_ year<br>
_ reclat<br>
_ reclong<br>
_ GeoLocation<br>
<br>

# Process

<h3>1</h3>
Research about open source data <br>

<h3>2</h3>
Find data source(s) <br>

<h3>3</h3>
Choose an interesting topic (in this case meteorite landings) <br>

<h3>4</h3>
Decide what data fields are useful and what would be a good way to visualize this: I decided that for the landing of meteorites, the geolocation, mass (g) and year would be the most useful information. Later I decided to make two different visualizations based on the 'fall' field: I divided it in 'fell' and 'found'. The use of a worldmap to visualize this all together seemed logical. <br>

<h3>5</h3>
Creating the PlotDevice code: I added a worldmap to the background and adjusted the size to the size of this background image. Then I defined the mapValue (The result is an immutable map which is a transformation of the original map (all values are incremented by one). Once the map method terminates, the new map is actually holding those new values) because I'm working with longitude and latitude (for the geolocation). This helps placing the ovals on the right geolocation. <br>
<br>
I import the json file that I'm using and give it the name 'meteordata': this way I can refer to the jsonfile throughout the code in PlotDevice. Next, I'm creating a ForLoop (to repeat the following block of code multiple times) and in the ForLoop I'm creating an If Statement (i.e. if the statement that follows after the If Statement is true, it will be printed). I start of with saying that I only want to deal with the 'fell' or 'found' meteorite landings in the json file (this way I'm exluding either one of the two).<br>
Next, I have to adjust the 'year' field in the json file. I can't use the information from the json file because it consists of multiple elements(slashes, spaces and comma's), and therefore it isn't recognized as a number. I'm converting this string into integers (int) and split it up by removing the slashes and spaces so only the year will be left. <br>
<br>
Next, I'm defining the reclong and reclat from the json file into the values 'lon' and 'lat',  and I'm defining the mass to be a value that can define the diameter of the drawn ovals (I divide this value by x so the ovals won't be too big). I'm also making sure that the very small ovals (meteorites) with a mass below 100, will be divided by a smaller number (so they will still be visible). <br>
<br>
The gradient in color is dependant of the year (with a range from 1850-2017). I made the overall color settings a bit transparent so you can see the smaller, underlying meteorite landings shine through the bigger ones (this way, they won't disappear). I added a small stroke to the ovals so they can be better distinguished from the others.<br>
<br>

N.B.<br>
For the 'fell' visualization, the color is dependant of the year the meteorites fell in. For the 'found' visualization, the color is dependant of the mass of the meteorite, because the year isn't a very important factor in this case. 

<h3>6</h3>
Export the outcomes as pdf and add a title for the poster.<br>

<h3>7</h3>
Update Github Page<br>

# Posters

![alt text](https://github.com/nndbkkr/MeteoriteDataPoster/blob/master/Artboard1.png)

![alt text](https://github.com/nndbkkr/MeteoriteDataPoster/blob/master/Artboard2.png)

# License 
MIT License

Copyright (c) 2017 Graphic Design Arnhem at ArtEZ Academy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

