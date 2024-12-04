# Endless-Neon
Team members: Annie Qiu, Catherine Cheng, Yifan Lu

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
| Time                          | Annie Qiu                                                                                      | Catherine Cheng                                                                              | Yifan Lu                                                                                                   |
|-------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| **Week 1: 2024/11/6 - 2024/11/13** | Factory building (FB) generator & basic light billboar setup | Traditional building (TB) generator & basic light billboard setup                            | Create tileable texture and material with substance designer. (Concrete/Metal Wall FB, Brick/Wood Wall TB, Roof TB, Road and pedestrian walk, Rolling door)PDG: City Layout & Procedural city generation pipeline |
| **Week 2: 2024/11/14 - 2024/11/20** | Refine factory generator & Billboard generator& Integration with PDG                                             | Refine building models & integrate with the pipeline & integrate with material                                         | PDG: City Layout & Procedural city generation pipeline                                  |
| **Week 3: 2024/11/21 - 2024/11/25** | Accessory modeling: Bridge; stairs; VFX Snow (Niagara System) | Accessory modeling & texturing Tree Street lamp Trash can Utility pole                   | Accessory modeling & texturing: vender machine, blockers                                                  |
| **Week 4: 2024/11/26 - 2024/12/2**  | Layout and lighting                                                                       | Layout and lighting                                                                         | Layout and lighting                                                                                        |


## Milestone 1: Implementation part 1 (due 11/13)
Begin implementing your engine! Don't worry too much about polish or parameter tuning -- this week is about getting together the bulk of your generator implemented. By the end of the week, even if your visuals are crude, the majority of your generator's functionality should be done.

Put all your code in your forked repository.

Submission: Add a new section to your README titled: Milestone #1, which should include
- written description of progress on your project goals. If you haven't hit all your goals, what's giving you trouble?
- Examples of your generators output so far
We'll check your repository for updates. No need to create a new pull request.

### Annie Qiu
For Milestone 1, my goal was to implement a Factory Building (FB) generator along with a basic light billboard setup in Houdini. Sharing similar tasks of creating light billboar with other member, I instead chosed to focus more on creating additional asset generators(stairs, roadblock and chimney) to enhance the overall factory atmosphere. This milestone centered on building the foundational structure of the FB generator from scratch.

To achieve factory buildings generation, I created two main generators:

- Building Generator: This generator uses adjustable parameters for floors, x, y, and z dimensions to define the basic structure of the factory. The generator includes essential elements like fences, chimneys, and an elevated middle section for a more industrial feel.
![](./img/factory.gif)

- Escape Ladder Generator: With similar adjustable parameters, this generator creates escape ladders that can integrate with the factory building, adding both functionality and visual appeal.
![](./img/stairs.gif)

In addition to the main building, I developed smaller asset generators:

- Roadblock Generator: This asset allows customization of the number of triangular shapes.
![](./img/roadblock.gif)

- Chimney Generator: Here, I added an iteration parameter to create distinct, customizable chimney shapes.
![](./img/chimney.gif)

### Yifan lu

My job for Milestone1 is to create some procedural textures for both traditional building and the factory building. The textures are created with Substance Designer to give them procedural parameters. Since the most visually-impact part of the TB is the roof, I created a 2K texture with the following parameters:

| Stain Scale | Tile Hue Color | Hole Size
|---------|---------|---------|
| ![roof1](./img/roof_1.gif)| ![roof1](./img/roof_2.gif)| ![roof1](./img/roof_3.gif)|

The node network for Tile texture:
![](./img/roof_tile.png)

For the concrete texture I add more types of cracks, divos and stains to adapt to the broken vibe of our concept art.
| Large Divots | Cracks | Grunge | Albedo
|---------|---------|---------|---------|
| ![roof1](./img/concrete_1.gif)| ![roof1](./img/concrete_2.gif)| ![roof1](./img/concrete_3.gif)| ![roof1](./img/concrete_4.gif)|

The node network for Concrete texture:
![](./img/concrete.png)

### Catherine Cheng
Traditional building generator with billboard and bridges connecting different buildings:
![](img/Traditional_Building.png)
![](img/bridge.png)

Built up the pipeline to texture procedural meshes using Substance Designer & Painter:
![](img/Textured_bridge.png)

Built up the pipeline for importing .hda meshes in UE5
| UE5 World View with Texture | HDA Panel |
|---------|---------|
| ![](./img/UE5%20World%20View.png)| ![](./img/HDA%20Panel.png)| 


## Milestone 2: Implementation part 2 (due 11/25)
### MS2 Demo Video (Golden Hour🌇):
https://github.com/user-attachments/assets/79ed4a32-bc27-4735-a8d5-102933c65c61

### MS2 Features:
- PDG network to layout 3 types of buildings based on a street map

  | Stages | Image |
  |---------|---------|
  | Grid Texture | <img src="./img/citygrid.jpg" alt="Traditional" width="600"/>)|
  | Grid in Houdini| <img src="./img/pdg1.png" alt="Traditional" width="600"/>|
  | Layout in Houdini| <img src="./img/pdg2.png" alt="Traditional" width="600"/>)|
  | Layout in Unreal| <img src="./img/pdg3.png" alt="Traditional" width="600"/>)|

- Pipeline for PDG from Houdini to UE5, including building shapes and materials

| Traditional | Factory |
|-------------|---------|
| <img src="img/566_procedural_building.gif" alt="Traditional" width="600"/> | <img src="./img/factoryTex.gif" alt="Factory" width="600"/> |

  - For materials in UE5, we have written a template for further adjusting tiling, base color tone, hue, saturation, and brightness.

  | Material Template | Matierials |
  |---------|---------|
  | ![](./img/ue_material_instance.png)| ![](./img/ue_material.png)| 

- Pipeline to generate texture from SD to SP and UE5 with a custom template to compress AO, Roughness and Metallic into one texture.



| Custom Texture Template in Substance Designer | Procedural Texture in UE imported from SD |
|---------|---------|
| ![image](https://github.com/user-attachments/assets/202a2a4e-df8f-4455-abd8-34b1ec02950e)| ![sd](./img/sbsar.gif)|



### MS3 Goals:
- Billboard texture
- PDG
  - Rearrange the layout to create center of city by placing higher buildings

![屏幕截图 2024-12-04 005052](https://github.com/user-attachments/assets/3007c633-aaff-404e-8272-f16fc67fec9a)

  - building type depend on the grid size

| Stages | Image |
|---------|---------|
| Small Block | ![small](https://github.com/user-attachments/assets/d7af0e87-3c98-4fe4-b230-85d373f14a92)|
| Middle Block| ![middle](https://github.com/user-attachments/assets/29c35d5c-2548-4356-bb8c-22dfd8076f0f)|
| Large Block| ![large](https://github.com/user-attachments/assets/6803de78-0bab-469e-a641-27ed00b364f5)|

- Small models


## Final submission (due 12/2)


https://github.com/user-attachments/assets/432d2d4b-9023-492f-a6e3-598c762bcb86



