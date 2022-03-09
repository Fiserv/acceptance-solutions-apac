# API Usage
Please note below details for all the APIs:

**Date fields**: All date fields (Request and Response) will be Gregorian -BasicISO (YYYYMMDD) unless mentioned otherwise.

**Amount Fields**: Unless otherwise specified all amount fields are returned in cents or pence or equivalent.

**Decimal fields**: The actual decimal point needs to be calculated based on the processing parameter. Number of Decimals used is returned as part of the response. API Request and Response do not display the decimal point unless mentioned in description for field or service. However, the Response provides “number of decimals” as an additional field. For example, “13000” in the Request field is accepted as 130.00. In Response 130.00 will be displayed as 13000 with number of decimal=2.

## JSON Considerations:

* To omit the field data from request objects, tag for the field should be omitted from the request altogether
* In the request object, numeric fields should not contain null strings (“”)
Date fields must conform to the format specified as part of that fields description
* In the response objects, any field that is alphanumeric with spaces as its value, will be omitted

## General 453 Error Messages:

1. [field] is required
2. [field] should be numeric
3. Length of [field] should not exceed <n> byte(s)
4. [field] should be numeric and should 4. not exceed <n> byte(s)
5. [field] should be numeric and in the format - MMYY
6. [field] should be numeric and in the format - YYMM
7. Invalid date in [field]. Expected BasicISO Date - YYYYMMDD format