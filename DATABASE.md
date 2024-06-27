## Text Prompts

The `prompts.csv` file contains the following fields:

* `prompt`: Text prompt used in image generation
* `has_numeral`: 1 if `prompt` contains word numeral ("one", "two", "three") or 0 if digit (1, 2, 3...)
* `is_frequent`: 1 if the noun in the text is frequent (0 if non-frequent), and -1 if not applicable
* `entitites`: a list of `noun:number` tuples in the prompt
* `prompt_type`: one of 12 `prompt_types` (see `Table 1` in the paper for a detailed description and examples)
* `dataset_id`: ID used to match prompts to `image_ids` in the Google Cloud bucket

Notes:

* `is_frequent` is only set for `numeric_simple` prompt type, for others it is set to -1
* `has_numeral` is 1 if any of the numbers in the prompt is represented using words  (in prompts with more than one number such as `2-additive` or `3-additive`)


## Annotations
Human annotations are stored as CSV files in the `./annotations/` directory. The names of the files are of the format: `{task}_{model}.csv`, where the task is one of `task_1`, `task_2`, `task_3` and `{model}` is one of the models.

For more information about the content of annotation CSVs, refer to the corresponding `README` in that directory. All annotations can be also downloaded as a single [zip file](./annotations/geckonum_annotations.zip) (<3 MB).

## Images
Generated images are stored separately in a <a href="https://storage.googleapis.com/geckonum_t2i_benchmark/index.html" target="_blank">Google Cloud bucket</a>, with a separate directory for each of the models: `dalle_3, imagen_a, imagen_b, imagen_c, imagen_d, muse_a, muse_b`.
A subset of images can be previewed in the in the browser, and all images can be downloaded as a [zip file](https://storage.googleapis.com/geckonum_t2i_benchmark/geckonum.zip) (18.8 GB).

Image filenames are of the following format: `geckonum_{prompt_id}_{seed_id}`.

* `prompt_id`: indicates the prompt used to generate the image and it maps to the ID in the `prompts.csv`
* `seed_id`: is one of the five different seeds `0,1,2,3,4`
