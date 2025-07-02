#Introduction

This project presents a novel graph-based deep learning framework to classify pulmonary diseases from chest X-ray images. Traditional CNNs often fail to capture fine-grained spatial relationships in medical images. To overcome this, we propose transforming X-ray images into graph representations using super pixel segmentation and applying Graph Attention Networks (GAT) to extract meaningful features, improving diagnostic performance. The approach was implemented as part of a summer internship at Pondicherry University under the guidance of Dr. R. Sunitha.


Technologies Used
Python
PyTorch / TensorFlow (based on your implementation – update accordingly)
OpenCV & NumPy
scikit-image (for SLIC superpixel segmentation)
NetworkX / DGL / PyTorch Geometric (for graph creation and manipulation)
Matplotlib / Seaborn (for visualizations)


Dataset
MIMIC-CXR-JPG v2.0.0
Sourced from PhysioNet
Contains 377,000+ chest X-ray images
Annotations derived from 227,827 radiology reports
Fully de-identified and HIPAA-compliant
JPG format, labeled for multiple pulmonary conditions


Methodology / Project Workflow
1. Image Preprocessing
•	All chest X-ray images were resized to 256×256 pixels
•	Pixel values were normalized between -1 and 1
•	Augmentation techniques were applied to enhance variability

2. Superpixel Segmentation (SLIC)
•	Each image was segmented into superpixels using the SLIC algorithm
•	This reduced image complexity while preserving structural information

3. Graph Construction (RAG)
•	Region Adjacency Graph (RAG) was constructed from superpixels
•	Nodes represent superpixels, and edges represent spatial adjacency

4. Feature Extraction with GAT
•	Graph Attention Networks (GAT) were applied on RAGs
•	The attention mechanism focused on important regions for disease classification

5. Classification
•	Features were passed through fully connected layers
•	Sigmoid activation was used for multi-label disease prediction
•	Evaluated using precision, recall, F1-score, and confusion matrix


Conclusion
This study demonstrated the effectiveness of graph-based deep learning using GAT for pulmonary disease classification. By leveraging super pixels and attention mechanisms, the model captured complex relationships in chest X-rays more effectively than CNNs or standard GCNs. Future improvements include incorporating multimodal data and exploring dynamic graph structures for enhanced accuracy and real-world clinical application.

