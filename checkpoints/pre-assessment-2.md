# Pre-Assessment, Version 2


<!-- QUESTION #1 -->
### !challenge
* type: multiple-choice
* id: 6c2e1ac6-2798-4429-8ca1-beb29507a8b3
* title: Data Type Identification
* topics: Data Types
##### !question
The below variable is assigned to which data type?

`const vehicle = { make: "Toyota", model: "4Runner" }`
##### !end-question
##### !options
* string
* array
* object
* number
* undefined
* null
##### !end-options
##### !answer
* object
##### !end-answer
### !end-challenge



<!-- QUESTION #2 -->
### !challenge
* type: code-snippet
* language: javascript
* id: a31d7e48-9b15-4973-a730-22ffac9b4930
* title: Write the Function
* topics: Functions
##### !question
Write a function `fuelEfficiencyDescription()` that accepts an object, `vehicle`, which would look like this:
```js
const vehicle = {
   make: "Hyundai",
   model: "Veracruz",
   year: "2007",
   milesPerGallon: 20,
   type: "SUV",
   dailyRateInUSD: 50,
   weeklyRateInUSD: 300
}
```
The function should return a message detailing the vehicle's fuel efficiency, or `milesPerGallon`, like this:

`"The <make> <model> has a fuel efficiency of <milesPerGallon> MPG."`
##### !end-question
##### !placeholder
```js
function fuelEfficiencyDescription(vehicle) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testFleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    },
    {
       make: "Toyota",
       model: "4Runner",
       year: "2020",
       milesPerGallon: 16,
       type: "SUV",
       dailyRateInUSD: 75,
       weeklyRateInUSD: 495
    },
  ]

describe('fuelEfficiencyDescription', function() {
  it("returns a string", function() {
    let result = fuelEfficiencyDescription(testFleet[0])
    expect(typeof result).to.deep.eq("string")
  })
  it("returns the correct string for the input vehicle", function() {
    let result = fuelEfficiencyDescription(testFleet[1])
    expect(result).to.deep.eq("The Volkswagen Jetta has a fuel efficiency of 31 MPG.")
  })
})
```
##### !end-tests
### !end-challenge




<!-- QUESTION #3 -->
### !challenge
* type: multiple-choice
* id: aa2ee46f-865a-410b-9615-d0902800975d
* title: Select the Logical Operators
* topics: Operators
##### !question
A customer is looking to rent a car.

Which logical expression represents that they would like a compact car or a sedan but not a luxury car?
##### !end-question
##### !options
* `("compact car" |& "sedan") && !"luxury"`
* `(!"compact car" || !"sedan") && "luxury"`
* `("compact car" &| "luxury") && !"sedan"`
* `("sedan" && "compact car") && !"luxury"`
* `("compact car" || "sedan") && !"luxury"`
##### !end-options
##### !answer
* `("compact car" || "sedan") && !"luxury"`
##### !end-answer
### !end-challenge



<!-- QUESTION #4 -->
### !challenge
* type: code-snippet
* language: javascript
* id: 8278cefa-031b-40aa-a631-c65afb891fbe
* title: Write a Function
* topics: Functions
##### !question
Write a function that accepts a parameter, `type`, a string, and an array, `fleet`, which represents a rental location's fleet of cars, and returns the exact string: `"There are <n> vehicles of type <type> at this location."`

A `fleet` array will look like this:
```js
const fleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    }
]
```
##### !end-question
##### !placeholder
```js
function carTypeSummary(type, fleet) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('carTypeSummary', function() {

  const testFleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    },
    {
       make: "Toyota",
       model: "4Runner",
       year: "2020",
       milesPerGallon: 16,
       type: "SUV",
       dailyRateInUSD: 75,
       weeklyRateInUSD: 495
    },
  ]


  it("should return a string", function() {
    let result = carTypeSummary("SUV", testFleet)
    expect(typeof result).to.deep.eq("string")
  })

  it("should return the correct string for a given input type for 1 match ", function() {
    let result = carTypeSummary("Compact", testFleet)
    let expected = "There are 1 vehicles of type Compact at this location."
    expect(expected).to.deep.eq(result)
  })

  it("should return the correct string for a given input type for multiple matches", function() {
    let result = carTypeSummary("SUV", testFleet)
    let expected = "There are 2 vehicles of type SUV at this location."
    expect(expected).to.deep.eq(result)
  })

  it("should return the correct string for a given input type for 0 matches", function() {
    let result = carTypeSummary("Sedan", testFleet)
    let expected = "There are 0 vehicles of type Sedan at this location."
    expect(expected).to.deep.eq(result)
  })
})
```
##### !end-tests
### !end-challenge



<!-- QUESTION #5 -->

### !challenge
* type: multiple-choice
* id: 5554e0ac-f4dc-46e4-a26e-d1dc73380325
* title: Pick the Function
* topics: Conditionals
##### !question
Which of the following functions would only return a vehicle from a year greater than the input year. A `vehicle` looks like this:
```js
let vehicle = {
   make: "Toyota",
   model: "4Runner",
   year: "2020",
   milesPerGallon: 16,
   type: "SUV",
   dailyRateInUSD: 75,
   weeklyRateInUSD: 495
}
```
##### !end-question
##### !options
*
```js
let vehicleSelector = (vehicle, year) => {
  if(vehicle.year >= year) {
    return vehicle
  }
}
```
*
```js
let vehicleSelector = (vehicle) => {
  if(vehicle.year > year) {
    return vehicle
  }
}
```
*
```js
let vehicleSelector = (vehicle, year) => {
  if(vehicle.year < year) {
    return vehicle.year
  }
}
```
*
```js
let vehicleSelector = (vehicle, year) => {
  if(vehicle.year > year) {
    return vehicle.year
  }
}
```
*
```js
let vehicleSelector = (vehicle, year) => {
  if(vehicle.year > year) {
    return vehicle
  }
}
```
##### !end-options
##### !answer
```js
let vehicleSelector = (vehicle, year) => {
  if(vehicle.year > year) {
    return vehicle
  }
}
```
##### !end-answer
### !end-challenge



<!-- QUESTION #6 -->

### !challenge
* type: code-snippet
* language: javascript
* id: 357f25b0-5de4-40ef-bdf6-6b677ccce11b
* title: Write a Function
* topics: Functions
##### !question
Uh oh!  Following a recent advertisement with our new low rates, one of our locations has mistakenly switched the weekly and daily prices for all of the vehicles in its fleet!

Write a function, `rateFixer()`, that takes in an array of cars, `fleet`, swaps their weekly and daily prices so they are back where they should be, and then returns the array.

Keep in mind that a `fleet` will have this structure:
```js
const fleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    }
]
```

##### !end-question
##### !placeholder
```js
function rateFixer(fleet) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js


describe('rateFixer', function() {
  it("returns an array", function() {
    const testFleet = [
      {
         make: "Hyundai",
         model: "Veracruz",
         year: "2007",
         milesPerGallon: 20,
         type: "SUV",
         dailyRateInUSD: 300,
         weeklyRateInUSD: 50
      },
      {
         make: "Volkswagen",
         model: "Jetta",
         year: "2019",
         milesPerGallon: 31,
         type: "Compact",
         dailyRateInUSD: 300,
         weeklyRateInUSD: 48
      },
      {
         make: "Toyota",
         model: "4Runner",
         year: "2020",
         milesPerGallon: 16,
         type: "SUV",
         dailyRateInUSD: 495,
         weeklyRateInUSD: 75
      }
    ]
    let result = rateFixer(testFleet)
    expect(Array.isArray(result)).to.deep.eq(true)
  })

  it("swaps the weekly and daily rates of all the cars", function() {
    const testFleet = [
        {
           make: "Hyundai",
           model: "Veracruz",
           year: "2007",
           milesPerGallon: 20,
           type: "SUV",
           dailyRateInUSD: 300,
           weeklyRateInUSD: 50
        },
        {
           make: "Volkswagen",
           model: "Jetta",
           year: "2019",
           milesPerGallon: 31,
           type: "Compact",
           dailyRateInUSD: 300,
           weeklyRateInUSD: 48
        },
        {
           make: "Toyota",
           model: "4Runner",
           year: "2020",
           milesPerGallon: 16,
           type: "SUV",
           dailyRateInUSD: 495,
           weeklyRateInUSD: 75
        }
    ]
    let result = rateFixer(testFleet)
    expect(result[0].weeklyRateInUSD).to.deep.eq(300)
    expect(result[0].dailyRateInUSD).to.deep.eq(50)
    expect(result[1].weeklyRateInUSD).to.deep.eq(300)
    expect(result[1].dailyRateInUSD).to.deep.eq(48)
    expect(result[2].weeklyRateInUSD).to.deep.eq(495)
    expect(result[2].dailyRateInUSD).to.deep.eq(75)
  })
})
```
##### !end-tests
### !end-challenge




<!-- QUESTION #7 -->
### !challenge
* type: multiple-choice
* id: 58a9793d-590d-40ce-a980-3acfecd617de
* title: Pick the Function
* topics: Functions
##### !question
A family wants to spend no more than `n` dollars per week on a vehicle rental.

Which function below would return an array of the makes and models they could rent from a location?
```js
const fleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    },
    {
       make: "Toyota",
       model: "4Runner",
       year: "2020",
       milesPerGallon: 16,
       type: "SUV",
       dailyRateInUSD: 75,
       weeklyRateInUSD: 495
    }
]
```
##### !end-question
##### !options
*
```js
let vehicleFilterOnPrice = (fleet) => {
  let eligibleVehicles = []
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD) {
      eligibleVehicles.push(fleet[i])
    }
  }
  return eligibleVehicles;
}
```
*
```js
let vehicleFilterOnPrice = (n, fleet) => {
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD <= n) {
      return fleet[i]
    }
  }
}
```
*
```js
let vehicleFilterOnPrice = (n, fleet) => {
  let eligibleVehicles = []
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD <= n) {
      eligibleVehicles.push(fleet[i])
    }
  }
  return eligibleVehicles;
}
```
*
```js
let vehicleFilterOnPrice = (n, fleet) => {
  let eligibleVehicles = []
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD < n) {
      eligibleVehicles.push(fleet[i])
    }
  }
  return eligibleVehicles;
}
```
*
```js
let vehicleFilterOnPrice = (n, fleet) => {
  let eligibleVehicles = {}
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD <= n) {
      eligibleVehicles.push(fleet[i])
    }
  }
}
```
##### !end-options
##### !answer
```js
let vehicleFilterOnPrice = (n, fleet) => {
  let eligibleVehicles = []
  for(let i = 0; i < fleet.length; i++) {
    if(fleet[i].weeklyRateInUSD <= n) {
      eligibleVehicles.push(fleet[i])
    }
  }
  return eligibleVehicles;
}
```
##### !end-answer
### !end-challenge





<!-- QUESTION #8 -->

### !challenge
* type: code-snippet
* language: javascript
* id: 07b4e92c-dcb8-4e60-ab76-f895bd6b8914
* title: Write the Function
* topics: Functions
##### !question
Write a function `efficiencyFilter()` that takes an array of cars, `fleet`, and returns an array of the vehicles that have a fuel efficiency, `milesPerGallon`, greater than 35.
##### !end-question
##### !placeholder
```js
function efficiencyFilter(fleet) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testFleet = [
    {
       make: "Hyundai",
       model: "Veracruz",
       year: "2007",
       milesPerGallon: 20,
       type: "SUV",
       dailyRateInUSD: 50,
       weeklyRateInUSD: 300
    },
    {
       make: "Volkswagen",
       model: "Jetta",
       year: "2019",
       milesPerGallon: 31,
       type: "Compact",
       dailyRateInUSD: 48,
       weeklyRateInUSD: 300
    },
    {
       make: "Toyota",
       model: "4Runner",
       year: "2020",
       milesPerGallon: 16,
       type: "SUV",
       dailyRateInUSD: 75,
       weeklyRateInUSD: 495
    },
    {
       make: "Toyota",
       model: "Prius",
       year: "2020",
       milesPerGallon: 40,
       type: "Compact",
       dailyRateInUSD: 80,
       weeklyRateInUSD: 500
    },
]

const result = efficiencyFilter(testFleet)

describe('efficiencyFilter', function() {
  it("returns an array", function() {
    expect(Array.isArray(result)).to.deep.eq(true)
  })
  it("returns the correct array", function() {
    expect(result.length).to.deep.eq(1)
    expect(result[0].milesPerGallon > 35).to.deep.eq(true)
    expect(result[0].model).to.deep.eq("Prius")
  })
})
```
##### !end-tests
### !end-challenge



<!-- QUESTION #9 -->

### !challenge
* type: multiple-choice
* id: e97985a8-ede5-49fd-8007-92cb94a7f139
* title: Identify the Bug
* topics: Word problems
##### !question
We're writing a function to help us organize a fleet of vehicles. We want to categorize a location's vehicles by their `manufacturer` and their `make`, but our current mechanism groups each vehicle individually. Can you identify what the bug is?

```js
function sortByMake(fleet){
  let organizedByMake = {}

  for(let i = 0; i < fleet.length; i) {
    if(organizedByMake[fleet[i].make]) {
      organizedByMake[fleet[i].make].push(fleet[i])
    } else {
      organizedByMake[fleet[i].make] = []
      organizedByMake[fleet[i].make].push(fleet[i])
    }
  }
  return organizedByMake
}
```
##### !end-question
##### !options
* Incorrectly defined variable
* Missing `return`
* Returns wrong value
* Missing `}` at end of for loop
* Infinite loop
##### !end-options
##### !answer
* Infinite loop
##### !end-answer
### !end-challenge




<!-- QUESTION #10 -->

### !challenge
* type: code-snippet
* language: javascript
* id: 0f9266f3-4ed0-4ef7-8930-e044dfb4ad66
* title: Write the Function
* topics: Iteration, Working with objects, Word problems
##### !question
Headquarters has decided to restructure the way fleets are organized. Rather
than placing the entire fleet in one garage, there will be a garage for each
vehicle type at every location.

Write a function, `fleetOrganizer()`, that:
1. Accepts an array of vehicle types, `vehicleTypes`
1. Accepts a fleet array of car objects, `fleet`
1. Returns a new object whose properties represent arrays with each of the
   passed-in vehicle types
1. If there is a vehicle `type` in the fleet that is not in the `vehicleTypes`
   array, gather them in an array stored at key `Other` on the return object

   _(*Note that `Other` is capitalized, like the other types)_

```js
const types = ["SUV", "Compact"];

const fleet = [
  {
   make: "Porsche",
   model: "Cayenne",
   year: "2021",
   milesPerGallon: 19,
   type: "SUV",
   dailyRateInUSD: 125,
   weeklyRateInUSD: 700
 },
  {
   make: "Toyota",
   model: "Prius",
   year: "2020",
   milesPerGallon: 40,
   type: "Compact",
   dailyRateInUSD: 80,
   weeklyRateInUSD: 500
 },
];

fleetOrganizer(types, fleet);

/*
Example output where each car is a car object from the fleet array:
{
  SUV: [{car1}, {car2}],
  Compact: [{car3}],
  Other: [{car4}, {car5}]
}
*/
```
##### !end-question
##### !placeholder
```js
function fleetOrganizer(vehicleTypes, fleet) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js

const testFleet = [
      {
         make: "Hyundai",
         model: "Veracruz",
         year: "2007",
         milesPerGallon: 20,
         type: "SUV",
         dailyRateInUSD: 50,
         weeklyRateInUSD: 300
      },
      {
         make: "Toyota",
         model: "Jetta",
         year: "2019",
         milesPerGallon: 31,
         type: "Compact",
         dailyRateInUSD: 48,
         weeklyRateInUSD: 300
      },
      {
         make: "Toyota",
         model: "4Runner",
         year: "2020",
         milesPerGallon: 16,
         type: "SUV",
         dailyRateInUSD: 75,
         weeklyRateInUSD: 495
      },
      {
         make: "Porsche",
         model: "Cayenne",
         year: "2021",
         milesPerGallon: 19,
         type: "SUV",
         dailyRateInUSD: 125,
         weeklyRateInUSD: 700
      },
      {
       make: "Toyota",
       model: "Prius",
       year: "2020",
       milesPerGallon: 40,
       type: "Compact",
       dailyRateInUSD: 80,
       weeklyRateInUSD: 500
    },
      {
       make: "Chevrolet",
       model: "Nova",
       year: "1980",
       milesPerGallon: 10,
       type: "Sedan",
       dailyRateInUSD: 420,
       weeklyRateInUSD: 500
    }
  ]

describe('fleetOrganizer', function() {
  it("returns an object", function() {
  let result = fleetOrganizer(["SUV"], testFleet )
    expect(typeof result).to.deep.eq("object")
  })

  it("returns the expected object", function() {
    let result = fleetOrganizer(["SUV", "Compact", "Sedan"], testFleet)

    expect(result.SUV.length).to.deep.eq(3)
    expect(result.Compact.length).to.deep.eq(2)
  })

  it(`should return an array of the "Other" cars when their types are not specified`, () => {
    let result = fleetOrganizer(["SUV"], testFleet)

    expect(result.SUV.length).to.deep.eq(3)
    expect(result.Other.length).to.deep.eq(3)
  })

  it(`Should not include an "Other" property if all vehicle types are passed in`, () => {
    let result = fleetOrganizer(["SUV", "Sedan", "Compact"], testFleet)

    expect(result.hasOwnProperty('Other')).to.deep.eq(false)
  })
})
```
##### !end-tests
### !end-challenge





<!-- SCENARIO E -->

<!-- QUESTION #11 -->
### !challenge
* type: multiple-choice
* id: f5f942c4-7933-47e6-a3eb-82c24af88876
* title: Data Type Identification
* topics: Data Types
##### !question
Which of the following is a correctly instantiated variable?
##### !end-question
##### !options
* `plant = "cactus"`
* `plant = "cactus"`
* `var plant = "cactus"`
* `cactus = "plant"`
* `var "plant" = "cactus"`
##### !end-options
##### !answer
* `var plant = "cactus"`
##### !end-answer
### !end-challenge




<!-- QUESTION #12 -->
### !challenge
* type: code-snippet
* language: javascript
* id: 8620b822-049a-4c6f-8530-efe55cc39608
* title: Write the Function
* topics: Functions
##### !question
Write a function that takes in a `plant` object that looks like this:
```js
{
  name: "fern",
  waterLevel: 4,
  color: "green",
  heightInInches: 14,
  sunExposure: 44,
  price: 12
}
```
and returns a string `"The <name> costs $<price>."`.
##### !end-question
##### !placeholder
```js
function priceChecker(plant) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('priceChecker', function() {
    it("returns a string", function() {
        let plant = { name: "fern", price: 12 }
        expect(typeof (priceChecker(plant))).to.deep.eq("string")
    })
    it("returns a properly formatted string", function() {
        let plant = { name: "fern", price: 12 }
        expect(priceChecker(plant)).to.deep.eq("The fern costs $12.")
    })
})
```
##### !end-tests
### !end-challenge


<!-- QUESTION #13 -->
### !challenge
* type: multiple-choice
* id: b2e919ab-f95a-4c5e-ac49-eea8223b9238
* title: Select the Logical Operators
* topics: Operators
##### !question
Which of the following returns `true` for a fiddle leaf OR a spider plant?
##### !end-question
##### !options
* `if(plant.name = "fiddle leaf" || plant.name = "spider plant") {return true}`
* `if(plant.name === "fiddle leaf" || plant.name === "spider plant") {return true}`
* `if(plant.name === "fiddle leaf" &| plant.name === "spider plant") {return true}`
* `if(plant.name === "fiddle leaf" && plant.name === "spider plant") {return true}`
* `if(plant.name = "fiddle leaf" & plant.name = "spider plant") {return true}`
##### !end-options
##### !answer
* `if(plant.name === "fiddle leaf" || plant.name === "spider plant") {return true}`
##### !end-answer
### !end-challenge



<!-- QUESTION #14 -->

### !challenge
* type: code-snippet
* language: javascript
* id: 17c30159-1cb3-4678-86be-bc2710a2d802
* title: Write the Function
* topics: Iteration
##### !question
The ideal sun exposure for a plant is a level 7. Write a function that takes in
an `inventory` array and a string `plantName`. This function
- Returns `"Needs more sun"` if an input plant’s current sun exposure is under a 7
- Returns `"Too much sun exposure"` if its level is over 7
- Returns  `"Sun exposure achieved"` if sun exposure level is currently a 7

Example:
```js
const inventory = [
        { name: "olive tree", price: 15, quantity: 17, sunExposure: 5 },
        { name: "sun flower", price: 3, quantity: 8, sunExposure: 9 },
        { name: "tulip", price: 9, quantity: 21, sunExposure: 7 },
        { name: 'rhododendron', price: 43, quantity: 68, sunExposure: 10 }
    ]

sunExposureAdjuster(inventory, 'rhododendron') // "Too much sun exposure!"
```

##### !end-question
##### !placeholder
```js
function sunExposureAdjuster(inventory, plantName) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('sunExposureAdjuster', function() {
    const inventory = [
        { name: "olive tree", price: 15, quantity: 17, sunExposure: 5 },
        { name: "sun flower", price: 3, quantity: 8, sunExposure: 9 },
        { name: "tulip", price: 9, quantity: 21, sunExposure: 7 },
    ]
    it("returns a string", function() {
        expect(typeof sunExposureAdjuster(inventory, "tulip")).to.deep.eq("string")
    })
    it("returns 'Too much sun exposure' if a plant's sunExposure is greater than 7", function() {
        expect(sunExposureAdjuster(inventory, "sun flower")).to.deep.eq('Too much sun exposure')
    })
    it("returns 'Needs more sun' if a plant's sunExposure is less than 7", function() {
        expect(sunExposureAdjuster(inventory, "olive tree")).to.deep.eq('Needs more sun')
    })
    it("returns 'Sun exposure achieved' if a plant's sunExposure is 7", function() {
        expect(sunExposureAdjuster(inventory, "tulip")).to.deep.eq('Sun exposure achieved')
    })
})
```
##### !end-tests
### !end-challenge



<!-- QUESTION #15 -->
### !challenge
* type: multiple-choice
* id: 156135d5-bcab-46fe-8e8c-2830b345198e
* title: Select the Function
* topics: Iteration, Conditionals
##### !question
Given the following item from our greenhouse, choose the function that would craft a message indicating whether the plant needs a soil update. Our example plant looks like this:

```js
const peony = {
  name: "peony",
  price: 8,
  quantity: 25,
  soilUpdateNeeded: true
}
```
##### !end-question
##### !options
* `if(peony.soilUpdateNeeded) { return "Soil Update Needed" }`
* `if(soilUpdateNeeded = true) { return "Soil Update Needed" }`
* `return "Soil Update Needed" if (peony.soilUpdateNeeded === true) }`
* `if(soilUpdateNeeded !== true) { return "Soil Update Needed" }`
##### !end-options
##### !answer
* `if(peony.soilUpdateNeeded) { return "Soil Update Needed" }`
##### !end-answer
### !end-challenge


<!-- QUESTION #16 -->
### !challenge
* type: code-snippet
* language: javascript
* id: 171c638c-c7dd-4ec3-990a-f076d65a2f80
* title: Write the Function
* topics: Iteration
##### !question
Our greenhouse currently grows a variety of different types of plants from seeds! We just received a shipment where we got 5 packets of each type of seed we're currently growing.

Please write a function that takes in an `inventory` array, increases each seed’s `quantity` by 5, and returns an array of the updated inventory. Our `inventory` looks like this:

`const seedInventory = [{ name: "seed name", price: priceNumber, quantity: quantityNumber}, ...]`
##### !end-question
##### !placeholder
```js
function inventoryUpdater(inventory) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('inventoryUpdater', function() {
    it("returns an object", function() {
        let inventory = [
            { name: "peony", price: 4, quantity: 11 },
            { name: "tomato", price: 3, quantity: 32 },
            { name: "maple tree", price: 5, quantity: 20 },
            { name: "poppy", price: 3, quantity: 14 },
        ]
        expect(typeof inventoryUpdater(inventory)).to.deep.eq("object")
    })
    it("updates each item in the inventory's quantity by 5", () => {
        let inventory = [
            { name: "peony", price: 4, quantity: 11 },
            { name: "tomato", price: 3, quantity: 32 },
            { name: "maple tree", price: 5, quantity: 20 },
            { name: "poppy", price: 3, quantity: 14 },
        ]
        let result = inventoryUpdater(inventory)
        expect(result.length).to.deep.eq(4)
        expect(result[0].quantity).to.deep.eq(16)
        expect(result[1].quantity).to.deep.eq(37)
        expect(result[2].quantity).to.deep.eq(25)
        expect(result[3].quantity).to.deep.eq(19)
    })
})
```
##### !end-tests
### !end-challenge


<!-- QUESTION #17 -->
### !challenge
* type: multiple-choice
* id: c27859c9-8a10-4862-afa4-7ebe14c45232
* title: Select the Function
* topics: Iteration, Working with objects
##### !question
The greenhouse manager needs information about our current plants. Please select the function that would iterate over our `inventory` array and return an array of objects, one for each item in our inventory, that indicates the name and number of items that need to be ordered to get the quantity up to 50.

Inventory looks like:
`const inventory = [{ name: "peony", price: 8, quantity: 25}, ...]`

And the returned collection would look like:
`const inventoryNeeded = [{ name: "peony", quantityToOrder: 25 }, ...]`
##### !end-question
##### !options
*
```js
const inventoryChecker = () => {
  for(let i = 0; i < inventory.length; i++) {
    if(inventory[i].quantity < 50) {
      inventoryNeeded.push({ name: inventory[i].name, quantityToOrder: 50 - inventory[i].quantity})
    }
  }
  return inventoryNeeded
}
```
*
```js
const inventoryChecker = (inventory) => {
  let inventoryNeeded = []

  for(let i = 0; i < inventory.length; i++) {
    if(inventory[i].quantity < 50) {
      inventoryNeeded.push({ name: inventory[i].name, quantityToOrder: 50 - inventory[i].quantity})
    }
  }
  return inventoryNeeded
}
```
*
```js
const inventoryChecker = (inventory) => {
  let inventoryNeeded = []

  for(let i = 0; i < inventory.length; i++) {
    if(inventory[i].quantity < 50) {
      inventoryNeeded.push({ name: inventory[i].name, quantityToOrder: 50 - inventory[i].quantity})
    }
  }
}
```
*
```js
const inventoryChecker = () => {
  for(let i = 0; i < inventory.length; i++) {
    if(inventory[i].quantity <= 50) {
      inventoryNeeded.push({ quantityToOrder: 50 - inventory[i].quantity})
    }
  }
  return inventoryNeeded
}
```
##### !end-options
##### !answer
```js
const inventoryChecker = (inventory) => {
  let inventoryNeeded = []

  for(let i = 0; i < inventory.length; i++) {
    if(inventory[i].quantity < 50) {
      inventoryNeeded.push({ name: inventory[i].name, quantityToOrder: 50 - inventory[i].quantity})
    }
  }
  return inventoryNeeded
}
```
##### !end-answer
### !end-challenge




<!-- QUESTION #18 -->
### !challenge
* type: code-snippet
* language: javascript
* id: ba799757-bf6e-4ae2-b58e-ef18c6cdbad3
* title: Write the Function
* topics: Iteration, Working with objects
##### !question
Given the following `inventory`, write a function, `waterLevelAdjuster()`, that will increase each plant’s water level to 100 if it is less than 100, and return a list of objects recording the names of the plants that required water and how much water they required, stored as the property `waterRequired`.

If the inventory looks like:
```js
const inventory = [
    { name: "palm tree", price: 80, quantity: 12, waterLevel: 100 },
    { name: "pine tree", price: 109, quantity: 291, waterLevel: 100 },
    { name: "maple tree", price: 92, quantity: 93, waterLevel: 73 },
    { name: "aspen tree", price: 89, quantity: 44, waterLevel: 33 },
]
```
The returned array and objects should look like this:
```js
[
  { name: "maple tree", waterRequired: 27 },
  { name: "aspen tree", waterRequired: 67 }
]
```
##### !end-question
##### !placeholder
```js
function waterLevelAdjuster(inventory) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('waterLevelAdjuster', function() {
    it("returns an array", function() {
      const inventory = [
          { name: "palm tree", price: 80, quantity: 12, waterLevel: 100 },
          { name: "pine tree", price: 109, quantity: 291, waterLevel: 100 },
          { name: "maple tree", price: 92, quantity: 93, waterLevel: 73 },
          { name: "aspen tree", price: 89, quantity: 44, waterLevel: 33 },
      ]
        expect(Array.isArray(waterLevelAdjuster(inventory))).to.deep.eq(true)
    })
    it("returns an array where all waterLevels are increased to 100", function() {
        const inventory = [
          { name: "palm tree", price: 80, quantity: 12, waterLevel: 100 },
          { name: "pine tree", price: 109, quantity: 291, waterLevel: 100 },
          { name: "maple tree", price: 92, quantity: 93, waterLevel: 73 },
          { name: "aspen tree", price: 89, quantity: 44, waterLevel: 33 },
        ]
        let result = waterLevelAdjuster(inventory)
        expect(result[0].name).to.deep.eq("maple tree")
        expect(result[0].waterRequired).to.deep.eq(27)
        expect(result[1].name).to.deep.eq("aspen tree")
        expect(result[1].waterRequired).to.deep.eq(67)
    })
})
```
##### !end-tests
### !end-challenge


<!-- QUESTION #19 -->
### !challenge
* type: multiple-choice
* id: a526e495-a60f-47c4-b3aa-ba59fb994437
* title: Find the Bug
* topics: Word problems
##### !question
We own 5 greenhouses. We have a lot of plants that need to be pruned!

Every time we prune the plants, we update our inventory to reflect their `pruneNeeded` status from `true` to `false`. When we prune, we prune all of the plants at once that need to be pruned at one greenhouse, and then move on to the next greenhouse.

Our program returns our updated inventories after we have pruned all plants at all greenhouses who need it, but it isn’t working correctly. Please select the phrase that correctly describes what the error is.

The inventory looks like this:
```js
const totalGreenhouseInventories = {
  greenhouse1: [
    { name: "olive tree", price: 43, quantity: 92, waterLevel: 100, pruneNeeded: true },
    { name: "begonia", price: 17, quantity: 38, waterLevel: 100, pruneNeeded: false },
  ],
  greenhouse2: [{}, {}],
  ...
}
```

```js
const pruneNeededAdjuster = (totalGreenhouseInventories) => {
    for(let greenhouse in totalGreenhouseInventories) {
      for(let i = 0; i < totalGreenhouseInventories[greenhouse].length; i++) {
          if(totalGreenhouseInventories[greenhouse][i].pruneNeeded) {
              totalGreenhouseInventories[greenhouse][i].pruneNeeded = false;
          }
      }
    }
  yield totalGreenhouseInventories;
}
```
##### !end-question
##### !options
* Incorrectly defined variable
* Missing `return`
* Iteration error
* Missing `}` at end of for loop
* Infinite loop
##### !end-options
##### !answer
* Missing `return`
##### !end-answer
### !end-challenge


<!-- QUESTION #20 -->
### !challenge
* type: code-snippet
* language: javascript
* id: 5709a868-f66c-4017-bf42-e6df347079e1
* title: Write the Function
* topics: Word problems, Working with objects, Iteration
##### !question
Our inventory is a mess. Everything is in one big array, `inventory`, and we’d like to break it into categories so it’s easier to navigate.

To help with the reorganization, we've made sure every individual plant in the `inventory` has a `type`, which it will now be categorized by. Right now, it looks like this:

```js
const inventory = [
    { name: "dahlia", price: 12, quantity: 100, type: "flower"},
    { name: "fern", price: 10, quantity: 72, type: "shrub" },
...]
```
Note the new `type` property on each plant. We’d like the inventory rearranged to match the following format, where the keys in the object are the type of plant and the value is an array of all plants who match that plant type:

```js
const inventory = {
    flower:  [
        { name: "dahlia", price: 12, quantity: 100, type: "flower"},
    ...],
    shrub: [
        { name: "fern", price: 10, quantity: 72, type: "shrub" },
    ...]
}
```
##### !end-question
##### !placeholder
```js
function inventoryReformatter(inventory) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
describe('inventoryReformatter', function() {
    it("returns an object", function() {
      let inventory = [
          { name: "dahlia", price: 12, quantity: 100, type: "flower"},
          { name: "fern", price: 10, quantity: 72, type: "shrub" },
          { name: "tulip", price: 4, quantity: 5, type: "flower" }
      ]
      expect(typeof inventoryReformatter(inventory)).to.deep.eq("object")
    })
    it("reformats the inventory to an object with keys for plant types", function() {
        let inventory = [
          { name: "dahlia", price: 12, quantity: 100, type: "flower"},
          { name: "fern", price: 10, quantity: 72, type: "shrub" },
          { name: "tulip", price: 4, quantity: 5, type: "flower" }
        ]
        let result = inventoryReformatter(inventory)
        expect(result.flower.length === 2)
        expect(result.flower[0].name === "dahlia")
        expect(result.flower[0].type === "flower")

        expect(result.flower[1].name === "tulip")
        expect(result.flower[1].type === "flower")

        expect(result.shrub.length === 1)
        expect(result.shrub[0].name === "fern")
        expect(result.shrub[0].type === "shrub")
    })
})
```
##### !end-tests
### !end-challenge









<!-- SCENARIO F -->

<!-- QUESTION #21 -->
### !challenge
* type: multiple-choice
* id: 9a3c51c8-14b2-47d3-bb8a-8098425be7e8
* title: Data Type Identification
* topics: Data Types
##### !question
The below variable is assigned to which data type?

```js
let dragon;
```
##### !end-question
##### !options
* null
* undefined
* number
* string
* boolean
* symbol
##### !end-options
##### !answer
* undefined
##### !end-answer
### !end-challenge


<!-- QUESTION #22 -->
### !challenge
* type: code-snippet
* language: javascript
* id: d6b77955-0bce-4b4b-af5e-5d3f73d1ca9d
* title: Write the Function
* topics: Functions
##### !question
Write a function, `joinPartyAnnouncer()` that accepts a parameter called `character` and returns the string `"<character.name> the <character.type> joined the party!"` if passed a character object like the one shown below:
```js
const character = {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  };
```
##### !end-question
##### !placeholder
```js
 function joinPartyAnnouncer(character) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Sir Duncan",
    type: "Knight",
    inventory: ["sword", "shield"],
    partyName: "Knights of the Square Table",
    gold: 300,
  },
  {
    name: "Artemis",
    type: "Hunter",
    inventory: ["bow"],
    partyName: "The Classicists",
    gold: 25,
  },
];

describe('joinPartyAnnouncer', function() {

it("returns a string", function() {
    let result = joinPartyAnnouncer(testParty[0])
    expect(typeof result).to.deep.eq("string")
})
it("returns the correct string for the input character", function() {
    let result = joinPartyAnnouncer(testParty[1]);
    let expected = "Sir Duncan the Knight joined the party!";
expect(result).to.deep.eq(expected)
})
})
```
##### !end-tests
### !end-challenge

<!-- QUESTION #23 -->
### !challenge
* type: multiple-choice
* id: c34a8734-471a-459e-8e9d-924f848b8103
* title: Select the Logical Operators
* topics: Operators
##### !question
In this particular fantasy setting, characters each have their own specialization (like `"Bard"` or `"Paladin"`) stored at a property called `type`, such as on the example character below:
```js
const character = {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  };
```
Which of the following would evaluate to true if a character's type is _neither_
a `"Bard"` _nor_ a `"Knight"`?

##### !end-question
##### !options
* character.type !== "Bard" || "Knight"
* character.type !== "Bard" OR "Knight"
* character == "Bard" || character.type == "Knight"
* character.type !== "Bard" || character.type !== "Knight"
* character.type =! "Bard" || character.type =! "Knight"
##### !end-options
##### !answer
* character.type !== "Bard" || character.type !== "Knight"
##### !end-answer
### !end-challenge

<!-- QUESTION #24 -->
### !challenge
* type: code-snippet
* language: javascript
* id: 83dd9796-5674-462e-ba44-f594b0c8f89b
* title: Write the Function
* topics: Functions, Conditionals, Operators
##### !question
Write a function that takes an array of characters (`party`) and a string representing a character type, `characterType`, and returns one of two things: either the  string `"This party has a <characterType> in it"` or `"This party doesn't have a <characterType> in it"`, depending on if the party contains at least one character whose type matches the input `characterType`.

A party looks like this:
```js
[
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Garric",
    type: "Barbarian",
    inventory: ["axe", "bigger axe"],
    partyName: "Clan of the Cave Squirrel",
    gold: 300,
  }
]
```

##### !end-question
##### !placeholder
```js
 function partyContains(party, characterType) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Sir Duncan",
    type: "Knight",
    inventory: ["sword", "shield"],
    partyName: "Knights of the Square Table",
    gold: 300,
  },
  {
    name: "Artemis",
    type: "Hunter",
    inventory: ["bow"],
    partyName: "The Classicists",
    gold: 25,
  },
];

describe('partyContains', function() {

const falseResult = partyContains(testParty, "Squire")
const successResult = partyContains(testParty, "Knight")

  it("returns a string", function() {
    expect(typeof successResult).to.deep.eq("string")
    expect(typeof falseResult).to.deep.eq("string")
  })

  it("returns the correct string no match found", function() {
    const expected = "This party doesn't have a Squire in it";
    expect(falseResult===expected).to.deep.eq(true)
  })

  it("returns the correct string if a match is found", function() {
    const expected = "This party has a Knight in it";
    expect(successResult===expected).to.deep.eq(true)
  })
})
```
##### !end-tests
### !end-challenge

<!-- QUESTION #25 -->
### !challenge
* type: multiple-choice
* id: 2854f584-4262-4c29-ad38-5760839d3f0a
* title: Select the Function
* topics: Word problems, Iteration, Working with objects
##### !question
Our party earned some gold saving a town from a dragon - now we need to split it up evenly between the members of the party!  These are classic big heavy gold coins, so they can't be divided - that means that every party member can only receive a _whole number_ of coins - not decimals or fractional amounts.

The `goldAmount` should be split equally among party members. Disregard any remainder as you can't divide coins.  The party have decided to donate any remainders to the local town council to help repair the dragon damage.

Which of these functions correctly takes an array of characters (`party`) and a number (`goldAmount`) and distributes the gold equally between the members of the party?
##### !end-question
##### !options
*
```js
function shareGold(party, goldAmount){
    goldAmount = goldAmount%party.length;
    let share = goldAmount/party.length;

    for (let i = 0; i<party.length; i++){
        party[i].gold += share;
    }

    return party;
}
```
*
```js
function shareGold(party, goldAmount){
    goldAmount -= goldAmount%party.length;
    let share = goldAmount/party.length;

    for (let i = 0; i<party.length; i++){
        party[i].gold += share;
    }

    return party;
}
```
*
```js
function shareGold(party, goldAmount){
    goldAmount -= goldAmount%party.length;

    for (let i = 0; i<party.length; i++){
        party[i].gold += goldAmount;
    }

    return party;
}
```
*
```js
function shareGold(party, goldAmount){
    goldAmount -= goldAmount%party.length;
    let share = goldAmount/party.length;

    for (let i = 0; i<party.length; i++){
        party.gold += share;
    }

    return party
}
```
##### !end-options
##### !answer
```js
function shareGold(party, goldAmount){
    goldAmount -= goldAmount%party.length;
    let share = goldAmount/party.length;

    for (let i = 0; i<party.length; i++){
        party[i].gold += share;
    }

    return party;
}
```
##### !end-answer
### !end-challenge

<!-- QUESTION #26 -->
### !challenge
* type: code-snippet
* language: javascript
* id: bbcc70ae-ddc3-4b52-ba81-4148096c39d0
* title: Write the Function
* topics: Iteration, Working with objects
##### !question
Our party is ready to start a new Quest!

Everyone knows that any self-respecting group of adventurers _has_ to have a cool name before they can do any questing, though!

Write a function, `partyNameSetter()`, that takes two arguments: an array of characters, `party`, and a string, `partyName`. Write a function that returns the input `party` array with each character's `partyName` property set to the cool new name.
##### !end-question
##### !placeholder
```js
 function partyNameSetter(party, partyName) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Sir Duncan",
    type: "Knight",
    inventory: ["sword", "shield"],
    partyName: "Knights of the Square Table",
    gold: 300,
  },
  {
    name: "Artemis",
    type: "Hunter",
    inventory: ["bow"],
    partyName: "The Classicists",
    gold: 25,
  },
];

let result = partyNameSetter(testParty, "The NPCs")

describe('partyNameSetter', function() {

it("returns an array", function() {
expect(Array.isArray(result)).to.deep.eq(true)
})

it("returns an array of characters", function() {
    let expectation = result[0].name === "Jeffie"
    let allObjects = result.map(char=>typeof char).every(type => type === "object")
    expect(expectation).to.deep.eq(true)
    expect(result.length).to.deep.eq(3)
})

it("sets all characters' partyName correctly", function() {
    let partyNamesArray = result.reduce((list, char)=>{
        if (!list.includes(char.partyName)) list.push(char.partyName)
        return list;
    },[])
expect(partyNamesArray.length).to.deep.eq(1)
expect(partyNamesArray[0]).to.deep.eq("The NPCs")
})

})
```
##### !end-tests
### !end-challenge

<!-- QUESTION #27 -->
### !challenge
* type: multiple-choice
* id: f24e5749-d358-4014-8e0d-e528ca6b0396
* title: Select the Function
* topics: Iteration, Working with objects
##### !question
We've come to a locked door! From the list below, locate the function that correctly:
* takes in an array of characters (`party`)
* checks to see if any character in the party has a `"key"` in their `inventory` array
* removes the key and returns the string `"Door unlocked"` if a key is found
* returns the string `"Key required"` if no key is found

Which of the below functions is the correct one?
##### !end-question
##### !options
*
```js
function findKey(party) {
  for (let i = 0; i < party.length; i++) {
    const character;

    for (let j = 0; j < character.inventory.length; j++) {
      const item = character.inventory[j];
      if (item === "key") {
        character.inventory.splice(j, 1);
        return "Door unlocked";
      }
    }
  }
  return "Key required";
}
```
*
```js
function findKey(party) {
  for (let i = 0; i < party.length; i++) {
    const character = party[i];

    for (let j = 0; j < character.inventory.length; j++) {
      const item = character.inventory[j];
      if (item === "key") {
        character.inventory.splice(j, 1);
        return "Door unlocked";
      }
    }
    return "Key required";
  }
}
```
*
```js
function findKey(party) {
  for (let i = 0; i < party.length; i++) {
    const character = party[i];

    for (let j = 0; j < character.inventory.length; j++) {
      const item = character.inventory[j];
      if (item === "key") {
        character.inventory.splice(j, 1);
        return "Door unlocked";
      }
    }
  }
  return "Key required";
}
```
*
```js
function findKey(party) {
  for (let i = 0; i < party.length; i++) {
    const character = party[i];

    for (let j = 0; j < character.inventory.length; j++) {
      const item = character.inventory[j];
      if (item === "key") {
        return "Door unlocked";
      }
    }
  }
  return "Key required";
}
```
##### !end-options
##### !answer
```js
function findKey(party) {
  for (let i = 0; i < party.length; i++) {
    const character = party[i];

    for (let j = 0; j < character.inventory.length; j++) {
      const item = character.inventory[j];
      if (item === "key") {
        character.inventory.splice(j, 1);
        return "Door unlocked";
      }
    }
  }
  return "Key required";
}
```
##### !end-answer
### !end-challenge

<!-- QUESTION #28 -->
### !challenge
* type: code-snippet
* language: javascript
* id: c103c4c8-268c-4f15-a444-71f81192437d
* title: Write the Function
* topics: Iteration, Working with objects
##### !question
No quest is complete without a few monsters!  Monsters are weak to one or more character types:
```js
    const dragon = {
    type: "dragon",
    defeatedBy: [`Wizard`],
    };
```
A monster can only be defeated by a party that contains a character of that class.

Write function `championSelector()` that takes an array of characters, `party`, and an object, `monster`, and returns an array of _only those members of the party_ whose `type` matches _any_ of the types in the `monster`'s `defeatedBy` property array.
##### !end-question
##### !placeholder
```js
    function championSelector(party, monster) {
    // YOUR CODE HERE

    }
```
##### !end-placeholder
##### !tests
```js
const testParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Sir Duncan",
    type: "Knight",
    inventory: ["sword", "shield", "key"],
    partyName: "Knights of the Square Table",
    gold: 300,
  },
  {
    name: "Artemis",
    type: "Hunter",
    inventory: ["bow"],
    partyName: "The Classicists",
    gold: 25,
  },
];

const dragon = {
  type: "dragon",
  defeatedBy: [`Wizard`],
};

const gargoyle = {
    type: "gargoyle",
    defeatedBy: ["Knight"],
}

const spectre = {
    type: "spectre",
    defeatedBy: ["Hunter", "Bard"],
}

describe('championSelector', function() {

it("returns an array", function() {
    const result = championSelector(testParty, dragon)
    expect(Array.isArray(result)).to.deep.eq(true)
})

it("returns an empty array in the case of no matches are found", function() {
    const result = championSelector(testParty, dragon)
    const expectation = Array.isArray(result) && result.length===0;
    expect(expectation).to.deep.eq(true)
})

it("returns the correct array if a single match is found", function() {
    const result = championSelector(testParty, gargoyle)

    expect(result.length).to.deep.eq(1)
    expect(result[0].name).to.deep.eq("Sir Duncan");
})

it("returns the correct array if multiple matches are found", function() {
    const result = championSelector(testParty, spectre)
    expect(result.length).to.deep.eq(2);
    expect(result[0].name).to.deep.eq("Jeffie");
    expect(result[1].name).to.deep.eq("Artemis");
})
})
```
##### !end-tests
### !end-challenge

<!-- QUESTION #29 -->
### !challenge
* type: multiple-choice
* id: 5a2465f8-523e-4ff3-9c44-89a0a6b9ebfd
* title: Identify the Bug
* topics: Word problems
##### !question
The King of S'di, grateful that we helped rid his castle of enchanted statues, has given us a bunch of items he had lying around his castle as a reward!  There's a lot of random stuff here, so to make it fair, we've decided to take turns pulling things out of the loot bag one at a time until it's all distributed.  We tried, but something's going wrong!

The following `distributeLoot` function takes in an array of characters (`party`) and an array of loot (`hoard`) and should distribute (i.e. it should end up in their `inventory` property array) the first item in the hoard to the first character in the party, the second item to the second character, and so on until everyone has gotten one item.  Then, if some items still haven't been distributed, it should continue to distribute items in the same character order as before, and so forth until all items have been distributed.  Then it should return the party.

Here's the `distributeLoot()`function - identify what's wrong with it and select the phrase that best describes the problem below:
```js
  function distributeLoot(party, hoard) {
    for (let i = 0; i < hoard.length; i++) {
      for (let j = 0; j < party.length; j++) {
        if (i % party.length === j) {
          party[j].inventory.push(hoard[i]);
        }
    }
    return party;
  }
```
##### !end-question
##### !options
* Incorrectly defined variable
* Missing `return`
* Iteration error
* Missing `}` at end of for loop
* Infinite loop
##### !end-options
##### !answer
* Missing `}` at end of for loop
##### !end-answer
### !end-challenge

<!-- QUESTION #30 -->
### !challenge
* type: code-snippet
* language: javascript
* id: db3c817f-4433-4637-9841-c1fd4e2fe50c
* title: Write the Function
* topics: Working with objects, Iteration, Word problems
##### !question
Write a function `questAssessment()` that takes array of characters (`party`) and an an object (`quest`) which has a `monsters` property and a `lockedDoors` property, such as in the examples below:

```js
const exampleQuest = {
  lockedDoors: 2,
  monsters: [
    { type: "dragon", defeatedBy: ["Wizard"] },
    { type: "spectre", defeatedBy: ["Hunter", "Bard"] },
  ],
};

const exampleParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Biff",
    type: "Druid",
    inventory: ["staff"],
    partyName: "The Accordion Fire",
    gold: 225,
  }
]
```

A quest can be completed only if:
* all of the locked doors can be unlocked _AND_
* all the monsters can be defeated

So, in the example above, a party would need 2 `"key"` entries in their inventories _and_ would have to include a Wizard type character _as well as_ either a `"Bard"` or a `"Hunter"` type character.

Your function should check these things and return one of three possible messages, depending on the circumstances:

* `"Find more keys"` if the party doesn't have enough keys
* `"Make more new friends first"` if the party's character _do have_ enough `"key"`s in their combined inventories, _but the party doesn't contain_ at least one character whose type matches one of _each_ of the monsters' `defeatedBy` types
* `"We've got this!"` if the characters _BOTH_ have enough keys and the party contains at least one character whose class that matches at least one of each of the monsters' `defeatedBy` types.
##### !end-question
##### !placeholder
```js
 function questAssessment(party, quest) {
// YOUR CODE HERE
}
```
##### !end-placeholder
##### !tests
```js
const testParty = [
  {
    name: "Jeffie",
    type: "Bard",
    inventory: ["lute"],
    partyName: "The Accordion Fire",
    gold: 50,
  },
  {
    name: "Sir Duncan",
    type: "Knight",
    inventory: ["sword", "shield", "key"],
    partyName: "Knights of the Square Table",
    gold: 300,
  },
  {
    name: "Artemis",
    type: "Hunter",
    inventory: ["bow"],
    partyName: "The Classicists",
    gold: 25,
  },
];
// Enough keys, but no type match
const questOne = {
  lockedDoors: 1,
  monsters: [
    {
      type: "dragon",
      defeatedBy: [`Wizard`],
    },
  ],
};
// Not enough keys, no type match
const questTwo = {
  lockedDoors: 12,
  monsters: [
    {
      type: "dragon",
      defeatedBy: [`Wizard`],
    },
  ],
};
// Not enough keys, all of multiple types matched
const questThree = {
  lockedDoors: 2,
  monsters: [
    {
      type: "spectre",
      defeatedBy: ["Hunter", "Bard"],
    },
    {
      type: "gargoyle",
      defeatedBy: ["Knight"],
    },
  ],
};

// enough keys, not all of multiple types matched
const questFour =  {
  lockedDoors: 1,
  monsters: [
    {
      type: "dragon",
      defeatedBy: [`Wizard`],
    },
    {
      type: "spectre",
      defeatedBy: ["Hunter", "Bard"],
    },
    {
      type: "gargoyle",
      defeatedBy: ["Knight"],
    },
  ],
};
// enough keys, all of multiple types matched
const questFive =
{
  lockedDoors: 1,
  monsters: [
    {
      type: "spectre",
      defeatedBy: ["Hunter", "Bard"],
    },
    {
      type: "gargoyle",
      defeatedBy: ["Knight"],
    },
  ],
};


const questOneResult = questAssessment(testParty, questOne); // "Make more new friends first"
const questTwoResult = questAssessment(testParty, questTwo); // "Find more keys"
const questThreeResult = questAssessment(testParty, questThree); // "Find more keys"
const questFourResult = questAssessment(testParty, questFour); // "Make more new friends first"
const questFiveResult = questAssessment(testParty, questFive); // "We've got this!"

describe('questAssessment', function() {
  it("should return a string", function() {
    expect(typeof questOneResult).to.deep.eq("string")
    expect(typeof questTwoResult).to.deep.eq("string")
    expect(typeof questThreeResult).to.deep.eq("string")
    expect(typeof questFourResult).to.deep.eq("string")
  })
  it("should identify if not enough keys", function() {
    expect(questTwoResult).to.deep.eq("Find more keys")
    expect(questThreeResult).to.deep.eq("Find more keys")
  })
  it("should identify missing keys before monster type matches", function() {
    expect(questTwoResult).to.deep.eq("Find more keys")
  })

  it("should identify monster type mismatches", function() {
    expect(questOneResult).to.deep.eq("Make more new friends first")
     expect(questFourResult).to.deep.eq("Make more new friends first")
  })

  it("should identify successes", function() {
    expect(questFiveResult).to.deep.eq("We've got this!")
  })
})
```
##### !end-tests
### !end-challenge

