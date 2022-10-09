# Auto Landscape Material Showcase
###### UE 4.27.2

## Features
- Landscape Material With 3 Layers
	- Base Layer (Bottom)
	- Slope layer (Cliffs)
	- Flat Layer (Grass)
- Material Functions
	- Normal Mask (Used For Slopes and Flat Areas)
	- Texture Tiling Break Up For Close And Mid Ranges
- Runtime Virtual Textures
	- Used To Optimize Landscape Material Performance

### Potential Future Features (If I Feel Like Adding Them)
- Height Blending Object Materials With Landscape
- Better Texture Tiling Break up
- More Mask Types
- Auto Grass Setup (this one is kinda complicated to optimize)

## How To Setup Auto Landscape In Your Project
1. In your project settings, turn on **Virtual Texture Support**
2.  Migrate **M_Landscape** under **Materials/BaseMaterials/Landscape** into your project
3. Make 2 **RuntimeVirtualTexture** assets in your project
4. Open one of them and set its **Virtual Texture Context** to **WorldHeight** (the other one will default to material properties)
5. In your level, put 2 **RuntimeVirtualTextureVolumes**
6. Set each of the RVT assets as the **Virtual Texture** in one of the **RVTVolumes**, select your **Landscape** as the **Bounds Align Actor** and press **Set Bounds**
7. Select your landscape.  Add the two RVT assets you made to the **Draw In Virtual Textures** array.
8. Create a **Material Instance** of **M_Landscape**. Assign the RVT asset you made which holds the material properties to the **RVT_Color** Parameter. Assign your own CR/NOH textures, change the parameters if you like, and lastly assign the instance to your **Landscape**.
9. Change to **Landscape Mode**. Under the **Paint** section, press the **plus icon (Create Layer Info)** next to each layer.
Your landscape should automatically be painted with the textures you set. You also have the option to paint over the auto material in landscape paint mode.


## Disclaimer
I do not own the textures used in the showcase material (except for clouds). They are Quixel assets that I packed into CR/NOH textures as the engine does not have good default textures I can use.