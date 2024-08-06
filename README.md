# Surfboards image training

This Notebook code for training a model for binary image classification.


```bash
pip install keras 
```

## Usage

```python
from PIL import Image
import keras
import numpy as np

img = Image.open('board_fundo.jpeg')
img = img.resize((256, 256))
img_tensor = keras.utils.img_to_array(img)
img_tensor = np.expand_dims(img_tensor, axis=0)
model = keras.saving.load_model('surfboard-classifier.keras', custom_objects=None, compile=True, safe_mode=True)
model.load_weights(checkpoint_filepath)
pred = model.predict(img_tensor)
print(f"prediction: {pred[0][0]}")

if (pred[0][0] > 0.5):
    print('fundo da prancha')
else:
    print('frente da prancha')
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

## License

[MIT](https://choosealicense.com/licenses/mit/)
