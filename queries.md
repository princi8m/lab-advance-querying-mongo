![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

<!-- Your Code Goes Here -->
const filter = {
  'name': 'Babelgum'
};

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

<!-- Your Code Goes Here -->
const filter = {
  'number_of_employees': {
    '$gte': 5000
  }
};
const limit = 20;

//filter    {number_of_employees: {$gte: 5000 }}

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

const filter = {
  '$and': [
    {
      'founded_year': {
        '$gte': 2000
      }, 
      'founded_year': {
        '$lte': 2005
      }
    }
  ]
};
const projection = {
  'name': 1, 
  'founded_year': 1
};

//{$and: [ {founded_year: { $gte: 2000}, founded_year: { $lte: 2005} }]}
//{ "name": 1, "founded_year": 1 }


### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

// there is no ipo field in my data 
<!-- Your Code Goes Here -->

const filter = {
  '$and': [
    {
      'ipo': {
        '$gte': 100000000
      }, 
      'founded_year': {
        '$lt': 2010
      }
    }
  ]
};
const projection = {
  'name': 1, 
  'ipo': 1
};

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

<!-- Your Code Goes Here -->
const filter = {
  '$and': [
    {
      'founded_year': {
        '$lte': 2005
      }, 
      'number_of_employees': {
        '$lte': 1000
      }
    }
  ]
};
const sort = {
  'number_of_employees': 1
};
const limit = 10;


//filter  {$and: [ {founded_year: { $lte: 2005}, number_of_employees: {'$lte': 1000}}]}
//sort  { number_of_employees:  1 }

### 6. All the companies that don't include the `partners` field.

<!-- Your Code Goes Here -->
 {
     partners: $not
 }


### 7. All the companies that have a null type of value on the `category_code` field.

<!-- Your Code Goes Here -->
 {
     category_code: null
 }

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

<!-- Your Code Goes Here -->
const filter = {
  '$and': [
    {
      'number_of_employees': {
        '$gte': 100
      }, 
      'number_of_employees': {
        '$lt': 1000
      }
    }
  ]
};
const projection = {
  'name': 1, 
  'founded_year': 1
};

//filter    {$and: [ {number_of_employees: { $gte: 100}, number_of_employees: { $lt: 1000} }]}
//project    { "name": 1, "founded_year": 1 }


### 9. Order all the companies by their IPO price in a descending order.

<!-- Your Code Goes Here -->
const filter = {};
const sort = {
  'ipo': -1
};

//sort  { ipo:  -1 }

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

<!-- Your Code Goes Here -->
const filter = {};
const sort = {
  'number_of_employees': -1
};
const limit = 10;

//sort    { number_of_employees:  -1 }

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

<!-- Your Code Goes Here -->
const filter = {
  'founded_month': {
    '$gt': 6
  }
};
const limit = 100;

//filter    {founded_month: {$gt: 6 }}


### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

<!-- Your Code Goes Here -->

const filter = {
  '$and': [
    {
      'founded_year': {
        '$lt': 2000
      }, 
      'ipo': {
        '$gt': 10000000
      }
    }
  ]
};

//filter    {$and: [ {founded_year: {$lt: 2000 }, ipo: {$gt:10000000}}]}

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

<!-- Your Code Goes Here -->
const filter = {
  'acquired_year': {
    '$gt': 2010
  }
};
const projection = {
  'name': 1
};

//filter    {acquired_year: {$gt: 2010 }}
//project   {name: 1}


### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

<!-- Your Code Goes Here -->

const filter = {};
const projection = {
  'name': 1, 
  'founded_year': 1
};
const sort = {
  'founded_year': 1
};


//project    {"name": 1,"founded_year": 1 }
//sort    {"founded_year": 1 }


### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

<!-- Your Code Goes Here -->
const filter = {
  'founded_day': {
    '$gte': 7
  }
};
const sort = {
  'price_amoun': -1
};
const limit = 10;

//filter   {founded_day: {$gte: 7 }}
//sort    {price_amoun: -1 }

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

<!-- Your Code Goes Here -->

const filter = {
  '$and': [
    {
      'category_code': 'web'
    }, {
      'number_of_employees': {
        '$gt': 4000
      }
    }
  ]
};
const sort = {
  'number_of_employees': 1
};


//filter    {$and: [ {  category_code: 'web'}, {number_of_employees: { $gt: 4000}}]}
//sort      {number_of_employees: 1 }

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

<!-- Your Code Goes Here -->

const filter = {
  '$and': [
    {
      'ipo': {
        '$gt': 10000000
      }
    }, {
      'currency': 'EUR'
    }
  ]
};

//filter    {$and: [  {ipo: {$gt:10000000}},  {currency: 'EUR'}   ]}

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

<!-- Your Code Goes Here -->

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

<!-- Your Code Goes Here -->
