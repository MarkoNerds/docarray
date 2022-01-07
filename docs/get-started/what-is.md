# What is DocArray?

- It is like `numpy.ndarray`, but for unstructured data. 
- It is like `pandas.DataFrame`, but for nested data. 
- It is like JSON, but for media data.
- It is like Protobuf, but for data scientists and deep learning engineers. 

If you are a **data scientist** who works with image, text, video, audio data in Python all day, you should use DocArray: it can greatly facilitate the work on representing, embedding, matching, visualizing, evaluating, sharing data; while stay close with your favorite toolkits, e.g. Torch, Tensorflow, ONNX, PaddlePaddle, JupyterLab, Google Colab.

If you are a **deep learning engineer** who works on scalable deep learning service, you should use DocArray: it can be the basic building block of your system. Its portable data structure can be wired in Protobuf, compressed bytes, JSON; allowing your engineer friends to happily integrate it into the production system.

This is DocArray: a very unique one, aiming to be *the data structure for unstructured data*.

## Design 

DocArray consists of two simple concepts:
- **Document**: a data structure for easily representing nested, unstructured data.
- **DocumentArray**: a container for efficiently accessing, processing, and understanding multiple Documents.

DocArray is designed to be extremely easy to use for Python users, if you know how to Python, you know how to DocArray.

DocArray is designed to maximize the local experience, with the requirement of cloud readiness at anytime.

# Comparing to Alternatives

|                                 | DocArray     | `numpy.ndarray` | JSON | `pandas.DataFrame` | Protobuf |
|---------------------------------|--------------|--- |------|--- | --- |
| Tensor/matrix data              | ✅|✅| ❌    |✅|☑️|
| Text data                       |✅|❌| ✅    |✅|✅|
| Media data                      |✅|❌| ❌    |❌|❌|
| Nested data                     |✅|❌| ✅    |❌|✅|
| Mixed data of the above four    |✅|❌| ❌    |❌|❌|
| Easy to (de)serialize           |✅|❌| ✅    |✅|✅|
| Pythonic experience             |✅|✅| ❌    |☑️|❌|
| IO support for filetypes        |✅|❌| ❌    |❌|❌|
| Deep learning framework support |✅|✅| ❌    |❌|❌|
| multi-core/GPU support          |✅|☑️| ❌    |❌|❌|
| Rich functions for data types   |✅|❌| ❌    |✅|❌|


## To Jina Users

Jina 2.0-2.6 *kind of* have their own "DocArray", with very similar `Document` and `DocumentArray` interface. However, it is an old design and codebase. Since then, many redesigns and improvements have been made to improve its efficiency, usability and portability. DocArray is now an independent package that other frameworks such as future Jina 3.x and Finetuner will rely on.

The first good reason to use DocArray is its efficiency. Here is a side-by-side speed comparison of Jina 2.6 vs. DocArray on some common tasks.

```{figure} speedup-vs2.svg
```

The benchmark was conducted on 100K Documents/DocumentArray averaged over 5 repetitions with min & max values removed.

Besides code refactoring and optimization, many features have been improved or redesigned including:
- Advanced indexing for both elements and attributes;
- Comprehensive serialization protocols;
- Unified and improved Pythonic interface; 
- Improved visualization on Document and DocumentArray;
- ... and many more.

The new Jina 3.0 (expected in Feb. 2022) will fully rely on the new DocArray.