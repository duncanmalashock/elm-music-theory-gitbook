# Modeling chords

## Goals when modeling chords

* A chord has a set of pitch classes, called factors
* A chord's factors are built up from its root
* A chord's quality is defined by the intervals between its root and its factors
* A chord is named for its root and its quality
* A chord's quality may be characterized by some common conventions when possible:
  * Triad
  * "Added tone" chords like 6 and 6/9
  * Seventh chords with optional extensions and/or alterations
* A chord can have a suspended fourth or second
* A chord's name can be written as a symbol, sometimes in many different ways
* Some chords have no name

## Modeling `ChordType`

A `ChordType` is a definition of chord quality apart from a particular root as a list of intervals:

```text
type ChordType
    = ChordType (List Interval)
```

`ChordType`s can be instantiated by building up factors with some helper functions:

```text
majorSixNine : ChordType
majorSixNine =
    custom
        |> withMajorThird
        |> withFifth
        |> withSixth
        |> withNinth
```

## Modeling `Chord`

`ChordType` and `Chord` work have a similar abstract/concrete relationship like those between `PitchClass` and `Pitch`, and `ScaleType` and `Scale`. A `Chord` is a `ChordType` with a root defined by a `PitchClass`:

```text
type Chord
    = Chord PitchClass.PitchClass ChordType.ChordType
```

