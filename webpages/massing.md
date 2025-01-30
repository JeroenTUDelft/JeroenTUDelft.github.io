# Massing

- [Home](https://jeroentudelft.github.io/)
- [Planning](https://jeroentudelft.github.io/webpages/planning)
- [Configuring](https://jeroentudelft.github.io/webpages/configuring)
- [Massing](https://jeroentudelft.github.io/webpages/massing)
- [Forming](https://jeroentudelft.github.io/webpages/forming)
- [Water and Energy Calculations](https://jeroentudelft.github.io/webpages/water)
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


![flowchart closeness groundlevel analyse](https://github.com/user-attachments/assets/9c20f569-d3b2-43f7-b932-4b8309d81361)

![flowchart sound analyse](https://github.com/user-attachments/assets/1cc7d9a1-23ea-47dc-a265-b34a1d41cdde)

![flowchart golden view analyse](https://github.com/user-attachments/assets/7fa5edc2-b345-4aaa-9a8b-d78677dfbe7f)

![flowchart sun analyses](https://github.com/user-attachments/assets/ceaf1208-9ef9-4cf9-876a-8e61e91ed576)

## Growing Algorithm
![flowchart growing algorithm](https://github.com/user-attachments/assets/d68b7fa3-2fef-4703-b31a-1359d3efb65a)

![gif van growing algorithm](https://github.com/user-attachments/assets/f74af914-3e92-4ac8-963b-1e35cedc15ec)













