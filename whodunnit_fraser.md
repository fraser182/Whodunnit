# Scope Homework: Who Dunnit

### Learning Objectives

- Understand function scope
- Know the difference in between the let and const keywords

## Brief

Using your knowledge about scope and variable declarations in JavaScript, look at the following code snippets and predict what the output or error will be and why. Copy the following episodes into a JavaScript file and add comments under each one detailing the reason for your predicted output.

### MVP

#### Episode 1

```js
const scenario = {
  murderer: 'Miss Scarlet',
  room: 'Library',
  weapon: 'Rope'
};

const declareMurderer = function() {
  return `The murderer is ${scenario.murderer}.`;
}

const verdict = declareMurderer();
console.log(verdict);
// The murderer is Miss Scarlet
```

#### Episode 2

```js
const murderer = 'Professor Plum';
//murderer Prof Plum

const changeMurderer = function() {
  murderer = 'Mrs. Peacock';
}
// murderer Mrs Peacock
const declareMurderer = function() {
  return `The murderer is ${murderer}.`;
}

changeMurderer();
const verdict = declareMurderer();
console.log(verdict);
// ERROR Murderer is still Professor Plum but code will give error.
// const defined as murderer, so cant change it to Mrs. Peacock.
// set const murder as let murder for it to then be Mrs Peacock

```

#### Episode 3

```js
let murderer = 'Professor Plum';
// murderer = Prof Plum

const declareMurderer = function() {
  let murderer = 'Mrs. Peacock';
  return `The murderer is ${murderer}.`;
}
// declareMurderer = Mrs Peacock

const firstVerdict = declareMurderer();
console.log('First Verdict: ', firstVerdict);
// First Verdict calls declareMurderer = Mrs Peacock

const secondVerdict = `The murderer is ${murderer}.`;
console.log('Second Verdict: ', secondVerdict);

// Second Verdict: Professor Plum

```

#### Episode 4

```js
let suspectOne = 'Miss Scarlet';
let suspectTwo = 'Professor Plum';
let suspectThree = 'Mrs. Peacock';

const declareAllSuspects = function() {
  let suspectThree = 'Colonel Mustard';
  return `The suspects are ${suspectOne}, ${suspectTwo}, ${suspectThree}.`;
}

const suspects = declareAllSuspects();
console.log(suspects);
console.log(`Suspect three is ${suspectThree}.`);
// The suspects are Miss Scarlet, Professor Plum, Colonel Mustard.
// Suspect three is Mrs Peacock.
```

#### Episode 5

```js
const scenario = {
  murderer: 'Miss Scarlet',
  room: 'Kitchen',
  weapon: 'Candle Stick'
};
// scenario.weapon = Candle Stick

const changeWeapon = function(newWeapon) {
  scenario.weapon = newWeapon;
}
// function changeWeapon defines new weapon
// scenario.weapon = Candle Stick

const declareWeapon = function() {
  return `The weapon is the ${scenario.weapon}.`;
}
// declare

changeWeapon('Revolver');
const verdict = declareWeapon();
console.log(verdict);
// The weapon is the Revolver
```

#### Episode 6

```js
let murderer = 'Colonel Mustard';
// murderer = Colonel Mustard

const changeMurderer = function() {
  murderer = 'Mr. Green';
  // murderer = Mr Green

  const plotTwist = function() {
    murderer = 'Mrs. White';

  }
  // murderer =#1 Mr Green
  plotTwist();
  // murderer = Mrs White
}

const declareMurderer = function () {
  return `The murderer is ${murderer}.`;
}

changeMurderer();
const verdict = declareMurderer();
console.log(verdict);
// The murderer is Mrs White
```

#### Episode 7

```js
let murderer = 'Professor Plum';

const changeMurderer = function() {
  murderer = 'Mr. Green';
// murderer = Mr Green

  const plotTwist = function() {
    let murderer = 'Colonel Mustard';
// murderer = Colonel Mustard
    const unexpectedOutcome = function() {
      murderer = 'Miss Scarlet';
      // murderer = Miss Scarlett
    }
// murderer = Colonel Mustard
    unexpectedOutcome();
// murderer = Miss Scarlett
} // end of plotTwist
// murderer = Mr Green
  plotTwist();
}
// murderer = Professor Plum
const declareMurderer = function() {
  return `The murderer is ${murderer}.`;

}
// murderer = Professor Plum
changeMurderer();
const verdict = declareMurderer();
console.log(verdict);
// The murderer is Mr Green (runs declareMurderer)
```

#### Episode 8

```js
const scenario = {
  murderer: 'Mrs. Peacock',
  room: 'Conservatory',
  weapon: 'Lead Pipe'
};
// weapon = Lead pipe

const changeScenario = function() {
  scenario.murderer = 'Mrs. Peacock';
  scenario.room = 'Dining Room';
// scenario.weapon = Lead Pipe

  const plotTwist = function(room) {
    if (scenario.room === room) {
      scenario.murderer = 'Colonel Mustard';
    }
// scenario.weapon = Lead Pipe

    const unexpectedOutcome = function(murderer) {
      if (scenario.murderer === murderer) {
        scenario.weapon = 'Candle Stick';
      }
    }

    unexpectedOutcome('Colonel Mustard');
  }

  plotTwist('Dining Room');
}

const declareWeapon = function() {
  return `The weapon is ${scenario.weapon}.`
}

changeScenario();
const verdict = declareWeapon();
console.log(verdict);
// The weapon is Candle Stick
```

#### Episode 9

```js
let murderer = 'Professor Plum';

if (murderer === 'Professor Plum') {
  let murderer = 'Mrs. Peacock';
}

const declareMurderer = function() {
  return `The murderer is ${murderer}.`;
}

const verdict = declareMurderer();
console.log(verdict);
// The murderer is Professor Plum
```

### Extensions

Make up your own episode!
