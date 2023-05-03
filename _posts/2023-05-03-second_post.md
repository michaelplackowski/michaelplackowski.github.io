## Blog Post (BP) #2 - Introduction to fastai with Bird & Forest Recognition

# First Foray into Deep Learning & AI
## Quick & Powerful
---
Following the fastai course by Jeremy Howard, I have gone through and ran the bird and forest recognition model using the fastai library among others. DuckDuckGo was used to search for and download images for training and verification - it all worked perfectly and was quick to run. 

The code used to search for and download images may be seen below (where images that failed to download were removed):

```python
searches = 'forest','bird'
path = Path('bird_or_not')
from time import sleep

for o in searches:
    dest = (path/o)
    dest.mkdir(exist_ok=True, parents=True)
    download_images(dest, urls=search_images(f'{o} photo'))
    sleep(10)  # Pause between searches to avoid over-loading server
    download_images(dest, urls=search_images(f'{o} sun photo'))
    sleep(10)
    download_images(dest, urls=search_images(f'{o} shade photo'))
    sleep(10)
    resize_images(path/o, max_size=400, dest=path/o)

failed = verify_images(get_image_files(path))
failed.map(Path.unlink)
len(failed)
```
    12

To train the model, the following code snippet was used to create training and validation sets of images:
```python
dls = DataBlock(
    blocks=(ImageBlock, CategoryBlock), 
    get_items=get_image_files, 
    splitter=RandomSplitter(valid_pct=0.2, seed=42),
    get_y=parent_label,
    item_tfms=[Resize(192, method='squish')]
).dataloaders(path)
```
With the actual training implemented using the following:
```python
learn = vision_learner(dls, resnet18, metrics=error_rate)
learn.fine_tune(3)
```
*Only **2** lines!*[^1]

## Using the Trained Model is Easy!
---
Finally, using the trained model, other images can be input to be recognised (in this case, the two categories trained to be recognised were images of birds and forests):
```python
is_bird,_,probs = learn.predict(PILImage.create('bird.jpg')) # 'bird.jpg' or 'forest.jpg'
print(f"This is a: {is_bird}.")
print(f"Probability it's a bird: {probs[0]:.4f}") # probs[x] -> x=0:probability it's a bird, x=1:probability it's a forest
```
    This is a: bird
    Probability it's a bird: 1.0000

## Footnotes

[^1]: Making use of a complex neural network