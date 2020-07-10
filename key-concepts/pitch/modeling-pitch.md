# Modeling pitch

## Goals when modeling pitch

* There are twelve semitones to the octave, which, by convention, are represented as pitch classes using letter names and optional accidentals
* Pitches are instances of pitch classes in a particular octave
* Octaves should be limited to a practical range

Here is my model of a `PitchClass`, which allows an arbitrary semitone offset given the possibility of any number of accidentals:

```text
type PitchClass
    = PitchClass Letter Offset

type Letter
    = C
    | D
    | E
    | F
    | G
    | A
    | B
    
type Offset
    = Offset Int
```

Triple \(or more\) sharps or flats are theoretically possible, but only constructor functions for double accidentals are exposed:

```text
natural : Offset
natural =
    Offset 0
    
flat : Offset
flat =
    Offset -1

sharp : Offset
sharp =
    Offset 1
    
doubleSharp : Offset
doubleSharp =
    Offset 2
    
doubleFlat : Offset
doubleFlat =
    Offset -2
```

 Conversion to semitones:

```text
semitones : PitchClass -> Int
semitones (PitchClass l (Offset o)) =
    Letter.semitones l + o
```

A `Pitch` is a `PitchClass` within a particular `Octave`:

```text
type Pitch
    = Pitch PitchClass Octave
    
type Octave
    = Octave Int
```

Converting from `PitchClass` to `Pitch`:

```text
fromPitchClass : Octave -> PitchClass -> Pitch
```

