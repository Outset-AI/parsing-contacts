If the "contacts.csv" has the following content:

```
first name,last name,email,phone,birthday
John , Dow   ,john@dow.com,(416) 111-1111,   1980-01-15
John ,   Dow,john2@dow.com,,1980-01-15
Jane   ,Dow,jane@dow.com,   (416) 222-2222,1980-02-15
```
The output of your script, when run against the above example should be:

`[{"first name":"John","last name": "Dow","email": "john2@dow.com","phone": "(416) 111-1111","birth date": "1980-01-15"},{"first name":"Jane","last name":"Dow","email":"jane@dow.com","phone":"(416) 222-2222","birth date":"1980-02-15"}]`

Please note that the JSON output doesn’t need to be prettified, and that the trailing whitespaces were removed, along with the duplicate entry for "John Dow".

In case there is data missing from one contact, the property should still exist, but with a null value. For example, if the "contacts.csv" file has the following content:

```
first name,last name,email,phone,birth date
John,Dow,,(416) 111-1111,
```
The output of your script, when run against the above example should be:

 `[{"first name":"John","last name": "Dow","email": null,"phone": "(416) 111-1111","birth date": null}]`