# Configuring

## Index
- [Home](https://jeroentudelft.github.io/)
- [Planning](https://jeroentudelft.github.io/webpages/planning)
- [Configuring](https://jeroentudelft.github.io/webpages/configuring)
- [Massing](https://jeroentudelft.github.io/webpages/massing)
- [Forming](https://jeroentudelft.github.io/webpages/forming)
- [Water and Energy Calculations](https://jeroentudelft.github.io/webpages/waterandenergycalculations)
- [Reflections](https://jeroentudelft.github.io/webpages/reflections)


## The configuring phase consists of:
1. Voxelsize
2. Bubble diagram
   - Proces
   - Product
   - Final bubble diagram


## 1. Voxelsize
We based our voxel size on the question of what is the “minimum liveable space”?.  
Author and designer Bruno Munari provides an interesting reflection on the traditional Japanese house as follows: 
“The proportions of the rooms are expressed in tatami: [a mat of fine and tightly woven straw […] its size about three foot by six [91*182cm], the size of a man lying down.], so that a two-tatami room is about six foot by six [182*182cm], an eight-tatami room is twelve by twelve [366*366] and so on. […] The rooms are about eight feet [244cm] high, so that when one lies in bed there is not a great yawning void above one.”1, which we used and adjusted to Dutch upper median (average height of men in upper median in 2020 above 19 year’s old, 194cm tall), and further standardized to arrive at a three-by-three-by-three meter voxel.

![voxelsize](https://github.com/user-attachments/assets/a2f754a6-8ac9-4d95-a2ee-8810c5068083)
Figure 1 : Voxelsize diplayed.


## 2. Bubble diagram
### Proces

Bubble diagrams
Our initial hand drawn bubble diagrams, illustrating the distribution of the space and functions can be appreciated as follows.

![first bubblediagram1](https://github.com/user-attachments/assets/b608ba38-3c84-4ce6-8dc2-539be0dba4de)
Figure 2: Initial Bubble Diagram (no floor division).


![first bubblediagram2](https://github.com/user-attachments/assets/cbe3d8ba-4091-4017-840c-dab248edc2e1)
Figure 3 : Initial Bubble Diagram (Ground Floor).


![first bubblediagram3](https://github.com/user-attachments/assets/0dd4559b-39d7-4c00-92f0-6d9e1384b4fd)
Figure 4 : Initial Bubble Diagram (Floor (n)).


We furthermore developed a simple code to illustrate in two-dimensions the relationship between functions and their connections. 

Figure 5 shows how a bubble diagram can be used to illustrate connections (lines) between the different spaces (nodes). The size of the nodes can be used to represent the actual size of the space or the relative importance of the given space. The importance of each line, i.e.: the importance of the connection between the two spaces, can also be adjusted and the configuration/shape of the diagram will be respectfully a changed. This can be observed between Figure 6: Bubble Diagram Schieblok Ground Floor-Configuration 1 and Figure 7: Bubble Diagram Schieblok Ground Floor-Configuration 2, where the configuration of the diagram and shape is dependant on the independent variable line or “importance of connection”. In the first figure variable line is equal between “Lobby” and the three street access points: “Delftseplein/Schiestraat”, “Delftsehof” and “Schiekade”, whilst in Figure 3 variable line is equal to 1 between “Lobby” and “Delftseplein/Schiestraat” and 0.1 between the two other street access points. You can see how this affect the disposition ad arrangement of not only the concerned nodes, but of all the nodes in the network.

![scnd bubbeldiagram1](https://github.com/user-attachments/assets/3ce916e6-8d6f-4e8d-a489-3f63e76fad18)

Figure 5 : “Architectural Bubble Diagram” of standard housing unit.


![scnd bubbeldiagram2](https://github.com/user-attachments/assets/1071e24d-bde9-48b7-b4af-3ad7393a3eae)

Figure 6 : Bubble Diagram Schieblok Ground Floor-Configuration 1.


![scnd bubbeldiagram3](https://github.com/user-attachments/assets/18190eb2-969b-4240-b84c-61784f6b1702)

Figure 7 : Bubble Diagram Schieblok Ground Floor-Configuration 2.



### Product
After finalizing the floor configurations, we created the following bubble diagrams to illustrate the flow paths of the user groups within the building. These diagrams provide a schematic representation of the routes one must take to reach a specific location. To highlight key differences in movement, as shown in Figure 8, the path for an assisted elderly resident is more direct, with fewer spaces to navigate through before reaching the lobby, compared to, for example, a resident of a starter unit.

![image](https://github.com/user-attachments/assets/025d6f99-ebe8-405c-8d8e-0f20f63f21e6)

Figure 8 : General flowpath of all the user groups.

![image](https://github.com/user-attachments/assets/d87dd5f0-65a9-4f2e-9734-ee8c5f6e7805)

Figure 9 : Flowpath elderly.


![image](https://github.com/user-attachments/assets/0b1a3e24-0195-4f74-b230-9cb681e958f0)

Figure 10 : Flowpath starter.


![image](https://github.com/user-attachments/assets/d0e4b888-939b-45e7-92bb-2c18753b7837)

Figure 11 : Flowpath student.


### Final Bubble diagram

To make even more use of the bubble diagram concept, we used a Houdini-script to illustrate how the different fucntions would be distributed through the building. In this script every function gets assigned to a point in a circle. This point gets weighted according to the amount of space it takes up in the building and the importance of the function itself. This importance is a quantified value. You could see it as an average per column from figure 6 on the planning page. The Houdini-script than calculates the exact and most efficient position for every function, and by how much every function needs to "stick" to another function. The workflow for this proces is diplayed in the flowchart below


![flowchart bubblediagram](https://github.com/user-attachments/assets/2c2eaa98-2ab9-4ecc-b8a9-6b7dfdf78b96)

figure 12 : Flowchart bubble diagram.


![final bubble diagram2](https://github.com/user-attachments/assets/44d8e5a3-aae5-4bfb-8944-da65985604b7)

Figure 13 : Bubble diagram starting position.


![final bubblediagram annimation](https://github.com/user-attachments/assets/02d1149b-8a7f-4c2f-8b26-1c91ac47244c)

Figure 14 : Bubble diagram animation.


![final bubblediagram1](https://github.com/user-attachments/assets/4f01ff2e-422e-496c-86dd-59f86dcc6961)

Figure 15 : Bubble diagram final position.





