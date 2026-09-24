# Criteria-Grounded Surgical Skill Assessment

Code and qualitative examples for our ICASSP 2027 submission:

**Criteria-Grounded Surgical Skill Assessment: A Multimodal Reasoning Framework**

We assess surgical skill as a mapping from **video + scoring criteria** to a **score**.  
*Exemplar learning* describes key frames; *criteria grounding* compares those descriptions with the criteria to predict a score.

This repository currently hosts **visualizations**. Code will be added here.

---

## Qualitative Example 1 (correct prediction)

**Phase:** scleral flap making in trabeculectomy (score range 1–5)

### 1. Example image (key frames)

<p align="center">
  <img src="visualizations/example_01/frames.png" width="85%"/>
</p>

<p align="center"><em>Key frames extracted near the end of the scleral-flap phase.</em></p>

### 2. Ground-truth score

**GT score: 4**

### 3. Prediction (ours)

**Predicted score: 4**

**Reason:** The scleral flap is moderate in size, but thickness is not fully uniform. Shape and completeness are worse than Example 1, fall between Examples 2 and 3, and are less uneven than Example 3. Thickness also does not show the extreme local thinning of Example 4. This matches the scoring gist for score 4 (*moderate in size, but slightly uneven in thickness*).

### 4. Direct description

> This is an image of the scleral flap stage during trabeculectomy. The forceps is located in the upper left part of the image and appears to be a micro-toothless forceps, as the bite surface of the forceps appears to be smooth and has no obvious gear-like protrusions. The tissue that the forceps are holding is the scleral flap, which is moderate in size, but it can be seen from the image that the thickness is not completely uniform, with local irregular thickness.

---

## Qualitative Example 2 (correct prediction)

**Phase:** scleral flap making in trabeculectomy (score range 1–5)

### 1. Example image (key frames)

<p align="center">
  <img src="visualizations/example_02/frames.png" width="85%"/>
</p>

### 2. Ground-truth score

**GT score: 1**

### 3. Prediction (ours)

**Predicted score: 1**

**Reason:** The flap is visually moderate in size: larger than the too-small flap in Example 3, but not as small and uniform as Example 1. Thickness looks relatively uniform (unlike Example 4) yet does not reach the ideal thickness of Examples 1 and 2. Together these cues support a low score.

### 4. Direct description

> This is an image of the scleral flap stage during trabeculectomy. In the image, we can see that the forceps are located in the upper left part of the image and are micro-toothed forceps. The tissue that the forceps are holding is the scleral flap, and the scleral flap in this image is visually moderate in size.

---

## Qualitative Example 3 (failure case)

**Phase:** scleral flap making in trabeculectomy (score range 1–5)

### 1. Example image (key frames)

<p align="center">
  <img src="visualizations/example_03/frames.png" width="85%"/>
</p>

### 2. Ground-truth score

**GT score: 3**

### 3. Prediction (ours)

**Predicted score: 4**

**Reason:** Due to limited resolution and viewing angle, the model treats the flap as relatively large and infers fairly uniform treatment, which over-shoots the expert score. An experienced surgeon can still score this case correctly from the same frames.

### 4. Direct description

> This is an image showing the scleral flap stage of trabeculectomy. The forceps are located in the middle and upper part of the image, and they look like toothless microscopic forceps. Due to the limitations of image resolution and angle, the description of the exact type of forceps is somewhat speculative. The size of the scleral flap appears to be relatively large, and the uniformity of its thickness is not easy to determine from the image.

---

## Dataset note

Examples come from porcine trabeculectomy practice videos. Do not upload patient identifiers, faces, or hospital marks.

## Citation

If you use this repository, please cite the ICASSP 2027 paper (link will be added after submission).
