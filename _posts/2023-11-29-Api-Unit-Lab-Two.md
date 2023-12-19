---
layout: post
title: Api Unit Lab Two
subtitle: Using an Animal Crossing API to analyze data
tags: [code,lab]
comments: true
---
{: .box-note}
Here are my reflections for the lab

## Part One

**Discuss how you used the API to obtain the dataset.**

```python
def getData(idx):
    allData = []
    
    for i in range(0, idx):
        payload = {'key' : "GrayArtOfDataKEY123ABCsecret", 'idx' : i}
        response = requests.get(url + endpoint, params=payload)
        if response.status_code == 200:
            allData.append(response.json())
        else:
            print(f"Error at index {i}: {response.status_code}")
            print("Response content:", response.text) 
            continue

    return allData
```
To start I used the base URL (https://afeingoldhm.pythonanywhere.com) and the specific endpoint (/socks), which was important as the data I needed to answer the questions were all related to the socks. The base URL and endpoint form the full URL to which the GET requests are sent. The questions required me to look through many rows of data from the source, meaning multiple requests had to be sent to the api through a range of indices (0, 363 - for every row in the dataset). For each request a payload is made, which requires two fields, a 'key' (an API key, which allowed the program to identify and authenticate me), and 'idx' (the number that acts as a representative for the row you wish to extract data from). The requests.get method was used to send the GET request to the API, the full URL and the payload were used as arguments. If the response status code was 200, it meant that the request was successful, and the data from the response in json format was added to the 'allData' list. But, if any other status code was received an error message was printed along with the index at which it failed. The function then returns allData. 

```python
def makeCSV(data, fileName):
    if data is not None:
        cats = data[0].keys()
        with open(fileName, 'w', newline='', encoding='utf-8') as file:
            dict_writer = csv.DictWriter(file, cats)
            dict_writer.writeheader()
            dict_writer.writerows(data)

        print(f"Data saved to {fileName}")
    else:
        print("No data available.")
```
After obtaining the data from the API using the getData function, it was next converted into a '.CSV' using the function above, for easier analysis. First the function checks if there is any data available. If the 'data' parameter is empty or 'None', it will exit the function. Assuming the data is not empty, the data extracts the key from the first item in the list, these keys represent the column headers for the '.CSV' file. The function then creates a new '.CSV' file with the inputed 'fileName', using the 'open' function in the writing mode. A 'csv.DictWriter' object is created, passing the opened file and the list of column headers ('cats'). The 'writeheader()' method wrote the column headers into the '.CSV' file. The 'writerows()' method writes each item from the 'data' list to the '.CSV' file. Since data is expected to be a list of dictionaries and the keys of these dictionaries match the headers, each dictionary in the list is written as a row in the '.CSV' file. After writing all the data, the '.CSV' file is closed. 

## Part Two

'''python
import requests
import csv

url = "https://afeingoldhm.pythonanywhere.com"
endpoint = "/socks"

def most_variations(csvName):
    # Opening and reading from the CSV file
    with open(csvName, "r") as f:
        data = csv.DictReader(f)

        variation_counter = {}

        max_variations = 0
        socksmax_variations = []

        for row in data:
            sock_name = row['Name']
            variation = row['Variation']

            if sock_name not in variation_counter:
                variation_counter[sock_name] = {variation}
            else:
                variation_counter[sock_name].add(variation)

        for sock, variations in variation_counter.items():
            variation_counter[sock] = len(variations)

        for sock, count in variation_counter.items():    
            if count > max_variations:
                max_variations = count
                socksmax_variations = [sock]
            elif count == max_variations:
                socksmax_variations.append(sock)

        print(f"The following socks: {', '.join(socksmax_variations)}. Have the most variations at: {max_variations}")

def color_counter(csvName):
    # Opening and reading from the CSV file
    with open(csvName, "r") as f:
        data = csv.DictReader(f)

        color_counter = {}

        for row in data:
            color1 = row['Color 1']
            color2 = row['Color 2']

            if color1 == color2:
                    if color1 not in color_counter:
                        color_counter[color1] = 1
                    else:
                        color_counter[color1] += 1
            else:
                if color1 not in color_counter:
                    color_counter[color1] = 1
                else:
                    color_counter[color1] += 1

                if color2 not in color_counter:
                    color_counter[color2] = 1
                else:
                    color_counter[color2] += 1

        for color, count in color_counter.items():
            print(f"{color}: {count}")
'''

Once I had fully converted the API into the CSV, the process of writing the code was relatively easy. Due to us having done multiple projects analyzing CSV files these questions were very similar, the brunt of the work was definitely trying to figure out how to make the payload, and trying to "get" the data in general. 
