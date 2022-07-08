# Accepted Solutions

## Question 10
```javascript
const fleetOrganizer = (vehicleTypes, fleet) => {
  const result = {};
  vehicleTypes.forEach(type => result[type] = []);

  fleet.forEach((car) => {
      const {type} = car;

      if (!result.hasOwnProperty(type)) {
          if (!result.hasOwnProperty('Other')) {
            result.Other = [car];
          } else {
            result.Other.push(car);
          }
      } else {
        result[type].push(car);
      }
  })

  return result;
}
```

## Question 14
```javascript
const correctSunLevel = 7;

const validateSunExposure = (level) => {
  if (level < correctSunLevel) {
    return 'Needs more sun';
  } else if (level > correctSunLevel) {
    return 'Too much sun exposure';
  }
  return 'Sun exposure achieved';
};

const sunExposureAdjuster = (inventory, plantName) => {
  return inventory.reduce((string, current) => {
    return current.name === plantName
      ? validateSunExposure(current.sunExposure)
      : string;
  }, '');
};
```