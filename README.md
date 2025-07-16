# NeuralForge: Sculpting Generative Architectures Through Reinforcement Learning

NeuralForge is a cutting-edge research project exploring differentiable Neural Architecture Search (NAS) kernels for Generative Adversarial Network (GAN) hyperparameter optimization, driven by reinforcement learning. This repository provides the codebase and experimental framework for researchers and developers interested in automating the design and optimization of GAN architectures, ultimately leading to the generation of higher-quality and more diverse synthetic data.

The project addresses the significant challenge of manually tuning GAN architectures, a time-consuming and often inefficient process. Instead of relying on human intuition and trial-and-error, NeuralForge dynamically evolves GAN architectures through a differentiable search space. This allows us to leverage gradient-based optimization techniques to efficiently identify promising architectures. The reinforcement learning component guides the search process, rewarding architectures that demonstrate superior performance based on predefined metrics such as Inception Score (IS) and Frechet Inception Distance (FID). This closed-loop feedback mechanism enables NeuralForge to progressively refine the generated architectures, leading to state-of-the-art results in GAN training.

NeuralForge provides a flexible and extensible platform for exploring various NAS kernels and reinforcement learning algorithms. Researchers can easily experiment with different search spaces, reward functions, and optimization strategies. The modular design allows for the integration of custom GAN architectures and datasets. Furthermore, the project includes comprehensive logging and visualization tools for monitoring the training process and analyzing the performance of different architectures. By automating the architecture search process, NeuralForge aims to democratize GAN research and make it accessible to a wider audience.

## Key Features

*   **Differentiable NAS Kernel:** Employs a continuous relaxation of the architecture search space, enabling gradient-based optimization of GAN architectures. Specifically, the kernel utilizes a directed acyclic graph representation where each node represents an operation (e.g., convolution, batch normalization) and edges are weighted by learnable parameters.
*   **Reinforcement Learning Agent:** Implements a policy gradient-based reinforcement learning agent (e.g., PPO or REINFORCE) that learns to select optimal architectural parameters for the differentiable NAS kernel. The agent receives rewards based on the performance of the generated GAN architectures.
*   **Flexible GAN Architecture Support:** Designed to be compatible with a wide range of GAN architectures, including but not limited to DCGAN, StyleGAN, and ProGAN. The modular design allows for easy integration of custom GAN architectures.
*   **Customizable Reward Functions:** Provides the flexibility to define custom reward functions based on various performance metrics, such as Inception Score (IS), Frechet Inception Distance (FID), and Kernel Inception Distance (KID).
*   **Distributed Training Support:** Supports distributed training across multiple GPUs and machines using PyTorch's DistributedDataParallel, enabling efficient exploration of the architecture search space.
*   **Comprehensive Logging and Visualization:** Includes detailed logging of training progress, architecture parameters, and performance metrics. Visualization tools are provided to analyze the performance of different architectures and identify promising design patterns.
*   **Configurable Search Space:** Allows users to define custom search spaces by specifying the set of allowed operations, the number of nodes and edges in the architecture graph, and other architectural parameters.

## Technology Stack

*   **TypeScript:** The primary programming language, providing type safety, maintainability, and scalability.
*   **Node.js:** Used for running the reinforcement learning agent and managing the training process.
*   **PyTorch:** The deep learning framework used for implementing the GAN architectures and the differentiable NAS kernel. PyTorch's dynamic computational graph enables flexible and efficient experimentation.
*   **TensorBoard:** Used for visualizing training progress, architecture parameters, and performance metrics.
*   **NumPy:** Used for numerical computation and data manipulation.
*   **CUDA:** Used for GPU acceleration of the deep learning models.

## Installation

1.  Clone the repository:

    git clone https://github.com/jjfhwang/NeuralForge.git
    cd NeuralForge

2.  Install Node.js dependencies:

    npm install

3.  Install Python dependencies (using pip):

    pip install -r requirements.txt

4.  Ensure you have CUDA installed and configured correctly for PyTorch. Verify by running a simple PyTorch CUDA test script.

5.  Install TypeScript globally (if not already installed):

    npm install -g typescript

6.  Compile the TypeScript code:

    npm run build

## Configuration

NeuralForge relies on environment variables for configuration. The following environment variables must be set before running the training process:

*   `DATASET_PATH`: The path to the training dataset.
*   `OUTPUT_DIR`: The directory where the training logs and checkpoints will be saved.
*   `CUDA_VISIBLE_DEVICES`: Specifies which GPUs to use for training (e.g., "0,1" for GPUs 0 and 1).

The following settings can be configured in the `config.ts` file:

*   `nasKernel`: Configuration options for the differentiable NAS kernel, such as the number of nodes and edges in the architecture graph.
*   `rlAgent`: Configuration options for the reinforcement learning agent, such as the learning rate and the discount factor.
*   `ganArchitecture`: Configuration options for the GAN architecture, such as the number of layers and the activation functions.
*   `rewardFunction`: Configuration options for the reward function, such as the weights for different performance metrics.

## Usage

1.  Prepare the training dataset and set the `DATASET_PATH` environment variable accordingly. The dataset should be organized in a format compatible with PyTorch's `ImageFolder` dataset.

2.  Configure the training settings in the `config.ts` file.

3.  Start the training process:

    npm start

The training progress can be monitored using TensorBoard. Run `tensorboard --logdir runs` in your terminal and navigate to http://localhost:6006 in your browser.

Example configuration (config.ts):

  const config = {
    nasKernel: {
      numNodes: 4,
      numEdges: 8,
    },
    rlAgent: {
      learningRate: 0.0001,
      discountFactor: 0.99,
    },
    ganArchitecture: {
      type: "DCGAN",
      latentDim: 100,
    },
    rewardFunction: {
      inceptionScoreWeight: 1.0,
      frechetInceptionDistanceWeight: -1.0,
    },
  };

## Contributing

We welcome contributions to NeuralForge! Please follow these guidelines when contributing:

*   Fork the repository and create a branch for your feature or bug fix.
*   Write clear and concise commit messages.
*   Submit a pull request with a detailed description of your changes.
*   Ensure that your code adheres to the project's coding style.
*   Include unit tests for any new functionality.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/NeuralForge/blob/main/LICENSE) file for details.

## Acknowledgements

This project was inspired by and builds upon the work of numerous researchers in the fields of Neural Architecture Search and Generative Adversarial Networks. We would like to thank the open-source community for providing valuable tools and resources that enabled this research.