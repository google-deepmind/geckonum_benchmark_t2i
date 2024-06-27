# GeckoNum Benchmark
<img src="https://storage.googleapis.com/geckonum_t2i_benchmark/example_images_wbg.png" width="800" />

GeckoNum is a benchmark for evaluation of numerical reasoning capabilities in text-to-image generative models.
This repository includes:

* Text prompts that probe different aspects of numerical reasoning.
* Human annotations of images generated using the text prompts.

Due to the large size, generated images are stored separately in a <a href="https://storage.googleapis.com/geckonum_t2i_benchmark/index.html" target="_blank">Google Cloud bucket</a>.

For the detailed description of the dataset, see the [DATASET.md](DATABASE.md). Experimental details on how the data was collected and processed are described in the [paper](https://arxiv.org/pdf/2406.14774v1). For a subset of selected examples of prompts, generated images and associated annotations see [examples](examples.md).


## Citing this work


```latex
@article{kajic2024evaluating,
      title={Evaluating Numerical Reasoning in Text-to-Image Models},
      author={Kaji{\'c}, Ivana and Wiles, Olivia and Albuquerque, Isabela and Bauer, Matthias and Wang, Su and Pont-Tuset, Jordi and Nematzadeh, Aida},
      eprint={2406.14774},
      archivePrefix={arXiv},
      year={2024},
}
```

## License and disclaimer

Copyright 2024 DeepMind Technologies Limited

All software is licensed under the Apache License, Version 2.0 (Apache 2.0);
you may not use this file except in compliance with the Apache 2.0 license.
You may obtain a copy of the Apache 2.0 license at:
https://www.apache.org/licenses/LICENSE-2.0

All other materials are licensed under the Creative Commons Attribution 4.0
International License (CC-BY). You may obtain a copy of the CC-BY license at:
https://creativecommons.org/licenses/by/4.0/legalcode

Unless required by applicable law or agreed to in writing, all software and
materials distributed here under the Apache 2.0 or CC-BY licenses are
distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied. See the licenses for the specific language governing
permissions and limitations under those licenses.

This is not an official Google product.
