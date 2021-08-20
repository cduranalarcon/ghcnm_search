# ghcnm_search

## Description

Function to read the Global Historical Climatology Network monthly (GHCNm) temperature dataset v4, selection data by station code or a rectangular geographic area. 

## Install ghcnm_search

```
$git clone https://github.com/cduranalarcon/ghcnm_search
```

## Usage (python3)

###  Search stations by --area

```
python ghcnm_search.py  -d path/to/ghcnm.tavg.vn.y.z.YYYMMDD.qcu.dat -m path/to/ghcnm.tavg.vn.y.z.YYYMMDD.qcu.inv -o output/path/ -a minlat minlon maxlat maxlon` 
```
###  Search stations by --code

```
$python ghcnm_search.py  -d path/to/ghcnm.tavg.vn.y.z.YYYMMDD.qcu.dat -m path/to/ghcnm.tavg.vn.y.z.YYYMMDD.qcu.inv -o output/path/ -c code-1 code-2 ... code-N
```
## Example

### Input

```
$python ghcnm_search.py -d ghcnm.v4.0.1.20210819/ghcnm.tavg.v4.0.1.20210819.qcu.dat -m ghcnm.v4.0.1.20210819/ghcnm.tavg.v4.0.1.20210819.qcu.inv -a -70 -70 -60 -50
```

### Output
```
###############################################################

26 stations were found.

           Code Elevation  Latitude  Longitude                         Name
0   AYM00088963      24.0   -63.400    -56.983               BASE_ESPERANZA
1   AYM00089050      14.0   -62.183    -58.883           BELLINGSHAUSEN_AWS
2   AYM00089053      11.0   -62.233    -58.633                  BASE_JUBANY
...
23  AYXLT546296      18.0   -63.500    -57.300                       PETREL
24  AYXLT606419      26.0   -67.800    -68.900                     ADELAIDE
25  AYXLT885346      10.0   -63.300    -57.900                    O_HIGGINS

Output files were saved in  '/home/human/ghcnm_search/ghcnm_out'

###############################################################
```
## Help

```
$python ghcnm_search.py -h
```
```
usage: ghcnm_search.py [-h] -d DATA_PATH -m METADATA_PATH [-o OUTPUT_PATH]
                       [-s STATIONS_LIST] [-c CODES [CODES ...]]
                       [-a AREA [AREA ...]]

Tool to select and read ghcnm datasets by area OR station code

optional arguments:
  -h, --help            show this help message and exit
  -d DATA_PATH, --data_path DATA_PATH
                        Filepath to ghcnm data
                        (ghcnm.tavg.vn.y.z.YYYMMDD.qcu.dat)
  -m METADATA_PATH, --metadata_path METADATA_PATH
                        Filepath to ghcnm metadata
                        (ghcnm.tavg.vn.y.z.YYYMMDD.qcu.inv)
  -o OUTPUT_PATH, --output_path OUTPUT_PATH
                        Output filepath
  -s STATIONS_LIST, --stations_list STATIONS_LIST
                        Name of the stations selected by area or a list of
                        station code
  -c CODES [CODES ...], --codes CODES [CODES ...]
                        List of station codes within the ghcnm dataset [code1
                        code2 code3 code4 ...]. When --codes is provides,
                        --area is not used.
  -a AREA [AREA ...], --area AREA [AREA ...]
                        Geographic coordinates of the opposite vertices of a
                        rectangle [minlat minlon maxlat maxlon]
```
## GHCNm temperature dataset v4 access

Download the data from the website of the National Centers for Environmental Information (NCEI) of NOAA: https://www.ncei.noaa.gov/pub/data/ghcn/v4/

or 

```
wget ftp://ftp.ncdc.noaa.gov/pub/data/ghcn/v4/ghcnm.latest.qcu.tar.gz
tar -xvf ghcnm.latest.qcu.tar.gz
```
