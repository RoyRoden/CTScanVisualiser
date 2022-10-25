# CTScanVisualiser
A Unity scene setup to generate a 3D Texture from a series of CT scans and turn it into a volume of particles

![CTScanVisualiser](https://user-images.githubusercontent.com/1048085/197761936-0833e41e-2d0f-4335-aa3f-a5eed0bdd02f.gif)

## Instructions
You'll find a scene named "CT" and if I didn't forget to package something should look like in the screenshot below.
There are multiple gameobjects:
* Texture3DGenerator - if you hit play it generates a 3D texture under the Assets folder using the MRI images inside the DICOM_PNGs_256 folder.
* Texture3D_VFXGraph - this gameobject relies on VFX graph to generate a volume of particles which colours are samples from a 3D texture
* Texture3D_Shader - this gameobject uses a shader (copied directly from the 3D Texture Unity documentation) to render it
<img width="655" alt="CTScanVisualiser" src="https://user-images.githubusercontent.com/1048085/197761098-0e980b3c-efff-4ee4-9792-1c6e033c9bef.png">
