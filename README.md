# Spatially-Adjusted-Recurrent-U-Net

Background: The manual delineation of the gross tumor volume (GTV) for Head
and Neck Cancer (HNC) patients is an essential step in the radiotherapy treatment
process. Methods to automate this process have the potential to decrease the amount
of time it takes for a clinician to complete a plan, while also decreasing the inter-
observer variability between clinicians. Deep learning (DL) methods have shown great
promise in auto-segmentation problems. However, for HNC, we show that DL methods
systematically fail at the axial edges of GTV where the segmentation is dependent on
both information from the center of the tumor and nearby slices. These failures may
decrease trust and usage of proposed Auto-Contouring Systems if not accounted for

Purpose: In this paper we propose a model to increase edge accuracy of GTV con-
tours using DL. We compare performance to a 2D U-Net, which has no way to capture
inter-slice connectivity, and a 3D U-Net, the current standard to capture information
across axial slices.

Methods: To increase performance at the axial edges, we propose the Spatially Ad-
justed Recurrent Convolution U-Net (SARC U-Net), which can more accurately process
dependence between slices to create a more robust GTV contour. Our method uses
Convolutional Recurrent Neural Networks to push information from salient regions out
to the axial edges. To account for shifts in anatomical structures through adjacent CT
slices, we allow an affine transformation to the adjacent feature space using Spatial
Transformer Networks.

Results: Models were trained using multi-modal CT and PET scan inputs gathered
from a dataset of 70 HNC patients. After averaging performance across 7-fold cross
validation our proposed model increases accuracy at the edges by 12% inferiorly and
26% superiorly over a baseline 2D U-Net, which has no inherent way to capture in-
formation between adjacent slices. Over all slices our proposed architecture increases
Sørensen–Dice coefficient by 2.1% and 8.1% over a baseline 3D and 2D U-Net respec-
tively.

Conclusions: SARC U-Net was designed to target current weaknesses in HNC GTV
contours proposed by DL methods. Results show that SARC U-Net can increase ac-
curacy at the axial edges of GTV contours while also increasing accuracy over baseline
models, creating a more robust contour.
