🐦 multi_label_pigeon
========================

This repo is a simple multiclass image extenstion of the pigeon library by
@agermanidis located [here](https://github.com/agermanidis/pigeon). Credit goes to them for building
the annotate function for images, text, and regression for multi-class type problems. All I am doing is extending it to multi-label and multi-task type problems.

## Installation

Can install with standard pip.

```
pip install multi-label-pigeon
```


## Examples

```
from multi_label_pigeon import multi_label_annotate
from IPython.display import display, Image

annotations = multi_label_annotate(
    ['assets/altera.jpg', 'assets/chibi_gil.jpg','assets/chibi_saber.jpg'],
    options={'cute':['yes','no'], 'saber':['yes','no'],'colors':['blue','gold','white','red']},
    display_fn=lambda filename: display(Image(filename))
    )
```
Preview:

![alt text](/assets/sample_usage5.gif)

**New in v0.3.0: colors!** 
![](https://user-images.githubusercontent.com/31417712/85953171-0f0a6980-b934-11ea-8137-51718f88fd22.gif) 

## Additional Notes

- `skip` readded the old skip button for clarity. In the case you dont want to label any annotations for a sample you can press `skip` or `done` but having `skip` is probably more clear.

I added some additional buttons as well to the multi-label script. Since we want to be able to select more than one category I added a few extra buttons.

- `done` to press after all relevant fields have been clicked. 

- `back` button in case you want to go back to a previous image. **WARNING** this will erase that item from the dictionary so you will have to click through all the classes you want to mark for that previous image again. 
![back_example](/assets/back.gif)

- `clear current` **WARNING** will delete the current image from the dictionary on the back end so you can re enter the classes in case you messed one up.
![clear_current](/assets/clear_current2.gif)

