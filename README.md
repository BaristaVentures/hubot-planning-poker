# hubot planning poker
Hubot script for poker planning

## Installation

```
npm install hubot-planning-poker --save
```

Add "hubot-planning-poker" to external-scripts.json:

```json
[
  "hubot-planning-poker"
]
```

## Usage

### Vote

Records user vote

**poker vote #\<story_number> \<vote> [-u \<username>]**

[-u \<username>] allows to override default name. Useful for testing.

```
hubot> poker vote #4264 3
hubot> ShellUser has voted for story #123
hubot> 
hubot> poker vote #4264 3 -u bob
hubot> bob has voted for story #123
```

### Clear

Deletes user story

**poker clear #\<story_number>**

```
hubot> poker clear #4264
```

### Result

Prints all votes and statistics

**poker result #\<story_number> [-c]**

[-c] pretty prints vote results as cards. Might display incorrectly if font in output is not monospaced

```
hubot> poker result #4264 -c
hubot> Result for story #4264
       rob:
       +-----+
       |  5  |
       +-----+
       
       bob:
       +-----+
       |  8  |
       +-----+
       
       mob:
       +-----+
       |  8  |
       +-----+
       
       hob:
       +------+
       |  13  |
       +------+
       
       avg        min      max
       +=======+  +=====+  +======+
       |  8.5  |  |  5  |  |  13  |
       +=======+  +=====+  +======+
       
       stats:
       5 x 1 [rob]
       8 x 2 [bob,mob]
       13 x 1 [hob]
       time since start: 0 min, 34 sec
```