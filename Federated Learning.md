# Federated Learning

## What is Federated Learning?

Federated Learning (FL) is a distributed machine learning approach where models are trained across multiple decentralized devices or servers, each holding local data samples, without the need to share that data. Instead of sending raw data to a central server, each device trains a model locally, and only model updates (like gradients or weights) are shared. This allows for collaborative model training while keeping the data secure and private.

![72083f76-475f-4a38-b6b8-c29d664354e5_1108x598](https://github.com/user-attachments/assets/52d1ed7c-81f4-46ff-bfc2-d1fdc4e2a30a)


*Figure 1: Federated Learning Process Overview*

## How Federated Learning Works

Federated Learning follows a specific workflow:

1. **Initialization**: A global model is initialized on a central server and shared with edge devices (like mobile phones or IoT devices).
2. **Local Training**: Each edge device trains the global model using its local data for several iterations.
3. **Model Update**: Instead of sending the raw data back to the central server, each device sends the trained model updates (weights or gradients) back.
4. **Aggregation**: The central server collects the updates from various devices and aggregates them (typically through techniques like Federated Averaging).
5. **Global Update**: The aggregated model is updated and sent back to the edge devices, and the process is repeated until convergence.

## Types of federated learning

Let’s explore the commonly used strategies and algorithms used for federated learning.

### Federated learning strategies

### Centralized federated learning

Centralized federated learning requires a central server. It coordinates the selection of client devices in the beginning and gathers the model updates during training. The communication happens only between the central server and individual edge devices.

While this approach looks straightforward and generates accurate models, the central server poses a bottleneck problem—network failures can halt the complete 
process.
![63dd0bbd5a5e3b2accccdc3f_federated learning 1](https://github.com/user-attachments/assets/ddad5aa1-1b8b-4696-b276-0e2fd51c9e90)


### Decentralized federated learning

Decentralized
federated learning does not require a central server to coordinate the learning. Instead, the model updates are shared only among the interconnected edge devices. The final model is obtained on an edge device by aggregating the local updates of the connected edge devices.

This approach prevents the possibility of a single-point failure; however, the model's accuracy is completely dependent on the network topology of the edge devices.
![63dd0be289a72c7e01b470ef_local model](https://github.com/user-attachments/assets/c37a959b-c31d-4dab-bc97-c6807890a18f)

### Heterogeneous federated learning

Heterogeneous
 federated learning involves having heterogeneous clients such as mobile phones, computers, or IoT (Internet of Things) devices. These devices may differ in terms of hardware, software, computation capabilities, and data types.

HeteroFL was developed in response to the common Federated Learning strategies that assume the local models’ attributes resemble those of the main model. But in the real world, it happens very
 rarely. HeteroFL can generate a single global model for inference after training over multiple varied local models.

### Technical Workflow Example:

- **Step 1:** Server initializes model (M₀) and sends it to devices (D₁, D₂, ... Dn).
- **Step 2:** Each device trains model M locally with its data and generates updates (U₁, U₂, ... Un).
- **Step 3:** Updates are sent to the central server.
- **Step 4:** Server aggregates the updates and forms an improved global model (M₁).
- **Step 5:** Global model M₁ is sent back to devices for further refinement.

## Applications of Federated Learning

Federated Learning is being adopted in a variety of sectors where privacy and data governance are crucial. Some notable applications include:

- **Healthcare**: Federated Learning enables hospitals to collaborate on training models for medical imaging or diagnosis without sharing sensitive patient data.


*Figure 3: Federated Learning in Healthcare*

- **Finance**: Banks can improve fraud detection or risk assessment by training models on decentralized data from different branches or users while ensuring customer privacy.
- **Mobile Devices**: Google uses Federated Learning for Gboard to improve predictive text suggestions without accessing individual users' typing data.
- **Smart Cities and IoT**: Devices in smart cities, like traffic cameras, can train shared models to improve traffic flow predictions while keeping locally collected data secure.
- **Retail**: E-commerce platforms can optimize personalized shopping recommendations using customer data stored on decentralized devices without compromising user privacy.

## Advantages of Federated Learning

1. **Data Privacy**: The data never leaves local devices, maintaining user privacy and adhering to data protection regulations (like GDPR).
2. **Lower Communication Costs**: Only model updates are shared, reducing the need for large amounts of data transfer between edge devices and servers.
3. **Collaboration Without Sharing Raw Data**: Federated Learning allows institutions to collaboratively train models without directly sharing sensitive or proprietary data.
4. **Scalability**: Since computation happens on edge devices, federated learning can scale to a massive number of devices, each contributing to the model training process.
5. **Reduced Latency**: Training locally reduces the dependency on real-time internet connection, making it useful for offline applications.

## Disadvantages of Federated Learning

1. **Non-IID Data**: Data stored on devices can be non-independent and identically distributed (non-IID), which makes training more complex and affects model convergence.
2. **Device Variability**: Devices participating in federated learning have varying computational power and network availability, which can cause performance bottlenecks.
3. **Privacy Leaks via Model Updates**: Though the raw data is never shared, there are potential risks of inferring private data from the model updates, requiring advanced privacy techniques like Differential Privacy.
4. **Communication Overhead**: While model updates are smaller than raw data, transmitting updates from thousands or millions of devices can still incur a high communication cost.
5. **Model Synchronization**: Ensuring all devices work on the same version of the model can be challenging, especially when devices join or drop out at different times.

## Current Best Open-Source Federated Learning Models

Several open-source frameworks and models are available for those looking to explore or implement Federated Learning. Some of the leading frameworks include:

1. **TensorFlow Federated (TFF)**:
    - Developed by Google, TFF is an open-source framework for machine learning and other computations on decentralized data.
    - It supports both research and production settings.
    
    **Link**: [TensorFlow Federated](https://www.tensorflow.org/federated)
    
2. **PySyft**:
    - A library for encrypted, privacy-preserving machine learning developed by OpenMined. PySyft extends PyTorch with Federated Learning, Differential Privacy, and Multi-Party Computation.
    
    **Link**: [PySyft GitHub](https://github.com/OpenMined/PySyft)
    
3. **FATE (Federated AI Technology Enabler)**:
    - Developed by WeBank, FATE provides a secure computing framework to support federated AI ecosystem development.
    - It supports secure multi-party computation and cryptography-based federated learning techniques.
    
    **Link**: [FATE GitHub](https://github.com/FederatedAI/FATE)
    
4. **Flower (FLower)**:
    - A simple and scalable open-source framework for federated learning research and production. Flower can be used with TensorFlow, PyTorch, or any other ML framework.
    
    **Link**: [Flower GitHub](https://github.com/adap/flower)
    

## Notable Research Papers on Federated Learning

Here are some important research papers for deeper understanding:

1. **"Communication-Efficient Learning of Deep Networks from Decentralized Data"** by H. Brendan McMahan et al.
    - A foundational paper that introduces Federated Averaging (FedAvg), a core algorithm in FL.
    - [Link to paper](https://arxiv.org/abs/1602.05629)
2. **"Towards Federated Learning at Scale: System Design"** by Bonawitz et al.
    - Explores system design challenges and practical implementations of federated learning.
    - [Link to paper](https://arxiv.org/abs/1902.01046)
3. **"Federated Learning: Challenges, Methods, and Future Directions"** by Kairouz et al.
    - A comprehensive survey on challenges and potential improvements in federated learning.
    - [Link to paper](https://arxiv.org/abs/1912.04977)
    

## Conclusion

Federated Learning represents a transformative approach to machine learning, allowing for collaborative model training while addressing critical privacy, security, and data governance challenges. With applications spanning from healthcare to mobile devices, and open-source frameworks like TensorFlow Federated and PySyft making it accessible, Federated Learning is paving the way for the future of decentralized AI.
