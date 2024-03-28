# use-postal-ph

This utility library is specifically designed for the Philippines, providing comprehensive information on postal codes,
municipalities, locations, and regions. Moreover, searching within the library is case insensitive.

![use-postal-ph](https://github.com/blckclov3r/use-postal-ph/blob/master/img/use-postal-ph.png?raw=true)

[![npm version](https://img.shields.io/npm/v/use-postal-ph?style=flat-square&alt=use-postal-ph)](https://www.npmjs.com/package/use-postal-ph)
[![Bundlephobia](https://img.shields.io/bundlephobia/min/use-postal-ph)](https://bundlephobia.com/result?p=use-postal-ph)
[![Downloads](https://img.shields.io/npm/dt/use-postal-ph.svg?style=flat-square)](https://www.npmjs.com/package/use-postal-ph)
[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/blckclov3r)
[![jsDocs.io](https://img.shields.io/badge/jsDocs.io-reference-blue)](https://www.jsdocs.io/package/use-postal-ph)

## Installation

Install via NPM:

```bash
npm install use-postal-ph
````

Or via Yarn:

```bash
yarn add use-postal-ph
```

## Usage

First, import the `use-postal-ph` function:

```javascript
import usePostalPH from 'use-postal-ph';
```

Now, you can use the various methods provided by the library to fetch postal code, municipality, location, and region
information:

```javascript
const postalPH = usePostalPH();

// Fetch a list of municipalities
const municipalities = postalPH.fetchMunicipalities();
console.log(municipalities);

// Fetch postal codes
const postalCodes = postalPH.fetchPostCodes();
console.log(postalCodes);

// Fetch locations
const locations = postalPH.fetchLocations();
console.log(locations);

// Fetch regions
const regions = postalPH.fetchRegions();
console.log(regions);

// Fetch all data lists
const allData = postalPH.fetchDataLists();
console.log(allData);
```

You can also specify search criteria and limit the number of results returned:

```javascript
// Fetch a list of municipalities starting with 'Manila' and limit the result to 10
const municipalities = postalPH.fetchMunicipalities({search: 'Manila', limit: 10});
console.log(municipalities);

// Fetch postal code for 6045
const postalCodes = postalPH.fetchPostCodes({search: 6045});
console.log(postalCodes);

// Fetch postal codes with a limit of 5
const postalCodes = postalPH.fetchPostCodes({limit: 5});
console.log(postalCodes);

// Fetch locations containing 'Cebu' and limit the result to 3
const locations = postalPH.fetchLocations({search: 'Cebu', limit: 3});
console.log(locations);

// Fetch regions starting with 'NCR' and limit the result to 8
const regions = postalPH.fetchRegions({search: 'NCR', limit: 8});
console.log(regions);

// Fetch all data lists with a limit of 15
const allData = postalPH.fetchDataLists(15);
console.log(allData);

// Fetch data based on the search criteria and limit
const result = postalPH.fetchDataLists({
    post_code: 604,
    location: "ta",
    region: "VII",
    municipality: "Cebu"
});
console.log(result);
```

## Return Values

When fetching data, the function returns either an array of objects or an array of strings, depending on the method
used:

- If the method returns an array of objects:
    - Each object represents a place with the following properties:
        - `municipality`: The name of the municipality.
        - `location`: The specific district or neighborhood.
        - `post_code`: This represents the specific postal code assigned to the location.
        - `region`: The region where the place is located.

- If the method returns an array of strings or numbers:
    - Each string or number represents a specific piece of information, such as a postal code, location, or region.

## Query Options

When using the library's methods, you have the option to include an object containing two parameters:

- **Search**: This parameter is used to find specific information. For postal codes, search directly for the code
  itself.
- **Limit**: Optionally restricts the number of results returned. Please note that the `limit` parameter doesn't apply
  to postal codes. It functions differently and cannot be used to restrict the results when searching for postal codes.

## ECMAScript Module (ESM) Entry Point

If you prefer not to install the package and want to include the ECMAScript module (ESM) entry point directly in your
project, you can use the following script tag:

- CDN (
  jsDelivr): [`https://cdn.jsdelivr.net/npm/use-postal-ph@1.0.4/dist/index.mjs`](https://cdn.jsdelivr.net/npm/use-postal-ph@1.0.4/dist/index.mjs)

- npm: [`https://unpkg.com/use-postal-ph@1.0.4/dist/index.mjs`](https://unpkg.com/use-postal-ph@1.0.4/dist/index.mjs)

```html

<script type="module">
    import usePostalPH from 'https://unpkg.com/use-postal-ph@1.0.4/dist/index.mjs';

    const {
        fetchDataLists,
        fetchLocations,
        fetchMunicipalities,
        fetchPostCodes,
        fetchRegions
    } = usePostalPH();

    console.log(fetchPostCodes({search: "6045"}))
</script>
```

This script imports the `fetchPostCodes` function from the `use-postal-ph` package and retrieves information for the
postal code '6045'. It then logs the result to the console.

```json
{
  "municipality": "Cebu",
  "region": "VII",
  "location": "Talisay",
  "post_code": 6045
}
```

## Demo

Explore the live demo to experience fetching and searching functionalities for municipalities, post codes, locations,
and regions. Interact with the application to witness its efficiency and responsiveness in action.

https://use-postal-ph.vercel.app

## Contribution Guidelines

Contributions are highly appreciated! To contribute, fork the repository, create a new branch for your changes, and
submit a pull request. Please ensure your code adheres to the existing coding standards and conventions. While this
library provides information, it may not be comprehensive. Contributions aimed at improving data completeness are
welcome.

## License

MIT &copy; [blckclov3r](https://github.com/blckclov3r/use-postal-ph?tab=MIT-1-ov-file)