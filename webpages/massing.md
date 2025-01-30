# Massing

- [Home](https://jeroentudelft.github.io/)
- [Planning](https://jeroentudelft.github.io/webpages/planning)
- [Configuring](https://jeroentudelft.github.io/webpages/configuring)
- [Massing](https://jeroentudelft.github.io/webpages/massing)
- [Forming](https://jeroentudelft.github.io/webpages/forming)
- [Water and Energy Calculations](https://jeroentudelft.github.io/webpages/wwaterandenergycalculations)
- [Reflections](https://jeroentudelft.github.io/webpages/reflections)

## Criteria
List of criteria in order of hierarchy and respective quantification: define 

1. closeness_perimeter: minimize horizontal distance from function to perimeter/façade.
2. need_sunlight: maximize number of sun ray hits for function.
3. need_view: maximize number of hits to view surface for function.
4. less_noise: maximize euclidean distance from noise point to function: bier garden (<euclidean_distance: noise_point).
5. closeness_gf: minimize vertical distance from function to Ground Floor.
6. closeness_ug: minimize vertical distance from function to Underground.
7. closeness_r: minimize vertical distance from function to Roof.
8. closeness_schiestraat: minimize horizontal distance from function to Schiestraat.
9. closeness_schiekade: minimize vertical distance from function to Schiekade.
10. a_lift_shaft/stairs: minimize horizontal distance from Lift Shaft/Stairs to function.
11. wind_pollution: minimize wind pollution by rule of thumb: height of building should not exceed twice the width and/or it should be smaller than two times the height of surrounding buildings.
12. far_sc_elderly_unit: maximize euclidean distance from function Self-Contained Elderly Unit.
13. far_assisted_living_elderly_unit: maximize euclidean distance from function Assisted-Living Elderly Unit.
14. a_shared_kitchen/livingroom: minimize horizontal distance from Shared Kitchen/Living Room (floor-shared) to function.
15. a_laundryroom: minimize horizontal distance from Laundry Room to function.
16. a_carecentre: minimize horizontal distance from Care Centre to function.


## Analyses

### Golden View Analysis
Our project has the title “Rotterdam’s Golden View”, so it’s apparent that this analysis is an important aspect of the building. In this analysis, we project points onto our desired panoramic view and check to see if the voxel points have a view on these points without intersecting with other buildings or voxel points. We also opted to slant the building towards this panoramic view to ensure that this Golden View is better achieved. This analysis is later used to ensure that the dwellings are located at positions in the building with the best views. Green voxels have a better ‘Golden View’ than red voxels.

![flowchart golden view analyse](https://github.com/user-attachments/assets/7fa5edc2-b345-4aaa-9a8b-d78677dfbe7f)

Figure 1 : 


### Sound Analysis
The Schiestraat is surrounded by various sound sources. The train station is close to the location and the train rails run right next to the building, but also busy streets and clubs/cafes nearby can cause a lot of noise.  To analyse the sound levels, we used DCMR documents and adapted these in Photoshop to create sound points with 5 different levels of sound ranging from 57 to 77.5 decibels in Houdini. This information is later used for the growing algorithm to assign functions that require a quitter environment to voxel points that have lower sound levels. Green voxels have a lower sound disturbance than red voxels.
![flowchart sound analyse](https://github.com/user-attachments/assets/1cc7d9a1-23ea-47dc-a265-b34a1d41cdde)

Figure 1 : 

### Ground level Analysis 
This is a very simple analysis to be used in the placement of the functions. Since specific placement per floor is very important for some functions. The way it works is shown in the flowchart below. The program gets all the y-coordinates of the points in the voxel cloud and sorts them from maximum to minimum. These values are then normalized to a scale of 0 to 1, with 1 being the closest to ground level. This scale creates a gradient as a result. 

![flowchart closeness groundlevel analyse](https://github.com/user-attachments/assets/9c20f569-d3b2-43f7-b932-4b8309d81361)

Figure 1 : 


### Sun Analysis 

This analysis calculates the amount of shadow our building gets due to sun blocking of surrounding buildings. It looks very similar to the first one, only this one does not work with a threshold. It does not delete any voxels, it only adds data to the voxels, later to be used to place the functions. The number of hits per voxel is normalized to a scale of 0 to 1. This creates a gradient as a result. 

![flowchart sunanalysis](https://github.com/user-attachments/assets/0518221d-9242-450e-9a40-0b5a86ec6bb5)

Figure 1 :


### Blocking Analysis 

The first analysis we did was to check how much our building was blocking sunlight for surrounding buildings. In the flowchart below, you can see the pseudocode for the analysis, called ‘shadowcasting’. You can see that we set a threshold at a certain level of blocking. This explains why the result of this analysis leaves a hole in our voxel cloud. This hole represents all the voxels that block more sunlight than the threshold would allow. This would result in less shadow casting on the buildings on the north side of our building. The before and after are also visualized in the diagram below. 

![flowchart sunblocking](https://github.com/user-attachments/assets/331c4bfa-338f-4bc5-be10-ed1cfe77e596)

Figure 1 : 

![image sunblockingbefore](https://github.com/user-attachments/assets/f9db1c4e-0050-4d38-bebe-0de3bc2636f2)

Figure 1 : 

![image sunblocking after](https://github.com/user-attachments/assets/e1528edb-21c1-4130-87ff-4d8e3d15f30f)

Figure 1 :



## Growing Algorithm
The growing algorithm consists of two parts. The first part being the search for starting points and the second part being the growing of the functions, which you can see in the flowchart below. 

The imported voxel cloud contains all the data of the earlier performed analysis and stores this per voxel. Together with the data from our function-criterion file, which contains per function the desired value per analysis, the program can compute a weighted product matrix per function. All the points now hold the weighted data. With this data, the program finds the desired starting point per function. 

Continuing to the second part, the program uses these starting points (also stored in function groups) and the weighted data on the other points to grow. The program searches for neighbouring voxels per function group, finds the voxel with the highest desired value and adds it to the function group. This loop continues until each function has reached its desired area. 

Below you can see an animation of this looping process and the final result of the growing functions.
![flowchart growing algorithm](https://github.com/user-attachments/assets/d68b7fa3-2fef-4703-b31a-1359d3efb65a)

Figure 1 : 


![gif van growing algorithm](https://github.com/user-attachments/assets/f74af914-3e92-4ac8-963b-1e35cedc15ec)

Figure 1 : 













