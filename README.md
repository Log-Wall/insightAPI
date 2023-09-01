# **Insight** affliction tracking

Inisght affliction tracking package.

## API

### `currentAffs()`

Returns an array of afflictions on current target.

```js
insight.currentAffs(); // ['asthma', 'paralyis', 'clumsiness'];

```
### `currentAffDisplay()`
Returns an array of afflictions on current target in string format including probability.

```js
insight.currentAffDisplay(); // ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];

```
### `currentAffDisplayHTML()`
Returns an HTML friendly display of the current affs, including probability.

```js
insight.currentAffDisplay(); // ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];

```
### `hasAff({id, probability = 0})`
Returns a boolean for affliction on target meeting a provided probability from 0 - 1.

```js
//Target afflictions ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];
insight.hasAff('asthma'); // true

insight.hasAff('asthma', 0.75); //false

insight.hasAff('asthma', 0.25); // true
```
### `hasAnAff({ids, player, probability = 0})`
Returns a boolean for the presence of any aff listed in the array meeting a provided probability from 0 - 1 for the current target.
```js
//Target afflictions ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];
insight.hasAnAff(['asthma', 'clumsiness']); // true

insight.hasAnAff(['nausea', 'slickness']); // false

insight.hasAnAff(['asthma', 'paralysis'], 0.75); // true

insight.hasAnAff(['asthma', 'clumsiness'], 1); // false
```
### `hasAffs({ids, player, probability = 0})`
Returns a boolean for the presence of all affs listed in the array meeting a provided probability from 0 - 1 for the current target.
```js
//Target afflictions ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];
insight.hasAffs(['asthma', 'clumsiness']); // true

insight.hasAffs(['asthma', 'slickness']); // false

insight.hasAffs(['asthma', 'paralysis'], 1); // false

insight.hasAffs(['asthma', 'clumsiness'], 0.5); // true
```
### `hasDef({id, player})`
Returns a boolean for the state of a tracked defense on the target.
```js
//Target defense rebounding = true, shield = false;
insight.hasDef('rebounding'); // true

insight.hasDef('shield'); // false
```
### `getStatus({id, player})`
Returns the stored value of any status variable tracked by **insight** on the current target.
```js
//Target health = 5000, mana = 4500
insight.getStatus({id: 'hp'}); // 5000
```
### `addAff({id, player})`
### `randomAffs({ids, player})`
### `smartAffs({ids, player, ordered = false})`
### `removeAff({id, player})`
### `confirmAff({id, state, player})`
Used to confirm if a tracked aff is either 1.0 or no longer present; e.g. A target with tacked asthma smoking.
```js
//Target afflictions ['asthma: 0.5', 'clumsiness: 0.5', 'paralysis: 1'];
insight.confirmAff({id: 'asthma', state: true});
//Target afflictions ['asthma: 1', 'clumsiness: 0.5', 'paralysis: 1'];
insight.confirmAff({id: 'paralysis', state: false});
//Target afflictions ['asthma: 1', 'clumsiness: 0.5''];
```
### `usedCure({id, player})`

### `addDef({id, player})`

### `removeDef({id, player})`

### `setStatus({id, value, player})`

### `setTarget(player)`

### `reset()`


