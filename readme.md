## Video-based Social Interaction Behavior Analysis with the Simulated Interaction Task for Children (Kids-SIT)

All analysis steps are available in the `notebooks/` directory.  
Each notebook corresponds to one stage of the pipeline:

### 0. Feature Extraction
Extract features using:
- OpenFace  
- PyAFAR  
- REHG Eye Contact CNN  

All extracted features are merged into a unified dataset.

### 1. Preprocessing
- Retain only relevant video segments for analysis  
- Add metadata (e.g., speaker identity and segment information)

### 2. Annotation
- Integrate annotations from human annotators  
- Create a `behavior_agreed` column containing instances where all annotators agree

### 3. Behavior Extraction
Convert raw features into interpretable behavioral indicators, for example:
- **Gaze deviation** computed from `gaze_angle_x` and `gaze_angle_y`  
- **Nodding behavior** derived from head `pitch` and `yaw`

### 4. Threshold Selection
Fine-tune threshold values for:
- Smile detection  
- Gaze detection  

Thresholds are selected to maximize agreement with human annotations.

### 5. Subjective Impression
Compute results related to subjective impression measures.

### 6. Verbal Responses
Analyze and report results for verbal responses.

### 7. Non-Verbal Responses
Analyze and report results for non-verbal responses.

### 8. Classification
Evaluate the clinical applicability of Kid-SIT by classifying participants diagnosed with Social Anxiety Disorder (SAD) versus non-SAD participants.

---

## Setup

To run the code and notebooks from this repository:

```bash
conda env create -f environment.yml
conda activate kids-sit