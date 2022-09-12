# usg_AI V4.0.0 --alpha
![image](https://user-images.githubusercontent.com/47798805/189568951-30b7e928-f923-4857-a15a-a3a4c3b83c45.png)

Requirement\
Above OpenCV 2.0 , Above OpenGL 3.0, Above OpenCL 2.0, Above C++ 11, Window 64x

How 2 Use

![image](https://user-images.githubusercontent.com/47798805/189315179-2202bd0b-881c-4ec2-a7b9-6f89562606a7.png)

1. Create CNN (the layer types are in https://github.com/Naptwen/usgAI/wiki/usg_AI-3-version)
3. Create DNN (the function types are in https://github.com/Naptwen/usgAI/wiki/usg_AI-3-version)
4. Create Model (the model types are in https://github.com/Naptwen/usgAI/wiki/usg_AI-3-version)
5. Coding reward function and action function then make it as shared library (if you don't know how to do see extrafn.cpp file)

** action function should be formed as c++
```c++ 
void(unsigned int &action)
```
** reward function should be formed as c++
```c++ 
void(std::vector<float> &state, unsigned float &reward, bool &termination)
```

6. Create Enviroments
7. Create Tree\
** The number of connecting CNN to DNN should be match with the channels that you want to extract from the OpenCV\
** 1 CNN means Gray channel, 3 CNN means RGB channel, 4 CNN means RGBA channel, others are not allowed\
Example\
![image](https://user-images.githubusercontent.com/47798805/189314807-ea7ec250-bebd-483f-9d62-8864596d45f8.png)

Above shows 3 channel CNN

9. run it from the command CLI as ./usg_AI.exe --run T [your tree name] [max iteration] [result save file name]
____
Example by given test files
1. Required the tree.txt, enviro.txt, ppo.txt, dnn1.txt, dnn2.txt, cnn1.txt
2. Run the game that I made game.py 
3. Double click usg_AI.exe
4. click the ENVIRO CREATE\
![image](https://user-images.githubusercontent.com/47798805/189294569-09153fad-02a8-4388-8e1f-939ea571651e.png)
5. click the SET ACTION then typing
"extrafn.dll, rewardfn,  actionfn"\
![image](https://user-images.githubusercontent.com/47798805/189294825-21826d04-15de-4b70-9c15-71704fa92825.png)
6. click the Display then cropping the area that you will run the game.py screen\
![image](https://user-images.githubusercontent.com/47798805/189295184-662e2147-f96a-4a34-b4c2-5b53e5e6e72b.png)
7. Save the file name as enviro.txt\
![image](https://user-images.githubusercontent.com/47798805/189295506-adffecb2-5c4d-4f99-a867-17ee9ba00cb0.png)
8. run the game.py\
![image](https://user-images.githubusercontent.com/47798805/189295634-f04103a5-0e75-4c64-8dd9-81d92b7571c4.png)
8. open the command(terminal) Then typing ./usg_AI.exe  --run -t tree.txt 100,000 result.txt\
![image](https://user-images.githubusercontent.com/47798805/189303660-78756217-b02b-49de-9a49-7feb0bb71e7e.png)
9. Wait 100,000 times then the neural network will be saved in result.txt
___
How 2 make Tree
1. only one enviro is allowed, only one model is allowed\
2. click the add\
![image](https://user-images.githubusercontent.com/47798805/189348929-d0ded836-ef3b-45ab-9254-db9c7615ff93.png)
3. Then click empty node then click again the right mouse button\
![image](https://user-images.githubusercontent.com/47798805/189349097-6cadd424-b34f-4259-b499-59f9c3bfefbc.png)
4. Then write the name of file that you already made such as cnn, dnn, model, enviro\
![image](https://user-images.githubusercontent.com/47798805/189349263-cadee30d-909b-4ad6-8246-42e73b09e7d4.png)
5. Then click the block then click the empty space, it will be moved in there\
![image](https://user-images.githubusercontent.com/47798805/189349369-c857972e-58a6-48d8-af54-aeed030aa9d6.png)
6. Add another\
![image](https://user-images.githubusercontent.com/47798805/189349417-fdff35b8-bbce-4cc1-bed9-dfe02a361f69.png)
7. click the node that you made then click another node\
![image](https://user-images.githubusercontent.com/47798805/189349545-c539919e-c730-45b2-b2cd-10526df11dd2.png)
8. You can see the connection from empty to test.txt the direction is from empty to test.txt\
![image](https://user-images.githubusercontent.com/47798805/189349638-72551619-0c4f-4676-8a56-0d15964bbddc.png)
9. Make shape that you want\
![image](https://user-images.githubusercontent.com/47798805/189349731-d60d7e87-a454-44c2-88bb-7e0f2812b13d.png)\
![image](https://user-images.githubusercontent.com/47798805/189349799-0f677458-f5d7-485f-9fda-bc467cb2a003.png)
10. If you want to disconnect the node direction double click the node that you want to disconnect\
![image](https://user-images.githubusercontent.com/47798805/189349901-ba52b86a-3486-4cd5-8f65-a951861670ee.png)
11. If you want to delete the node click the node then press the Delete key\
![image](https://user-images.githubusercontent.com/47798805/189349988-d71c1e17-672e-4164-b25a-74757ac92366.png)
12. If you want to save the node click the node then click the save button\
![image](https://user-images.githubusercontent.com/47798805/189350105-d46bfff8-c142-46bd-8f24-e66797110905.png)

___
<!DOCTYPE HTML>
<HTML>

<HEAD>
   USG AI
</HEAD>

<BODY>
   <PRE>
Copy Right (c) 2022 Useop Gim
Affero GNU GPL v3 license
https://github.com/Naptwen/usgAI
<details>
<summary># Comment</summary>
   I coded this program for creating an A. I with freedom under positive purpose
   for the world. So hope it is useful for mathematicians, programmers, scientists,
   and whoever is interested.
</details>
<details>
<summary># Reference and notation</summary>
   1. The origin of this software must not be misrepresented; you must not
   claim that you wrote the original software. If you use this software
   in a product, an acknowledgment in the product documentation would be
   appreciated but is not required.
   2. Altered source versions must be plainly marked as such,
   and must not be misrepresented as being the original software.
   3. This notice may not be removed or altered from any source distribution.
</details>
<details>
<summary># GNU, AFFERO LICENSE</summary>
   This file is part of the usg_AI Library
   you can redistribute it and/or modify it under the terms of the GNU Affero.
   Affero General Public License V3 as published by the Free Software
   Foundation. http://www.gnu.org/licenses/ But, WITHOUT ANY WARRANTY without
   even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
   PURPOSE. See the GNU General Public License and Affero license for more details
</details>
<details>
<summary># STD C++ LICENSE</summary>
   The core part of standard c++ library is base on the using LLVM clang library
</details>
<details>
<summary># SPECIAL PROVISION</summary>
   To prevent and make users take responsibility, for the uncontrollable and
   unpredictable dangers in the future, a special provision for using this program
   for responsibility. This library is restricted about any purpose that breaks the
   Laws of Robotic including intentness, negligence, and recklessness also
   restricted and users take responsibility.
</details>
<details>
<summary># REFERENCE FOR BASE 64 SOURCE CODE</summary>

   base64.cpp and base64.h

   base64 encoding and decoding with C++.
   More information at
     <https://renenyffenegger.ch/notes/development/Base64/Encoding-and-decoding-base-64-with-cpp>

   Version: 2.rc.08 (release candidate)

   Copyright (C) 2004-2017, 2020, 2021 René Nyffenegger

   This source code is provided 'as-is', without any express or implied
   warranty. In no event will the author be held liable for any damages
   arising from the use of this software.

   Permission is granted to anyone to use this software for any purpose,
   including commercial applications, and to alter it and redistribute it
   freely, subject to the following restrictions:

   1. The origin of this source code must not be misrepresented; you must not
      claim that you wrote the original source code. If you use this source code
      in a product, an acknowledgment in the product documentation would be
      appreciated but is not required.

   2. Altered source versions must be plainly marked as such, and must not be
      misrepresented as being the original source code.

   3. This notice may not be removed or altered from any source distribution.

   René Nyffenegger rene.nyffenegger@adp-gmbh.ch
</details>
<details>
<summary># Khronos License For OpenGL, OpenCl, OpenCV</summary>
   The core part of OpenCL, OpenGL, OpenCV are following Khronos license
   https://www.khronos.org/legal/Khronos_Apache_2.0_CLA
</details>
</PRE>
</BODY>
<BLOCKQUOTE>
   <summary># PATCH NOTE 2.3</summary>
   <PRE>
Sep 10, 2022.
1. New : Applying shared lib of reward and enviro function for runtime.
2. New : RNN model (dynamical shapes)
3. Feature : operation tree to prepare LSTM
Sep 07, 2022.
1. Edit : Visualizing Algorithms with Enviroments
2. Edit : Change run menu to enviroment and add actions
3. New : loading by tree file which includes cnn, dnn, model, enviro
4. Feature : Looking forward how to make generlizing the reward
Sep 07, 2022.
1. New : Visualizing Algorithms.
2. New : Capture the screen and cropping inside OpenGL (only for winodw now).
3. New : Model running by captured screen.
4. Feature : Learning algorithm applying algorithm and multi thread.
Sep 05, 2022.
1. Edit : Change UI
2. Fix : Font bug fix
3. New : CNN and Model creating
4. Feauture : Visualizing AI creating
Sep 04, 2022.
1. Fix : When display pixel image that were flipped, using matrix transfer fixed it.
2. New : Output text in GUI system by FreeType libraray
3. New : GUI level text input and the object structure of integration GUI interface algorithm.
4. New : File I/O system by GUI for Model algorithm and Neural network algorithm
5. Feature : Tyring to read the video buffer and automatically creating CNN for neural net
Sep 03, 2022.
1. Fix : Edit the PPO algorithm for paraller multiplication
2. New : Construct GUI for OpenGL with GLFW and GLEW
3. New : Reading Screen as Video for using CNN algorithm
4. Feauture : Trying to change OpenGLES for application
</PRE>
</BLOCKQUOTE>
<BLOCKQUOTE>
   <details>Tree
      <BLOCKQUOTE>
         The mouse over text explains what is the function of header file and some header file is directly linked to the
         original code source website
      </BLOCKQUOTE>
      <summary># API Hirechy</summary>
      <ul class="menu">
         <li>
            <a href="https://github.com/Naptwen/usgAI"><span title="This is the main program">main.cpp</span></a>
            <ul class="submenu">
               <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for connection GUI">usg_Khronos.hpp</span></a></li>
               <ul class="submenu">
                  <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for graphic and UI object">usg_OpenGL.hpp</span></span></a></li>
                  <ul class="submenu">
                     <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for text buffer on graphic interface">usg_FreeType.hpp</span></a></li>
                     <ul class="submenu">
                        <li><a href="http://freetype.org/"><button title="This is for free type API">ft2build.h</button>
                        </li>
                     </ul>
                     <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for image and video">usg_OpenCV.hpp</span></a></li>
                     <ul class="submenu">
                        <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for fragment shader for 3d object">shader.frag</span></li>
                        <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for vertices shader for 3d object">shader.vert</span></li>
                        <li><a href="https://www.glfw.org/"><button
                                 title="This is for easy making OpenGL window">glfw3.h</button></li>
                        <li><a href="http://glew.sourceforge.net/"><button
                                 title="This is for easy making VAO for OpenGL">glew.h</button></li>
                        <li><a href="https://opencv.org/"><button title="This is for loading image">imgcode.h</button>
                        </li>
                        <li><a href="https://opencv.org/"><button title="This is for loading video">video.h</button>
                        </li>
                     </ul>
                  </ul>
               </ul>
               <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for console user interface">usg_CLI.hpp</span></a></li>
               <ul class="submenu">
                  <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for console interface for AI">usg_CLI_RL.hpp</span></a></li>
                  <ul class="submenu">
                     <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for running AI program">usg_RL_AI.hpp</span></a></li>
                     <ul class="submenu">
                        <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for multi threading agents">usg_RL_hivemind.hpp</span></a>
                        </li>
                        <ul class="submenu">
                           <li><a href="https://github.com/Naptwen/usgAI"><span
                                    title="This is for setting rule and enviroment">usg_RL_rule_book.hpp</span></a></li>
                           <ul class="submenu">
                              <li><a href="https://github.com/Naptwen/usgAI"><span title="This is for RL model algorithm">usg_RL_model.hpp</span></a>
                              </li>
                              <ul class="submenu">
                                 <li><a href="https://github.com/Naptwen/usgAI"><span
                                          title="This is for Neurla network algorithm">usg_Neural.hpp</span></a></li>
                                 <ul class="submenu">
                                    <li><a href="https://github.com/Naptwen/usgAI"><span
                                             title="This is for Neurla network functions">usg_Neural_function.hpp</span></a>
                                    </li>
                                    <ul class="submenu">
                                       <li><a href="https://github.com/Naptwen/usgAI"><span
                                                title="This is for CNN network algorithm">usg_CNN.hpp</span></a></li>
                                       <ul class="submenu">
                                          <li><a href="https://github.com/Naptwen/usgAI"><span
                                                   title="This is for CNN network functions">usg_CNN_function.hpp</span></a>
                                          </li>
                                          <ul class="submenu">
                                             <li><a href="https://github.com/Naptwen/usgAI"><span
                                                      title="This is for some convenient functinos">usg_etc_algorithm.hpp</span></a>
                                             </li>
                                             <ul class="submenu">
                                                <li><a
                                                      href="https://renenyffenegger.ch/notes/development/Base64/Encoding-and-decoding-base-64-with-cpp"><button
                                                         title="This is to reduce file size and communicate through network ">base_64.h</button></a>
                                                </li>
                                                <li><a href="https://github.com/Naptwen/usgAI"><span
                                                         title="This is for intersection between GPGPU and CPU">usg_vmatrix_Merge.hpp</span></a>
                                                </li>
                                                <ul class="submenu">
                                                   <li><a href="https://github.com/Naptwen/usgAI"><span
                                                            title="This is for matrix calculation algorithm base on standard vector container">usg_vmatrix.hpp</span></a>
                                                   </li>
                                                   <li><a href="https://github.com/Naptwen/usgAI"><span
                                                            title="This is for OpenCL gpgpu kernel interchange algorithm">usg_OpenCL.hpp</span></a>
                                                   </li>
                                                   <ul class="submenu">
                                                      <li><a href="https://www.khronos.org/opencl/"><button
                                                               title="This is for OpenCL">CL.h</button></a></li>
                                                   </ul>
                                                </ul>
                                             </ul>
                                          </ul>
                                       </ul>
                                    </ul>
                                 </ul>
                              </ul>
                           </ul>
                        </ul>
                     </ul>
                  </ul>
               </ul>
            </ul>
      </ul>
   </details>
</BLOCKQUOTE>

</HTML>
