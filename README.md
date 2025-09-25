# Datathon-WP7

A collection of beginner-friendly Jupyter notebooks that introduce Variational Autoencoders (VAEs) for tabular data. The tutorials walk through loading real-world tabular datasets, training a compact PyTorch VAE, visualising the learned latent space, and sampling synthetic records.

## Repository contents

| File | Description |
| --- | --- |
| `DataVisualization.ipynb` | Companion notebook that focuses on exploratory plots for the Iris dataset and mirrors the VAE workflow for presentation-ready visuals. |
| `TabularVAE_Tutorial_ copy.ipynb` | Main step-by-step tutorial that builds, trains, and samples from a simple VAE using the Iris dataset. |
| `Real_toy_data.ipynb` | Minimal scratchpad for loading an external CSV file (update the `data_dir` variable to point to your file). |
| `environment.yml` | Conda environment specification with PyTorch, scikit-learn, pandas, seaborn, and supporting scientific Python packages. |

## Getting started

1. **Install Conda (recommended).** Either Anaconda or Miniconda works.
2. **Create the project environment.**

   ```bash
   conda env create -f environment.yml
   conda activate deeplearning
   ```

3. **Launch Jupyter.**

   ```bash
   jupyter notebook
   ```

   Open any of the notebooks from the Jupyter interface to run the cells interactively.

> **Tip:** The notebooks include `%pip install ...` commands as a fallback for environments that do not use Conda. You can skip those cells if you already created the `deeplearning` environment.

## Start with data exploration

Begin with `DataVisualization.ipynb` to familiarise yourself with the Iris dataset and the types of plots you can generate from the notebook workflow. It covers:

- Key facts about the Iris dataset.
- Step-by-step loading of the data into pandas.
- Visual aids for understanding the latent space learned by the VAE.

This notebook is ideal for experimentation and presentation-ready visuals before you dive into model training.

## Train the VAE

Once you are comfortable with the dataset, move on to `TabularVAE_Tutorial_ copy.ipynb`, the primary learning resource for building the model. It is organised into five sections:

1. **Setup** – Installs/loads PyTorch, pandas, scikit-learn, seaborn, and Matplotlib.
2. **Load a sample dataset** – Uses the classic Iris dataset, shuffles it, and displays summary statistics.
3. **Build a simple VAE** – Defines a lightweight encoder/decoder architecture in PyTorch with a 2D latent space.
4. **Train the model** – Wraps the Iris features in a `TensorDataset`, iterates for 50 epochs, and prints reconstruction+KL loss values.
5. **Generate synthetic rows** – Visualises the latent embedding and decodes random latent samples into synthetic measurements.

Feel free to adapt the network size, learning rate, or number of epochs to explore different behaviours of the VAE.

## Working with your own data

To experiment with alternative datasets:

1. Duplicate the main tutorial notebook.
2. Replace the Iris-loading cells with code that reads your dataset into a pandas `DataFrame` (see the helper snippet in `Real_toy_data.ipynb`).
3. Ensure all features are numeric before converting to a PyTorch tensor. Apply preprocessing (normalisation, one-hot encoding, etc.) as needed.
4. Update the `input_dim` argument when instantiating the `VAE` class to match the number of columns in your processed table.

## Troubleshooting

- **Missing data file:** `Real_toy_data.ipynb` references a local path (`/Users/sadegh.mohammadi/Desktop/real-toy-dataset.csv`). Update the `data_dir` variable to point to a CSV file available on your system.
- **CUDA/GPU usage:** The tutorials default to CPU training. If you have CUDA available, move the tensors and model to the GPU with `to('cuda')` for faster experimentation.
- **Package conflicts:** If you already have a base environment, consider creating an isolated Conda environment as shown above to avoid dependency clashes.

## License

No explicit license file is included. If you plan to use or redistribute the materials, confirm the licensing requirements with the project owner or add a license of your choice.

## Contributing

Issues and pull requests are welcome. When contributing, please:

1. Fork the repository.
2. Create a feature branch for your changes.
3. Open a pull request describing the updates and any testing performed.

Enjoy exploring VAEs for tabular data!
