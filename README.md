# Single-Cell and Spatial Data Visualization with Vitessce


Welcome! Here you will find the source material for the Vitessce tutorial.

An overview of the content can be found at [notebooks/Index.ipynb](notebooks/Index.ipynb)


## Run the Tutorial

If you have a Google/Gmail account, you can Run this tutorial from your browser using Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vitessce/vitessce-python-tutorial-2026/blob/main/notebooks/Index.ipynb).

### Molab

If colab is not working, you can try Molab instead:
- [01-Single-Spatial-View.ipynb](https://molab.marimo.io/github/vitessce/vitessce-python-tutorial-2026/blob/main/notebooks/01-Single-Spatial-View.ipynb)
- [02-Multiple-Views.ipynb](https://molab.marimo.io/github/vitessce/vitessce-python-tutorial-2026/blob/main/notebooks/02-Multiple-Views.ipynb)
- [03-Available-View-Types.ipynb](https://molab.marimo.io/github/vitessce/vitessce-python-tutorial-2026/blob/main/notebooks/03-Available-View-Types.ipynb)
- [04-Coordinated-Multiple-Views.ipynb](https://molab.marimo.io/github/vitessce/vitessce-python-tutorial-2026/blob/main/notebooks/04-Coordinated-Multiple-Views.ipynb)

## Additional materials

Prior tutorial materials can be found in https://github.com/vitessce/vitessce-python-tutorial-2023.


## Acknowledgements

The format and structure of these tutorial materials are inspired heavily by the [Gosling Tutorial](https://github.com/gosling-lang/gosling-tutorial) created by Sehi L'Yi, Trevor Manz, Qianwen Wang, and Nils Gehlenborg.

## Local usage

To use these notebooks locally, clone the repository:

```sh
git clone https://github.com/vitessce/vitessce-python-tutorial-2026.git
cd vitessce-python-tutorial-2026
```

We recommend using [uv](https://docs.astral.sh/uv/#installation).

Create the virtual environment:

```sh
uv venv --python 3.12
```

Activate the virtual environment:

```sh
source .venv/bin/activate
```

Install:

```sh
uv add --requirements requirements.txt
```

Run the notebooks

```sh
uv run jupyter lab
```

When running the notebooks locally, ignore (i.e., do not run) the `!pip install` lines in the notebooks. Your virtual environment already contains these packages since they are listed in `requirements.txt`.

## Troubleshooting

If you see an anndata error that mentions `allow_write_nullable_strings`, run the following code:

```py
import anndata
anndata.settings.allow_write_nullable_strings = True
```

If you see errors related to missing data, try renaming the output file path and re-running the data writing code:

```diff
- zarr_path = join("data", "pbmc68k.adata.zarr")
+ zarr_path = join("data", "pbmc68k_v2.adata.zarr")
```