# Massing

## Index
- [Home](https://jeroentudelft.github.io/)
- [Planning](https://jeroentudelft.github.io/webpages/planning)
- [Configuring](https://jeroentudelft.github.io/webpages/configuring)
- [Massing](https://jeroentudelft.github.io/webpages/massing)
- [Water and Energy Calculations](https://jeroentudelft.github.io/webpages/waterandenergycalculations)
- [Forming](https://jeroentudelft.github.io/webpages/forming)
- [Reflections](https://jeroentudelft.github.io/webpages/reflections)


## The massing phase consists of:
1. Voxelcloud
2. Criteria
3. Analyses
   - Blocking analysis
   - Sun analysis
   - Ground level analysis
   - Sound analysis
   - Golden view analysis
4. Growing algorithm

After all the functions of the building are defined, have been given values for certain parameters and connections between them are defined, we now have a rough estimation of where each fucntion should be placed. To make sure the most efficient distribution of functions is realized, a voxelcloud has to be constructed and analyzed. This is proces is performed in the massing phase of the project.


## 1. Voxelcloud
In the previous phase of the proces the voxel-size was defined. With this the next step can be performed by building a voxelcloud. The voxelcloud is a large mass consisting of voxels, wich fills the intire site. All the voxels are lined up in a perfect grid to make any further calculations with this voxelcloud more efficient. The proces of building the voxelcloud out of multiple single voxels is displayed by the flowchart below.  

![flowchart voxelgrid](https://github.com/user-attachments/assets/ef53a7e6-c50b-4019-8a75-56e8264fa843)

figure 1 : Flowchart of making a voxelcloud.


![image voxelcloud1](https://github.com/user-attachments/assets/ae00d09b-782c-48bf-90da-0882c96cffb0)

Figure 2 : Voxelcloud from a north - east point of view.


![image voxelcloud2](https://github.com/user-attachments/assets/edced869-4f5c-4a4e-8b58-3e53d4c7b562)

Figure 3 : Voxelcloud form a south - west point of view.


## 2. Criteria
Once the voxel cloud is constructed, the next step is to define the criteria for evaluation. Each voxel is assessed based on these criteria through a series of analyses. For every criterion, an analysis is performed, and so each voxel is assigned with a corresponding list of values. Below, the criteria are presented along with their respective quantification.

List of criteria with respective quantification: 

1. Need_sunlight: maximize number of sun ray hits for function.
2. Need_view: maximize number of hits to view surface for function.
3. Less_noise: maximize euclidean distance from noise point to function: bier garten (<euclidean_distance: noise_point).
4. Closeness_gf: minimize vertical distance from function to Ground Floor.



## 3. Analyses
Now that all the criteria are defined, all the analyses can be performed. In every analysis the voxels that are assigend with a low value for that specific criterion are colored red, whilst every voxel that is assigned with a high value is colored green. 

### Blocking Analysis 

The first analysis we did was to check how much our building was blocking sunlight for surrounding buildings. In the flowchart below, you can see the pseudocode for the analysis, called ‘shadowcasting’. You can see that we set a threshold at a certain level of blocking. This explains why the result of this analysis leaves a hole in our voxel cloud. This hole represents all the voxels that block more sunlight than the threshold would allow. This would result in less shadow casting on the buildings on the north side of our building. The before and after are also visualized in the diagram below. 

![flowchart sunblocking](https://github.com/user-attachments/assets/331c4bfa-338f-4bc5-be10-ed1cfe77e596)

Figure 4 : Flowchart for sunblocking analysis.

![image sunblockingbefore](https://github.com/user-attachments/assets/f9db1c4e-0050-4d38-bebe-0de3bc2636f2)

Figure 5 : Voxelcloud before sunblocking analysis. 

![image sunblocking after](https://github.com/user-attachments/assets/e1528edb-21c1-4130-87ff-4d8e3d15f30f)

Figure 6 : Voxelcloud after sunblocking analysis.

![image sunblocking after without sun1](https://github.com/user-attachments/assets/21b67a9d-d502-497d-929f-30b5a1ceca71)

Figure 7 : Voxelcloud with removed voxels from north - east point of view.

![image sunblocking after without sun2](https://github.com/user-attachments/assets/38779bae-c7dc-4d1f-9e44-88f3acb07e88)

Figure 8 : Voxelcloud with removed voxels from south - west point of view.



### Sun analysis 

This analysis calculates the amount of shadow our building gets due to sun blocking of surrounding buildings. It looks very similar to the first one, only this one does not work with a threshold. It does not delete any voxels, it only adds data to the voxels, later to be used to place the functions. The number of hits per voxel is normalized to a scale of 0 to 1. This creates a gradient as a result. 

![flowchart sunanalysis](https://github.com/user-attachments/assets/0518221d-9242-450e-9a40-0b5a86ec6bb5)

Figure 9 : Flowchart sun analysis.

![image sunlight1](https://github.com/user-attachments/assets/e8cf0bdc-a2ed-4a40-b5d8-bc3c5782073b)

Figure 10 : Result of sun analysis form north - east point of view.

![image sunlight 2](https://github.com/user-attachments/assets/0afd1aaa-bd8d-4ccb-8579-50bfa948fd34)

Figure 11 : Result of sun analysis from south - west point of view.


### Ground level analysis 
This is a very simple analysis to be used in the placement of the functions. Since specific placement per floor is very important for some functions. The way it works is shown in the flowchart below. The program gets all the y-coordinates of the points in the voxel cloud and sorts them from maximum to minimum. These values are then normalized to a scale of 0 to 1, with 1 being the closest to ground level. This scale creates a gradient as a result. 

![flowchart closeness groundlevel analyse](https://github.com/user-attachments/assets/9c20f569-d3b2-43f7-b932-4b8309d81361)

Figure 12 : Flowchart of ground level analysis.

![image groundlevel1](https://github.com/user-attachments/assets/11e24afc-1df0-46f0-a471-04f91ac24d43)

Figure 13 : Result of ground level analysis form north - east point of view.

![image groundlevel2](https://github.com/user-attachments/assets/da66cd06-05a9-4057-a04a-96eb9887b148)

Figure 14 : Result of ground level analysis from south - west point of view.


### Sound Analysis
The Schiestraat is surrounded by various sound sources. The train station is close to the location and the train rails run right next to the building, but also busy streets and clubs/cafes nearby can cause a lot of noise.  To analyse the sound levels, we used DCMR documents and adapted these in Photoshop to create sound points with 5 different levels of sound ranging from 57 to 77.5 decibels in Houdini. This information is later used for the growing algorithm to assign functions that require a quieter environment to voxel points that have lower sound levels. Green voxels have a lower sound disturbance than red voxels.

![flowchart sound analyse](https://github.com/user-attachments/assets/1cc7d9a1-23ea-47dc-a265-b34a1d41cdde)

Figure 15 : Flowchart of sound analysis.

![image sound1](https://github.com/user-attachments/assets/f79d7305-a6d9-4cf8-83d0-630d2e01fe10)

Figure 16 : Result of sound analysis form north - east point of view.

![image sound2](https://github.com/user-attachments/assets/a2b9f0fd-39d0-4532-8cf0-bbedf900027a)

Figure 17 : Result of sound analysis from south - west point of view.


### Golden View analysis
Our project has the title “Rotterdam’s Golden View”, so it’s apparent that this analysis is an important aspect of the building. In this analysis, we project points onto our desired panoramic view and check to see if the voxel points have a view on these points without intersecting with other buildings or voxel points. We also opted to slant the building towards this panoramic view to ensure that this Golden View is better achieved. This analysis is later used to ensure that the dwellings are located at positions in the building with the best views. Green voxels have a better ‘Golden View’ than red voxels.

![flowchart golden view analyse](https://github.com/user-attachments/assets/7fa5edc2-b345-4aaa-9a8b-d78677dfbe7f)

Figure 18 : Flowchart of golden view analysis.

![image golden view1](https://github.com/user-attachments/assets/c7e773fe-78b1-40c7-aa45-dd3834c5d420)

Figure 19 : Result of golden view analysis form north - east point of view.

![image golden view1](https://github.com/user-attachments/assets/9b534385-3ec5-4505-be79-241a51063ca3)

Figure 20 : Result of golden view analysis from south - west point of view.




## 4. Growing Algorithm
After the completion of all the analyses, the data from both the bubblediagram and the analyses can be combined in the growing algorithm. 

The growing algorithm consists of two parts. The first part being the search for starting points and the second part being the growing of the functions, which you can see in the flowchart below. 

The imported voxel cloud contains all the data of the earlier performed analysis and stores this per voxel. Together with the data from our function-criterion file, which contains per function the desired value per analysis, the program can compute a weighted product matrix per function. All the points now hold the weighted data. With this data, the program finds the desired starting point per function. 

Continuing to the second part, the program uses these starting points (also stored in function groups) and the weighted data on the other points to grow. The program searches for neighbouring voxels per function group, finds the voxel with the highest desired value and adds it to the function group. This loop continues until each function has reached its desired area. 

A general overview of the construction of the growing algorithm is displayed below.

![flowchart growing algorithm](https://github.com/user-attachments/assets/d68b7fa3-2fef-4703-b31a-1359d3efb65a)

Figure 21 : Flowchart of the growing algorithm.

Below you can see an animation of this looping process and the final result of the growing functions.

![gif van growing algorithm](https://github.com/user-attachments/assets/f74af914-3e92-4ac8-963b-1e35cedc15ec)

Figure 22 : Animation of the algorithm growing.













