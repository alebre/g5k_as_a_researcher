# g5k_as_a_researcher

## Installation

to clone the repository, please run the following command:

```
git clone --recursive https://github.com/badock/g5k_as_a_researcher.git
```

Do not forget the **--recursive** option, otherwise a dependency may be missing.

## External libraries

This project is making an extensive use of the following libraries:

* scholar.py ([https://github.com/ckreibich/scholar.py](https://github.com/ckreibich/scholar.py))
* you need to install BeautifulSoup (pip install beautifulsoup)
* You need to install selenium (pip install selenium)

## Misc
* worker_0 => alebre

## usage
* Create additional directory in data and results
```
mkdir ./data/$DATE ; mkdir ./results/$DATE
```
* Retrieve the json index of G5K  (please replace DATE by the current date in a weird format such as XXMonthYYY)
```
curl -o ./data/$DATE/index.json -u alebre  https://intranet.grid5000.fr/g5kbib/index.json
python make_g5k_profile.py
```
Please note that the above script can last several days as it rely on several sleep of random duration between 30 and 120 seconds. Such random sleeps are mandatory to avoid being blocked by Google. 
```
python ./compute_g5k_index.py 
```
The result should be in the form fo 
There are 768 publications
g5k profile: citations nb 6625, h_index 66, i_index 174 (not_evaluated 23)

If you want to get a textual representation of the json sorted list
```
cat ./results/$DATE/sorted_results.json | json_pp -t dumper > ./results/$DATE/desc-sorted-list.txt
```
