# open fruit

This data package defines the "Open Fruit" dataset. Open Fruit is a collection of raw and cropped images and associated metadata of fruits taken from the [Google Open Images V4 dataset](https://github.com/openimages/dataset), which was generated by scraping and classifying permissively-licensed images on [flickr](https://www.flickr.com/). You can view this data package on [GitHub](https://github.com/quiltdata/open-fruit) (code only) or on [Quilt T4](https://alpha.quiltdata.com/b/quilt-example/tree/quilt/open_fruit/) (code + data).

To learn more about Open Images check out ["How to classify photos in 600 classes using nine million open images"](https://blog.quiltdata.com/how-to-classify-photos-in-600-classes-using-nine-million-open-images-3cdb989ad1c2).

This data package is used for a pair of articles:

* ["Boost your CNN image classifier performance with progressive resizing in Keras"](https://blog.quiltdata.com/boost-your-cnn-image-classifier-performance-with-progressive-resizing-in-keras-c215127bf55b)
* ["Building a fully reproducible machine learning pipeline with Comet.ml and Quilt"](https://medium.com/@ceceliashao/aa9c7bf85e72)

See also the [`ResidentMario/progressive-resizing`](https://github.com/ResidentMario/progressive-resizing) and [`comet-ml/keras-fruit-classifier`](https://github.com/comet-ml/keras-fruit-classifer) repositories, which contain the model builds that use this package.

To rebuild this dataset from scratch:

1. Run `notebooks/initial-exploration.ipynb`, to download the image metadata.
2. Download the [`openimager` script](https://github.com/quiltdata/open-images/blob/master/src/openimager/openimager.py) and run `python -c "import openimager; openimager.download(['Apple', 'Banana', 'Cantaloupe', 'Common fig', 'Grape', 'Grapefruit', 'Lemon', 'Mango', 'Orange', 'Peach', 'Pear', 'Pineapple', 'Pomegranate', 'Watermelon', 'Strawberry', 'Tomato'])"` (warning: this will take some time).
3. Run `notebooks/build-dataset.ipynb` to crop the images and split them by class (this will also take some time).