# Tools for ML

anaconda

jupyter notebook

kaggle&#x20;

google colab





you can import data sets from kaggle to google drive directly using the following metod



go to kaggle and get api token

profile > account > create new api token > download kaggle.json

download kaggle.json

now run following command in google colab

`!mkdir -p ~/.kaggle`

`!cp kaggle.json ~/.kaggle`



now you can directly download any dataset from kaggle to google colab using the copy api command from kaggle



like this

`kaggle datasets download -d andrewmvd/face-mask-detection`



```notebook-python
!chmod 600 /root/.kaggle/kaggle.json
!kaggle datasets download -d andrewmvd/face-mask-detection
```

now this following code to extract the content of dataset

```
import zipfile
zip_ref = zipfile.ZipFile("face-mask-detection.zip","r")
zip_ref.extractall("/content")
zip_ref.close()
```





