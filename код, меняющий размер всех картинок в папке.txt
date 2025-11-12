from glob import glob
from PIL import Image
import os


i = 1
if __name__ == '__main__':
    os.chdir("Stalin")                  # закинь папку с картинками в папку с проектом и поменяй тут на имя своей папки
    os.mkdir('400x400')
    for filename in glob('*.png'):
        original_image = Image.open(filename)
        resized_image = original_image.resize((400, 400))
        os.chdir("400x400")
        resized_image.save(str(i) + '_400x400.png')
        i += 1
        os.chdir("..")

print("Готово. Теперь внутри изначальной папки будет новая, хранящая измененные картинки.")
