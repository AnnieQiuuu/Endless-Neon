# Final Project!

Team members: Annie Qiu, Catherine Cheng, Yifan Lu, Crystal Zou

## Project planning: Design Doc (due 11/6)
Before submitting your first milestone, _you must get your project idea and scope approved by Rachel, Adam or a TA._

### Design Doc
[Google Doc Link](https://docs.google.com/document/d/169RYszQZ5gILNnsS2ZpIwD5Kloa3naZebUqEEF6zlcY/edit?tab=t.0#heading=h.kq99tkua9efe)

#### Introduction
Our project is motivated by a desire to blend Eastern traditional art with the futuristic aesthetics of cyberpunk, inspired by **Ghost in the Shell** and **Blade Runner 2049** which provide impressive visual effects and stunning cyberpunk scenes. The cyberpunk style is captivating, by combining it with Eastern aesthetics which can create a unique vision of ancient and futuristic elements.

#### Goal
We want to incorporate procedural asset creation into environment creation, combine it with textures, and eventually create an astonishing scene.

#### Inspiration/reference:
| Reference | Image |
|-----------|-------|
| [Main Reference](https://www.artstation.com/artwork/dyyoeJ) | ![Image](https://cdna.artstation.com/p/assets/images/images/080/781/078/4k/li-moly-691.jpg?1728492082) |
| [Reference1](https://www.artstation.com/artwork/29kdgB) | ![Image](https://cdna.artstation.com/p/assets/images/images/062/196/048/4k/julian-calle-002.jpg?1682565090) |
| [Reference2](https://www.artstation.com/artwork/Yeg6aY) | ![Image](https://cdnb.artstation.com/p/assets/images/images/031/994/447/large/laury-guintrand-noctem-final-shot1-hd1.jpg?1605177028) |
| [Reference3](https://www.theverge.com/2017/4/1/15142948/ghost-in-the-shell-1995-original-setting-most-interesting-part) | ![Image](https://duet-cdn.vox-cdn.com/thumbor/0x0:1920x1040/750x406/filters:focal(960x520:961x521):format(webp)/cdn3.vox-cdn.com/uploads/chorus_asset/file/8261407/Ghost_Shell_1995_Screenshot_0399.jpg) |
| [Reference4](https://aiinscreentrade.com/2024/05/29/the-importance-of-theme-exploring-existentialism-in-blade-runner-2049/) | ![Image](https://aiinscreentrade.com/wp-content/uploads/2024/05/kd7329555_a_dystopian_cityscape_at_dusk_with_towering_skyscrape_121280c6-d8b8-4485-8e3e-e8b7d5df30e8.png?w=1024) |
| [Reference5](https://www.artstation.com/artwork/G89oz) | ![Image](https://cdna.artstation.com/p/assets/images/images/000/544/340/large/sergey-zabelin-hong-kong-street-patrol-1920.jpg?1443928378) |

#### Specification:
- Traditional Building Generator

| Reference  |
|---------|
| [![Image 3](https://cdna.artstation.com/p/assets/images/images/076/006/196/large/lumiere-mah-kor1988-1.jpg?1715928564)](https://www.artstation.com/artwork/6Nm4z0) |


- Factory Building Generator

| Reference 1 | Reference 2 |
|---------|---------|
| [![Image 1](https://cdna.artstation.com/p/assets/images/images/070/104/402/4k/fabio-montorzi-abandoned-viewa-ue.jpg?1701775131)](https://www.artstation.com/artwork/Ry0ZdA) | [![Image 2](https://cdna.artstation.com/p/assets/images/images/023/892/436/4k/evgeny-lukashkov-factory-texturing-2.jpg?1580681926)](https://www.artstation.com/artwork/zA318D) |

- Material fir procedural buildings(Tileable textures)
- City Layout
- Lighting(Light Billboard)
  
#### Techniques:
- Lights Generation Problem
  - Asset Generation and Placement in Houdini (Separate assets from main buildings in order to assign light textures in UE5)
  - Emissive Surfaces Assignment in UE5
- Houdini Procedural Building Generator
  - Traditional building: Will use technique from HW3 to create multiple-level eastern style buildings. We could make a series of different windows, doors, and billboards and assemble them into buildings. Between different levels, we could add an eastern style roof with adjustable height and size. On the top of the building, we could also add a procedural top roof.
  - Factory Building:  Will use technique from HW3 to create multiple-level factory-style buildings. We could make a series of wires, windows, doors， and cables, and assemble them into buildings. Between different levels, we could add some stairs among each level and smokestacks on the top of the building.
- City Generation
  - PDG: We will use a Procedural Dependency Graph in Houdini to automate and manage complex tasks in our procedural city generation pipeline. PDG allows us to efficiently handle dependencies across asset instancing, and layout generation to make large-scale cityscapes.
  - https://youtube.com/playlist?list=PLXNFA1EysfYnWlvVy1ZzpzZd6Reyxmwxj&si=ADTaVLZNjySiRL2V
- Tileable Textures:
  - Assign simple materials to classify the material in Houdini
  - Using Substance Designer to create tileable textures
  - Attach those materials in Unreal Engine 5


#### Design:
![](./Design.jpg)

#### Timeline:
| Time                          | Annie Qiu                                                                                      | Catherine Cheng                                                                              | Yifan Lu                                                                                                   | Crystal Zou                                                   |
|-------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| **Week 1: 2024/11/6 - 2024/11/13** | Factory building (FB) generator & basic light billboard setup (build upon my previous work) | Traditional building (TB) generator & basic light billboard setup                            | Create tileable texture and material with Substance Designer (Concrete/Metal Wall FB, Brick/Wood Wall TB, Roof TB, Road and pedestrian walk, Rolling door) | PDG: City Layout & Procedural city generation pipeline |
| **Week 2: 2024/11/14 - 2024/11/20** | Refine factory generator & Billboard generator                                             | Refine building models & integrate with the pipeline                                         | Integrate materials with procedural models & integrate with the pipeline                                  | Integration with two building generators & Materials |
| **Week 3: 2024/11/21 - 2024/11/25** | Accessory modeling & texturing: Bridge; stairs; traffic light; VFX Snow (Niagara System) | Accessory modeling & texturing: Tree, Street lamp, Trash can, Utility pole                   | Accessory modeling & texturing: vendor machine, blockers                                                  | PDG: Add-on accessory assigning in UE5 (create more light textures); VFX Fog (Niagara System) |
| **Week 4: 2024/11/26 - 2024/12/2**  | Layout and lighting                                                                       | Layout and lighting                                                                         | Layout and lighting                                                                                        | Finalize the project                                           |


## Milestone 1: Implementation part 1 (due 11/13)
Begin implementing your engine! Don't worry too much about polish or parameter tuning -- this week is about getting together the bulk of your generator implemented. By the end of the week, even if your visuals are crude, the majority of your generator's functionality should be done.

Put all your code in your forked repository.

Submission: Add a new section to your README titled: Milestone #1, which should include
- written description of progress on your project goals. If you haven't hit all your goals, what's giving you trouble?
- Examples of your generators output so far
We'll check your repository for updates. No need to create a new pull request.
## Milestone 2: Implementation part 2 (due 11/25)
We're over halfway there! This week should be about fixing bugs and extending the core of your generator. Make sure by the end of this week _your generator works and is feature complete._ Any core engine features that don't make it in this week should be cut! Don't worry if you haven't managed to exactly hit your goals. We're more interested in seeing proof of your development effort than knowing your planned everything perfectly. 

Put all your code in your forked repository.

Submission: Add a new section to your README titled: Milestone #3, which should include
- written description of progress on your project goals. If you haven't hit all your goals, what did you have to cut and why? 
- Detailed output from your generator, images, video, etc.
We'll check your repository for updates. No need to create a new pull request.

Come to class on the due date with a WORKING COPY of your project. We'll be spending time in class critiquing and reviewing your work so far.

## Final submission (due 12/2)
Time to polish! Spen this last week of your project using your generator to produce beautiful output. Add textures, tune parameters, play with colors, play with camera animation. Take the feedback from class critques and use it to take your project to the next level.

Submission:
- Push all your code / files to your repository
- Come to class ready to present your finished project
- Update your README with two sections 
  - final results with images and a live demo if possible
  - post mortem: how did your project go overall? Did you accomplish your goals? Did you have to pivot?

## Topic Suggestions

### Create a generator in Houdini

### A CLASSIC 4K DEMO
- In the spirit of the demo scene, create an animation that fits into a 4k executable that runs in real-time. Feel free to take inspiration from the many existing demos. Focus on efficiency and elegance in your implementation.
- Example: 
  - [cdak by Quite & orange](https://www.youtube.com/watch?v=RCh3Q08HMfs&list=PLA5E2FF8E143DA58C)

### A RE-IMPLEMENTATION
- Take an academic paper or other pre-existing project and implement it, or a portion of it.
- Examples:
  - [2D Wavefunction Collapse Pokémon Town](https://gurtd.github.io/566-final-project/)
  - [3D Wavefunction Collapse Dungeon Generator](https://github.com/whaoran0718/3dDungeonGeneration)
  - [Reaction Diffusion](https://github.com/charlesliwang/Reaction-Diffusion)
  - [WebGL Erosion](https://github.com/LanLou123/Webgl-Erosion)
  - [Particle Waterfall](https://github.com/chloele33/particle-waterfall)
  - [Voxelized Bread](https://github.com/ChiantiYZY/566-final)

### A FORGERY
Taking inspiration from a particular natural phenomenon or distinctive set of visuals, implement a detailed, procedural recreation of that aesthetic. This includes modeling, texturing and object placement within your scene. Does not need to be real-time. Focus on detail and visual accuracy in your implementation.
- Examples:
  - [The Shrines](https://github.com/byumjin/The-Shrines)
  - [Watercolor Shader](https://github.com/gracelgilbert/watercolor-stylization)
  - [Sunset Beach](https://github.com/HanmingZhang/homework-final)
  - [Sky Whales](https://github.com/WanruZhao/CIS566FinalProject)
  - [Snail](https://www.shadertoy.com/view/ld3Gz2)
  - [Journey](https://www.shadertoy.com/view/ldlcRf)
  - [Big Hero 6 Wormhole](https://2.bp.blogspot.com/-R-6AN2cWjwg/VTyIzIQSQfI/AAAAAAAABLA/GC0yzzz4wHw/s1600/big-hero-6-disneyscreencaps.com-10092.jpg)

### A GAME LEVEL
- Like generations of game makers before us, create a game which generates an navigable environment (eg. a roguelike dungeon, platforms) and some sort of goal or conflict (eg. enemy agents to avoid or items to collect). Aim to create an experience that will challenge players and vary noticeably in different playthroughs, whether that means procedural dungeon generation, careful resource management or an interesting AI model. Focus on designing a system that is capable of generating complex challenges and goals.
- Examples:
  - [Rhythm-based Mario Platformer](https://github.com/sgalban/platformer-gen-2D)
  - [Pokémon Ice Puzzle Generator](https://github.com/jwang5675/Ice-Puzzle-Generator)
  - [Abstract Exploratory Game](https://github.com/MauKMu/procedural-final-project)
  - [Tiny Wings](https://github.com/irovira/TinyWings)
  - Spore
  - Dwarf Fortress
  - Minecraft
  - Rogue

### AN ANIMATED ENVIRONMENT / MUSIC VISUALIZER
- Create an environment full of interactive procedural animation. The goal of this project is to create an environment that feels responsive and alive. Whether or not animations are musically-driven, sound should be an important component. Focus on user interactions, motion design and experimental interfaces.
- Examples:
  - [The Darkside](https://github.com/morganherrmann/thedarkside)
  - [Music Visualizer](https://yuruwang.github.io/MusicVisualizer/)
  - [Abstract Mesh Animation](https://github.com/mgriley/cis566_finalproj)
  - [Panoramical](https://www.youtube.com/watch?v=gBTTMNFXHTk)
  - [Bound](https://www.youtube.com/watch?v=aE37l6RvF-c)

### YOUR OWN PROPOSAL
- You are of course welcome to propose your own topic . Regardless of what you choose, you and your team must research your topic and relevant techniques and come up with a detailed plan of execution. You will meet with some subset of the procedural staff before starting implementation for approval.
