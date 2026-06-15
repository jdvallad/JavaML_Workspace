# JavaML Workspace

This is the master meta-repository for the JavaML ecosystem. It ties together a custom, pure-Java machine learning engine (`JavaML_Core`) with various domain-specific implementations.

Because this workspace relies on **Git Submodules** to keep the core engine and the specific datasets cleanly decoupled, you must clone it using the recursive flag to pull down all the code.

## Cloning this Workspace

To clone this repository and automatically fetch all the attached submodules, run:

```bash
git clone --recurse-submodules https://github.com/yourusername/javaml-workspace.git
```

*(If you already cloned it without the flag, you can fetch the missing submodules by running `git submodule update --init --recursive` inside the workspace directory).*

## Repository Structure

```text
/JavaML_Workspace/
├── JavaML_Core/       <-- The mathematical engine (Matrix math, backprop, out-of-core streaming)
├── JavaML_Mnist/      <-- Image classification implementation (Digits 0-9)
└── JavaML_Claims/     <-- Actuarial severity prediction (Allstate Kaggle Dataset)
```

## Compiling the Ecosystem

To compile the core engine alongside all of the implementations at once, open your terminal, navigate to the root of this workspace, and run:

```bash
javac JavaML_Core/*.java JavaML_Mnist/*.java JavaML_Claims/*.java
```

## Running the Implementations

After compiling, you can run the individual drivers. 

**To run the MNIST Image Classifier:**
Ensure you have downloaded the dataset (see the `JavaML_Mnist` README for the download command), then run:
```bash
java JavaML_Mnist.MnistDriver
```

**To run the Allstate Claims Predictor:**
Ensure you have downloaded the Kaggle dataset (see the `JavaML_Claims` README for instructions), then run:
```bash
java JavaML_Claims.ClaimsDriver
```