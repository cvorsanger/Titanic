# Titanic

The Jupyter notebook of my first Machine Learning adventure. This is the famous titanic dataset. The notebook was done on kaggle for their titinic dataset competition at https://www.kaggle.com/c/titanic

<center><img src="https://atlasrtx.com/wp-content/uploads/2021/05/AtlasRTX-logo-color-v2Asset-2.svg" width=350></center><br>

# Get All Communties Currently in the Atlas-Prod Feeds

Python script to help pull all communties currently served by an AtlasRTX bot. When ran csv files will be created that detail community information, and differences since the last run.

## Installation <br>
Make sure you have the latest version of python installed on your computer. You can get python at the offical python webpage; [Download Python](https://www.python.org/downloads/release/python-3100/).

Another option is to use Anaconda; [Anaconda Homepage](https://www.anaconda.com/products/individual). Anaconda also makes for a great package manager.

Either solution should work for Windows, Mac, or Linux (cough, go penguin, cough)<br><br>

### Packages<br>
Most packages used come standard with python however, <b>pandas</b> for is used for data processing and <b>azure.storage</b> is used to read in rthe data. Please set up an environment to contain these two packages. 

If you are unsure please see either the environment.yml or environment.txt files.  You can set up an environment using either file.

- Using AnaConda (prefered) 
```
$ conda env create -f environment.yml
```
- Using Pip
    - Windows
    ```
    > py -m pip install -r requirements.txt
    ```
    - Mac/Linux
    ```
    $ python3 -m pip install -r requirements.txt
    ```

## Usage<br>
You can run this script on the command line by:
- Windows
```
> py communities.py
```
- Mac/Linux
```
$ python3 communities.py
```

By default this script will get all possible communities and output them to a file; [Communities.csv]('./Communities.csv). The information contained for each community is:
- Brand-ID: AtlasRTX Brand identifier
- Community Name: Name of Community from client's feed
- City: City of community
- State: State of community
- Builder: Identifier given from client feed for specific feed
- Market Name: Target market, given by client's feed
<br>

An additional file will also be created; [Delta.csv](.Delta.csv). This file will only given community additions and subtractions. in addition to what is contained in Communities.csv this file will also have:
- kind : (+) for an addition, (-) for a subtraction

### Flags<br>
The following section will detail CLI flags in Mac/Linux. In Windows make the same changes, just from your base Windows CLI statement,
<br><br>
1.  To only output a Communities.csv file provide the -c flag 
```
$ python3 communities.py -c
```
2. To only output a Delta.csv file provide the -c flag 
```
$ python3 communities.py -d
```
3.  To rename Communities.csv file provide the -f flag. An extension is not needed as it only outputs csv
```
$ python3 communities.py -f <filename>
```
4.  To rename Delta.csv file provide the -o flag. An extension is not needed as it only outputs csv
```
$ python3 communities.py -o <filename>
```

## Work needed <br>

- [x] Parse all communities into a csv
- [ ] Create a community change csv
- [ ] Automatically upload communties to NLP Provider through API call
- [ ] Ability to only get certain brands
