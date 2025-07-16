# NeuralForge - Your Customizable Neural Network Construction Kit

NeuralForge is a TypeScript-based library designed to provide developers with a modular and highly customizable toolkit for building and experimenting with neural networks. Unlike monolithic frameworks that enforce specific architectures and training procedures, NeuralForge empowers users to define their own network structures, activation functions, and training algorithms from the ground up. This flexibility is particularly beneficial for researchers exploring novel network topologies, students learning the fundamentals of deep learning, and developers requiring fine-grained control over their model's behavior. The project aims to abstract away the complexities of low-level tensor manipulation while still exposing the core building blocks necessary for advanced experimentation.

The core philosophy behind NeuralForge is composability. It provides a collection of pre-built, well-documented modules that can be assembled and customized to create a wide variety of neural network architectures. These modules include various layer types (dense, convolutional, recurrent), activation functions (ReLU, sigmoid, tanh), optimizers (SGD, Adam, RMSprop), and loss functions (cross-entropy, mean squared error). Developers can easily extend these modules or create their own custom components to tailor the library to their specific needs. Furthermore, the library prioritizes type safety and code clarity to ensure maintainability and ease of understanding, particularly for complex and custom-built neural networks.

NeuralForge is not intended to be a black-box solution for deep learning tasks. Instead, it is designed to be a transparent and educational tool that allows users to delve into the inner workings of neural networks. By providing a clear separation of concerns and a well-defined API, NeuralForge simplifies the process of building and debugging complex models. The project includes extensive documentation and examples to guide users through the process of creating, training, and evaluating their own neural networks. It encourages experimentation and exploration of different architectural choices, ultimately fostering a deeper understanding of the underlying principles of deep learning.

## Key Features

*   **Modular Architecture:** NeuralForge is built on a modular design, allowing developers to easily assemble and customize their neural networks using pre-built components. Each module is designed with a specific purpose in mind and can be easily extended or replaced with custom implementations.
*   **Type Safety:** Leveraging the power of TypeScript, NeuralForge ensures type safety throughout the codebase, reducing the risk of runtime errors and improving code maintainability. The type system helps developers catch potential issues early in the development process and provides better code completion and refactoring support.
*   **Customizable Layers:** The library provides a variety of pre-built layer types, including dense, convolutional, and recurrent layers. Developers can also create their own custom layers by implementing the `Layer` interface, which defines the core functionality required for a layer to interact with the rest of the network.
*   **Flexible Activation Functions:** NeuralForge includes a selection of common activation functions, such as ReLU, sigmoid, and tanh. Users can also easily define their own custom activation functions by implementing the `ActivationFunction` interface, enabling experimentation with novel non-linearities.
*   **Extensible Optimizers:** The library supports a range of optimization algorithms, including SGD, Adam, and RMSprop. Developers can add their own custom optimizers by implementing the `Optimizer` interface, providing the ability to fine-tune the training process.
*   **Comprehensive Loss Functions:** NeuralForge provides common loss functions like cross-entropy and mean squared error. The `LossFunction` interface makes it simple to define custom loss functions tailored to specific problem domains.
*   **Tensor Abstraction:** The library abstracts away low-level tensor manipulation details, allowing developers to focus on the high-level architecture and training process. This reduces the complexity of building and debugging neural networks and makes the library more accessible to developers with varying levels of experience.

## Technology Stack

*   **TypeScript:** The core language used for building NeuralForge, providing type safety, code clarity, and improved developer productivity. TypeScript's static typing helps prevent runtime errors and makes the codebase easier to maintain and refactor.
*   **Node.js:** A JavaScript runtime environment that enables the execution of NeuralForge code outside of a web browser. Node.js is used for building the development environment, running tests, and packaging the library for distribution.
*   **npm (Node Package Manager):** The package manager used for managing dependencies and publishing the NeuralForge library to the npm registry.
*   **Jest:** A testing framework used for writing and running unit tests to ensure the quality and correctness of the NeuralForge codebase. Jest provides a simple and intuitive API for writing tests and supports features such as mocking, code coverage, and snapshot testing.

## Installation

1.  **Prerequisites:** Ensure that you have Node.js and npm installed on your system. You can download and install them from the official Node.js website: https://nodejs.org.
2.  **Clone the repository:**
    git clone https://github.com/jjfhwang/NeuralForge.git
3.  **Navigate to the project directory:**
    cd NeuralForge
4.  **Install dependencies:**
    npm install

## Configuration

NeuralForge does not rely on external configuration files or environment variables for its core functionality. However, if you are extending the library with custom layers, activation functions, or optimizers, you may need to configure them based on your specific requirements. For example, you might want to expose hyperparameters as configurable parameters that can be adjusted through a configuration object passed to the constructor of your custom component.

## Usage

Here's a basic example of how to create a simple neural network using NeuralForge:

// Import necessary modules
import { DenseLayer, ReLUActivation, SequentialModel, AdamOptimizer, MeanSquaredErrorLoss } from './src'; // Adjust path as needed

// Define the model architecture
const model = new SequentialModel([
    new DenseLayer(10, 5, new ReLUActivation()), // 10 input features, 5 neurons in the hidden layer
    new DenseLayer(5, 1) // Output layer with 1 neuron
]);

// Define the optimizer and loss function
const optimizer = new AdamOptimizer(0.01); // Learning rate of 0.01
const lossFunction = new MeanSquaredErrorLoss();

// Generate some sample data
const inputData = [[0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0]];
const targetData = [[0.5]];

// Train the model
for (let i = 0; i < 100; i++) {
    const loss = model.train(inputData, targetData, optimizer, lossFunction);
    console.log(`Epoch ${i + 1}, Loss: ${loss}`);
}

// Make a prediction
const prediction = model.predict(inputData);
console.log(`Prediction: ${prediction}`);

//Refer to the /src directory for the API documentation of each class and interface. Detailed type documentation is present within the source code.

## Contributing

We welcome contributions to NeuralForge! Please follow these guidelines when contributing:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with thorough comments.
4.  Write unit tests to ensure the correctness of your changes.
5.  Submit a pull request with a detailed description of your changes.
6.  Follow the existing code style and conventions.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/NeuralForge/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for their contributions to the field of deep learning and for providing the tools and resources that made this project possible.