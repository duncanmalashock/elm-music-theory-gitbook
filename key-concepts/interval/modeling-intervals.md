# Modeling intervals

## Goals when modeling intervals

* Intervals contain a number and a quality
* Intervals are perfect or imperfect, depending on their number
* Intervals can be augmented or diminished to change their semitone value
* When using an interval to transpose a pitch:
  * The pitch's letter name changes according to the interval number
  * The pitch's accidentals are changed to agree with the interval's semitone value

Here is my model of an `Interval`:

```text
type Interval
    = Interval Direction IntervalQuality IntervalNumber


type Direction
    = Up
    | Down
    
type IntervalNumber
    = Unison
    | Second
    | Third
    | Fourth
    | Fifth
    | Sixth
    | Seventh
    | Octave IntervalNumber


type IntervalQuality
    = Perfect Offset
    | Imperfect Offset
    
    
type Offset
    = Offset Int
```

Here is its application in a `transpose` function:

```text
transpose :
    Interval
    -> Pitch
    -> Pitch
transpose interval p =
    let
        transposedPitchClass =
            pitchClass p
                |> PitchClass.transpose interval

        initialSemitones =
            semitones p

        intervalSemitoneTarget =
            Interval.semitones interval

        transposedSemitones =
            PitchClass.semitones transposedPitchClass

        semitoneError =
            intervalSemitoneTarget - transposedSemitones

        targetOctaveSemitones =
            initialSemitones + semitoneError

        numberOfOctaves =
            targetOctaveSemitones // 12
    in
    Octave.octave numberOfOctaves
        |> Pitch transposedPitchClass
```

