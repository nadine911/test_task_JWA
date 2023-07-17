# OMVIC PARSER

## The Task

Write a [Python] script that would parse all Dealerships and Salespersons for the https://omvic.powerappsportals.com/registrant-search/.


## INITIAL DATA

- city to scrape:
    ```
        ["Toronto", "Ottawa", "Mississauga"]
    ```
- shchema to save dealership:
    ```
        ref_id: str,
        legal_name: str,
        business_name: Optional[str],
        registration_status: str,
        web_url: str,
        website: Optional[str],
        emails: Optional[List[str]],
        phones: Optional[List[str]],
        country: str,
        state: str,
        city: str,
        zip: str,
        address: str,
        dealer_sub_class: Optional[str],
        extra_fields: Optional[JSON]
    ```
    * ref_id is a unique identifier of the entity on the website (like id or slug + id)
    * web_url is the address of the entity on [OMVIC]
    * website is the address of the personal [website of the dilership][dilership]
    * extra_fields is any other additional information that you think is important (example: {"awards": ["best company of the year 2022"]})
    
- shchema to save salespersons:
    ```
        ref_id: str,
        first_name: str,
        last_name: Optional[str],
        registration_status: str,
        expiry_date: str
        reports: Optional[str],
        dealerships: Optional[str],
    ```
    * expiry_date must be saved as a string in ISO 8601 date format
    * dealerships must contain a list of dealership's ref_ids where the salesperson is currently working

You should be able to complete this assignment without any third-party dependencies outside of the Python Standard Library, with the exception of the [BeautifulSoup] library for parsing HTML and XML documents. However, you can use any libraries you think are best for you. Please target Python version 3.7 or higher.

The results of scraping should be saved as CSV files with the names: omvic_dealerships.csv and omvic_salespersons.csv.

_Example of expected result:_

```
        ref_id 64c1ea05-b9e9-ed11-a7c5-000d3ae86452,
        legal_name: "MARKVIEW AUTO SALES LIMITED",
        business_name "",
        registration_status: "Terminated",
        web_url:  "https://omvic.powerappsportals.com/registrant-search/find-dealership-salesperson/dealership-profile/?id=e3d308f3-b9e9-ed11-a7c5-000d3ae86cd0",
        website: "",
        emails: "firs@markview.ca, seecond@markview.ca",
        phones: "4167404055, 4162093844",
        country: "Canada",
        state: "Ontario",
        city: "Toronto",
        zip: "M9L 1X9",
        address: "19-151 TORYORK DR",
        dealer_sub_class: "New and Used Motor Vehicles",
        extra_fields: "",
```

## Evaluation

Your code will be evaluated using the following criteria:

- Code simplicity, cleanliness, organization, and readability
- Data structures and algorithms used
- Correctness of the output

## How to Submit Your Solution?

Create a new Git repository either on GitHub or GitLab, and make all your commits there. When ready, send a link to the repository as a reply to the message. If you make the repo private, please remember to grant read permissions and send an invitation link to `nadia@justwebagency.com`.

## License

MIT


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [Python]: <https://www.python.org/downloads/release/python-390/>
   [OMVIC]: <https://omvic.powerappsportals.com/registrant-search/find-dealership-salesperson/dealership-profile/?id=c8d83e17-bbe9-ed11-a7c5-002248af89ad>
   [dilership]: <https://www.mercedes-benz-midtown-toronto.ca>
   [BeautifulSoup]: <https://pypi.org/project/beautifulsoup4/>