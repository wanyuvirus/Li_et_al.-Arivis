# Li_et_al.-Arivis
Codes used in the study by Li et al. 2024

These are custom-built pipelines within the Arivis 4DFusion commercial analysis software. Therefore, they can only be used with an Arivis 4DFusion license. Please find the system requirements, installation guides, and tutorials for how to install and use Arivis 4DFusion at https://kb.arivis.com/vision4d-arivis-pro.

Pipelines are in .xml format.

All raw image data files (.nd2 format) are supported by Fiji. For analysis, they need to first be converted to .sis format. This can be done using the free Arivis SIS Converter Pro software, or by dragging the files directly into Arivis 4DFusion. While using Arivis SIS Converter, untick "Save with compression" to preserve image quality.

To analyze converted .sis format images,

1. drag .sis images into Arivis 4DFusion v4.0.
2. Open Analysis panel.
3. In the menu of the Analysis panel, select Import.
   Import pipeline Virus_Detection.
4. Begin analysis. Analysis should end in less than 3 minutes.
   An object table will appear showing a list of virus objects detected in the image.
5. In the menu of the Analysis panel, select Import.
   Import pipeline Create_Membrane_Cytoplasm_Get_VIRUS_FINAL.
6. In the pipeline, navigate to Export modules for exporting Membranes, Cytoplasm, and viruses_in_membrane_in_cell.
   Select the directory to save excel outputs and rename the output files according to the image analyzed.
7. Begin analysis. Analysis may run for 10-15 minutes.
   An object table will appear showing a list of objects detected in the image.
   Excel files are exported to the indicated directory. Note that the pipeline will end prior to exporting if the file name is duplicated (i.e. output files are not renamed).
   In the Excel files, the #Children column contains numbers of virus objects determined to be in the parent object (cytoplasm or membrane).
8. Cytoplasm objects with a volume of < 500 μm^3 typically represent cells cut off at the edge of the imaged volume, or cellular blebs that are segmented as individual 
   cells. These objects and their corresponding membrane objects, as well as the virus objects they contain, are not counted.
