## Annotation files data format

# Annotation Task 1
In Task 1, the annotators were instructed to count the number of objects in an image.
An image was paired with a question: ``How many <noun> are in the image?``, where `<noun>` is the entity extracted from the original text prompt used to generate the image.
The answer was given as a free-form text.

In most cases, the answer was a single number (e.g., "0", "2", "1.5", "10+").
However, when objects were not clearly identifiable or were ambiguous, the count of objects can be provided as a range (e.g., "2-3").
In cases where the same type of object can be seen in the foreground and the background, the two separate counts can be comma-separated (e.g., "2, 10+").


The CSV columns are:
* `image_id`: The `image_id` to match the image filename in the GC bucket.
* `model`: The model used to generate the image.
* `question_id`: The Question ID (images generated from `additive`-prompts have several questions).
* `question`: The question shown to the annotator.
* `prompt`: The text prompt used to generate the image.
* `annot_id`: The annotator ID.
* `raw_answer`: Original answer as typed in by the annotator (may contain typos).
* `answer`: Processed original answer (removed typos, standardized number format)


# Annotation Task 2
In Task 2, annotators were instructed to choose the text description that best describes an image.
For images generated from *approx-1-entity* prompts there were three text descriptions, and for images generated from *approx-2-entity* prompts, there were five text descriptions.


The CSV columns are:
* `image_id`: The `image_id` to match the image filename in the GC bucket.
* `model`: The model used to generate the image.
* `prompt`: The text prompt used to generate the image.
* `gt_num`: The ground truth answer encoded as a number (see the encoding scheme below).
* `annot_id`: The annotator ID.
* `answer_text`: Original answer (the text description selected by the annotator).
* `answer_num`: The `answer_text` encoded as a number (see encoding scheme below).

The encoding scheme for `answer_num` to `answer_text` conversion:
* `0`: An image with **no** X and **no** Y. //  There are **no** X.
* `1`: An image with **some** X or **some** Y, but **not with both** X and Y.
* `2`: There are **fewer** X than Y.  // There are only a **few** X.
* `3`: There are **as many** X **as** Y.
* `4`: There are **more** X than Y. // There are **many** X.


# Annotation Task 3
In Task 3, annotators answered a series of yes/no questions about the image.
The questions are automatically generated using the approach described in [1].

The CSV columns are:
* `image_id`: The `image_id` to match the image filename in the GC bucket.
* `model`: The model used to generate the image.
* `question_id`: The question ID.
* `question`: The question shown to the annotator.
* `prompt`: The text prompt used to generate the image.
* `annot_id`: The annotator ID.
* `answer`: 1 for the `yes` answer, 0 for the `no` answer.




**References**:

[1] Cho, Jaemin, Yushi Hu, Jason Michael Baldridge, Roopal Garg, Peter Anderson, Ranjay Krishna, Mohit Bansal, Jordi Pont-Tuset, and Su Wang. "Davidsonian Scene Graph: Improving Reliability in Fine-grained Evaluation for Text-Image Generation." ICLR. 2023.

