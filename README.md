# ACM Research coding challenge (Spring 2023)

## The beginning 
When I first started reading through the data I had a lot of big ideas and concepts that came to mind. Graphing the data in 3 Dimenions, creating different models using ML to either create more data or answer a quesiton about the data. But instead I decided to go with a much more simplier goal of just creating an HR-Diagram and trying to see how far I could extend in that direction.

## The code 
the code itself isn't extremely techincal or complicated and the attached kaggle notebook file goes into more depth into the process and code. 
~~~ python 
import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)
import matplotlib.pyplot as plt
star_data = pd.read_csv('../input/star-dataset/6 class csv.csv', names=['Temperature', 'Luminosity', 'Radius', 'Abs_magnitude', 'Star_type', 'Star_color', 'Spectral_class']) # read in the star-dataset
# create variable names for the data
star_temperature_data = star_data["Temperature"] 
star_luminosity_data = star_data["Luminosity"] 
star_radius_data = star_data["Radius"] 
star_magnitude_data = star_data["Abs_magnitude"] 
star_type_data = star_data.Star_type
star_color_data = star_data.Star_color
star_class_data = star_data["Spectral_class"]

# creating two arrays of just the numerical data of both temperature and luminosity 
star_temperature_array = star_temperature_data.to_numpy()
star_temperature_array = star_temperature_array[1:].astype(float)

star_luminosity_array = star_luminosity_data.to_numpy()
star_luminosity_array = star_luminosity_array[1:].astype(float)

# use a scatter plot to plot the data and labeling the axis
plt.scatter(star_temperature_array, star_luminosity_array, c=star_temperature_array, cmap = 'inferno')
plt.xlabel('Temperature (K)')
plt.ylabel('Luminosity (L/Lo)')
plt.title("Hertzsprung–Russell diagram")
plt.yscale('log')
plt.xscale('log')
plt.colorbar(label="Temperature (K)")
plt.show()
~~~

![image](https://user-images.githubusercontent.com/76670360/216174720-a6a42675-6aa9-4623-a860-561f31254f2b.png)

The code above is just the base HR-digram which looks relatively simple. This however did take a couple of days given that I haven't worked with python for about a year and I also was knew to handling data within a CSV file so the start of the process was just familiarizing myself again and learning how best to graph the data.

I then altered the code to showcase the difference in size using the radius data of the stars. 

![image](https://user-images.githubusercontent.com/76670360/216175355-901fde52-8ef8-4ae7-97ef-e503b8cf5a72.png)

And then I finally wanted to see if I could match the given color data to the star data points. 

![image](https://user-images.githubusercontent.com/76670360/216175594-73e1fe58-338c-4080-8b37-67ac7f64260d.png)


## Final thoughts and takeaways 
If I where to list out the biggest problems I faced or the hardest difficulties they would be that: 
1) It took longer than I expected to relearn all the different python functions and syntax. 
2) The multitude of different libraries which you can use to visualize data with seems enourmous and so I question whether there was a better library that would have made things easier. 
3) And finally I still wished I was able to do more with the data given but with time restraints I couldn't prioritize this project more than I wanted to. 

If I also where to list the positive takeways it would mainly just be that, attempting a more simplier solution at first gave me a lot better direction than I would have expected. I tend to have ambitions about new technologys that leaves me with no clear direction or goals. But starting with something that is relatively simple and doable helps me to not only grasp the concepts and new ideas easier but also sets me up perfectly to see my next step to take.
