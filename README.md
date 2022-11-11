# CTScanVisualiser
CTScanVisualiser is a very minimal Unity package that generates a 3D Texture from a series of CT scans and turns them into a volume of particles using VFX Graph.
**Notes:** 
* Tested with Unity 2021 LTS HDRP on a gaming laptop equipped with an NVIDIA RTX 3080 graphics card.
* The sample CT scan images are from a DICOM dataset provided freely by Medimodel for education and research, if you find them useful please share their page (https://medimodel.com/sample-dicom-files/).

![CTScanVisualiser](https://user-images.githubusercontent.com/1048085/197761936-0833e41e-2d0f-4335-aa3f-a5eed0bdd02f.gif)

## Instructions
* Import the Unity package inside a project.

Once imported open the scene named "CT" to explore its contents. The hiearchy should have the following gameobjects:
* Texture3DGenerator - When active and after hitting Play, this gameobject has a script attached (Scripts/TextureArrayGenerator) that generates a 3D texture in the root of the Assets folder using images from a source folder which name can be specified in the Inspector.

![image](https://user-images.githubusercontent.com/1048085/201344074-2a205631-84d7-4cd5-afc7-b47b95007ac2.png)
* Texture3D_VFXGraph - This gameobject relies on a VFX asset (VFX/VolumetricCT) to generate a volume of particles which colours are sampled from the 3D texture generated in the previous step. Link a newly generated 3D Texture in the Properties section of the Inspector window.

![image](https://user-images.githubusercontent.com/1048085/201345069-1adfd718-ad2a-45a6-a256-9f817de977bb.png)
* Texture3D_Shader - This gameobject uses a shader (copied directly from the 3D Texture Unity documentation) to render it.

When used in combination with the Unity Virtual Camera app, you can use a compatible iOS device to "slice" through the volume of particles by moving the device.

* 80 Level article including full video sequence: https://80.lv/articles/turning-an-ipad-into-a-ct-scan-data-analyzer-using-unity/
* Unity Virtual Camera manual: https://docs.unity.cn/Packages/com.unity.live-capture@2.0/manual/virtual-camera.html

Notes:
* Source images must all be of the same size when generating a 3D Texture.
* Tested with 88 256x256 images on a gaming laptop equipped with an NVIDIA RTX 3080 graphics card. 
* The memory impact of 3D Texture increses rapidly based on the image resolution.
* Increasing the image resolution can drastically affect performance when rendering the volume of particles (VFX Graph). 
* Use the 3D Texture alone instead of the volume of particles (VFX Graph) for better performance. 
* "Out-of-the-box" the included 3D Texture shader won't allow "slicing" the volume.
* Check the documentation about 3D Textures at https://docs.unity3d.com/Manual/class-Texture3D.html.
