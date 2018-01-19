# Drone Flight Plan Generator for FLYLITCHI

### Prerequisites
Python 2.7 <br>
Numpy 1.14.0

### Installation
pip install dplan

### Website: https://flylitchi.com/hub <br>

### How to get the coordinates of the field?

1) Go to https://flylitchi.com/hub and search for your target location.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![searchloc](https://user-images.githubusercontent.com/11206290/35094779-49996776-fc81-11e7-9fd8-58c0b42da73a.png)

2) Click the map to generate a point and extract the coordinates from the panel.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![clickpoint](https://user-images.githubusercontent.com/11206290/35095296-eb475ac8-fc82-11e7-82b4-5e487dc3dba2.png) &nbsp;&nbsp;![getcoordinates](https://user-images.githubusercontent.com/11206290/35095469-88463588-fc83-11e7-8c18-3bac2fe029ac.png)

### Input requirement for the drone flight plan

Four corners of the field (latitude and longitude)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;corner 1 = 14.168092, 121.255055 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;corner 2 = 14.168402, 121.255369 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;corner 3 = 14.167741, 121.256036 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;corner 4 = 14.167434, 121.255701 <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![cornersfield](https://user-images.githubusercontent.com/11206290/35095787-c8142c64-fc84-11e7-878a-c2cea96d57d5.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Horizontal partition (x) and vertical partition (y)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this example x = 4 and y = 3

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![grid](https://user-images.githubusercontent.com/11206290/35096465-48f8539e-fc87-11e7-9337-4265b4d68343.png)

<b>NOTE:</b> Create <b>drone</b> folder in your root directory for the output

### Implementation of API

#### Import dplan library 
from dplan import Flight <br>
from dplan import Order <br>

#### Initialize flight 
flight = Flight()

#### Set four corners of the field
flight.setCorners(corner1 = (14.168092, 121.255055),
				  corner2 = (14.168402, 121.255369),
				  corner3 = (14.167741, 121.256036),
				  corner4 = (14.167434, 121.255701))
          
#### Set partition of x and y
flight.setPartition(x=4, y=3) <br>
unique_coordinates = fl.calculateDistance()
          
### Result 
To view the default flight plan result, import the <b>litchi.csv</b> from the </b>drone</b> folder to https://flylitchi.com/hub

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![folder](https://user-images.githubusercontent.com/11206290/35097591-bb2ac4e8-fc8b-11e7-915c-9d71b1f407c4.png) &nbsp;&nbsp;![litchi](https://user-images.githubusercontent.com/11206290/35097596-bebeb72c-fc8b-11e7-863d-545213892d8f.png) &nbsp;&nbsp;![import](https://user-images.githubusercontent.com/11206290/35097669-18067946-fc8c-11e7-8b8e-940b834a310b.png)

### Default flight plan result

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![result 2](https://user-images.githubusercontent.com/11206290/35098286-849d7508-fc8e-11e7-9e09-31f95b10e775.png)

### Customize flight plan

### Initialize order
order = Order()

#### Select point numbers in which order you prefer 
This a sample order of points <br>

list_order = [14,9,4,1,2,6,11,16,18,13,8,3,5,10,15,19,20,17,12,7] <br>
order.setPointOrder(unique_coordinates, list_order)<br>
order.start() <br>

### Result 
To view the customized flight plan result, import the <b>litchi_order.csv</b> from the </b>drone</b> folder to https://flylitchi.com/hub

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![folder](https://user-images.githubusercontent.com/11206290/35097591-bb2ac4e8-fc8b-11e7-915c-9d71b1f407c4.png) &nbsp;&nbsp;![litchi_order](https://user-images.githubusercontent.com/11206290/35098558-9e553002-fc8f-11e7-98aa-1cefc6330d7b.png) &nbsp;&nbsp;![import](https://user-images.githubusercontent.com/11206290/35097669-18067946-fc8c-11e7-8b8e-940b834a310b.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![customize](https://user-images.githubusercontent.com/11206290/35098596-d3fef206-fc8f-11e7-8f5c-8e49b80d7608.png)

### View test.py for your reference  


### MIT License

Copyright (c) 2018 Gene Romuga and Tri Setiyono

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
