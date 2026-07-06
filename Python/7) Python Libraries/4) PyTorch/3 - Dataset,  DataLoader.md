[[2 - torch layers]] $\leftarrow$ Back
[[4 - Example Training Loop]] $\leftarrow$ Next

---
# What are Datasets
Datasets, a class from `torch.utils.data`, are an abstract interface for storing, accessing, and transforming data.

Mathematically, a dataset $\mathcal{D}$ is defined as...
$$
\mathcal{D} = \bigg\{(x_1, y_1),...,(x_n, y_n)\bigg\}
$$

Where...
- $x_i$ is the $i^{th}$ input
- $y_i$ is the $i^{th}$ label or actual output which corresponds to $x_i$
- $n$ is the size of the data set: how many data points there are.

## User-defined Dataclass
you can define custom data sets by inheriting from the Dataset class.
- MUST override some methods.


```python
from torch.utils.data import Dataset

class CustomDataset(Dataset): 
	def __init__(self, ...):
		# define data contained within Dataset. Can be done via...
		#    - loading data from a given file path.
		#    - hard coding data within the data set.
		#    - etc.
		
	def __len__(self):
		# somehow calculate size of data set.
		return N
	
	def __getitem__(self, idx)
		# return a tuple of x_i, y_i
		return x_idx, y_idx
```


## Pre-existing Dataclass classes
torch provides multiple pre-defined dataclasses containing data.
- from `torchvision.datasets`

some examples are.
1) MNIST.
2) CIFAR-10
3) CIFAR-100
4) ImageNet
5) Fashion-MNIST

regardless of dataset being loaded...
- resulting type is a `torch.utils.data.Dataclass` object
- all objects are loaded the same way


```python
from torchvision import datasets
dataset = datasets.DATASET_NAME(
	root,
	train,
	download,
	transform
)
```

Where...
- `root` is a str parameter which provides the file path of a locally saved dataset.
- `train` is a boolean parameter which flags whether the loaded dataset is a training set or not.
- `download` is a boolean parameter which flags whether to download the dataset if it has not been found at the provided root filepath.
- `transform` is a function parameter which assigns a function used to transform loaded data.

# What are DataLoaders?
DataLoader is a class which wraps a Dataset, given upon initialisation, that acts as an iterable object that segments the Dataset's elements into batches with...
- Automatic batching and collation.
- Shuffling and sample strategies.
- Multi-process parallel data loading.
- Memory management optimisation.

DataLoader constructor is defined as:
```python
DataLoader(
	dataset,
	batch_size    = 1,
	shuffle       = False,
	sampler       = None,
	batch_sampler = None,
	num_workers   = None,
	collate_fn    = None,
	pin_memory    = None,
	drop_last     = False
	# some others exist.
)
```

Where...
- `batch` is a Dataclass type object containing the data to be loaded.
- `batch_size` controls the number of batches to iterate over per epoch.
- `shuffle` is a boolean flag which controls whether the dataset is shuffled each time a batch created.
