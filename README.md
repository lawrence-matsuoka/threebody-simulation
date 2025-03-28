# cpphysics

A repository to practice C++ and learn some basic physics using OpenGL.

## Learning outcomes
- Practice development in C++
- Learn OpenGL
- Apply my mathematical background to learn some basic physics

The code is mostly to get down and dirty and some experience with C++ rather than trying to make this repository look "pretty". I set a goal of trying to simulate the three body problem since I enjoyed the Netflix show and have now read 2/3 of the Remembrance of Earth's Past books that the show is based upon. This has had varying degrees of success.

There are examples that I made from scratch such as:
- hello.cpp: A basic hello world program
- circle.cpp: A basic circle created with the TRIANGLE_FAN parameter in OpenGL
- test.cpp: What ended up being a 2D program that does have three bodies but did not behave as planned
- gravity.cpp: Taken from [kavan010's gravity_sim repo](https://github.com/kavan010/gravity_sim) and modified to have three similarly sized bodies

## Dependencies

### C++
`sudo apt install libstdc++-12-dev`

### OpenGL
`sudo apt install cmake pkg-config mesa-utils libglu1-mesa-dev freeglut3-dev mesa-common-dev libglew-dev libglfw3-dev libglm-dev libao-dev libmpg123-dev`

### Wayland and X11
`sudo apt install libwayland-dev libxkbcommon-dev xorg-dev`

## OpenGL setup

### GLFW library
cd /usr/local/lib/
sudo git clone https://github.com/glfw/glfw.git
cd glfw
sudo cmake .
sudo make
sudo make install

### GLAD library
Access https://glad.dav1d.de/
Configure like the image below
![glad settings](glad.png)
Generate the zip file
Copy the directories inside of the directory /include (/glad and /KHR) into the system's /include directory 
`cp -R include/* /usr/include/`
Move the file glad.c inside the src/ directory into the current working directory
`mv src/glad.c /working/directory`

### GLM 
GLM is already downloaded from the previous apt install. Just include the headers in your .cpp files.

## Compile
`g++ sim.cpp glad.c -ldl -lglfw`

`g++ -o simulation test.cpp -lGL -lGLEW -lglfw -lm -lstdc++ -pthread`

## Physics concepts

### Velocity
$`dx/dt`$ = Change in distance over change in time. 

### Acceleration
$`dv/dt`$ = Change in velocity over change in time.

### Gravity
$`(G * m_1 * m_2)/(r^2)`$ = The gravitational constant G times the mass of the first object times the mass of the second object, divided by the distance between the masses squared.

### Relativity

## Out of scope
Actual analysis of orbits and/or determining if any system with three similarly sized bodies demonstrates periodicity.
