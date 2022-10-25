# CTScanVisualiser
CTScanVisualiser is a Unity package that generates a 3D Texture from a series of CT scans and turn it into a volume of particles.
**Notes:** 
* Tested with Unity 2021 LTS HDRP.
* The sample CT scan images are from a DICOM dataset provided freely by Medimodel for education and research, if you find them useful please share their page (https://medimodel.com/sample-dicom-files/).

![CTScanVisualiser](https://user-images.githubusercontent.com/1048085/197761936-0833e41e-2d0f-4335-aa3f-a5eed0bdd02f.gif)

## Instructions
* Import the Unity package inside a project.

Once imported open the scene named "CT" to explore its contents. The hiearchy should have the following gameobjects:
* Texture3DGenerator - if you hit play it generates a 3D texture under the Assets folder using the MRI images inside the DICOM_PNGs_256 folder.
* Texture3D_VFXGraph - this gameobject relies on VFX graph to generate a volume of particles which colours are samples from a 3D texture.
* Texture3D_Shader - this gameobject uses a shader (copied directly from the 3D Texture Unity documentation) to render it.

Notes:
* Source images must all be of the same size when generating a 3D Texture.
* The memory impact of 3D Texture increses rapidly based on the image resolution.
* Check the documentation about 3D Textures at https://docs.unity3d.com/Manual/class-Texture3D.html.

When used in combination with the Unity Virtual Camera app, you can use a compatible iOS device to "slice" through the volume of particles by moving the device.

* Unity Virtual Camera manual: https://docs.unity.cn/Packages/com.unity.live-capture@2.0/manual/virtual-camera.html
