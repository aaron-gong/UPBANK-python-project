# UPBANK-python-project
A project that utilizes UP bank's API to pull and analyse transactional data

There are two primary goals of this project. 

1. To utilize UP Bank's API to practice calling APIs using Python
2. To analyze the pulled data to determine where my money is going. 

The first step is to successfully request the data via API.

I first needed to obtain my personal access token from UP, which was done via scanning a QR code with the app. 
Once the personal access token was obtained, it is put into a header:

 		Authorization: Bearer $your_access_token

This is included in the request which looks like this in Python:

    baseurl = "https://api.up.com.au/api/v1"
    endpoint = "/transactions"
    header = {"Authorization" : "Bearer token_goes_here"}
    requests.get(baseurl+endpoint, headers = header, params= 'page[size]=100')

Note the page[size] is capped at 100, so that's the sample size I'm working with in this project. 

From there, the data is pulled into a JSON, relevant data is extracted into a DataFrame for analysis. 

Please see the attached jupyter notebook file for further details.

Thanks for reading!
