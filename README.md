---
description: A toolkit for musical ideas
---

# Introduction

[https://github.com/duncanmalashock/elm-music-theory](https://github.com/duncanmalashock/elm-music-theory)

## Overview

This project is meant to ease the analysis and generation of musical concepts, starting from fundamental structures like pitch and rhythm; building up to larger ones like melodic lines, harmonic progressions, chord voicings; and ultimately, arrangements and logical sections of a composition.

## Motivation

Composing music can involve a huge number of information-processing tasks. Many of these tasks are possible to automate, but currently they must be done in the composer's head.

There are many applications that make it easier to write down—or _notate_—music, but no commercial software tool has made it possible to **express, organize, and manipulate musical ideas as more than concrete groups of notes**, in a way that would allow composers to work at a higher level of abstraction. The music must still be thought through and written down, note by note.

Mechanical engineers have [computer-aided design](https://en.wikipedia.org/wiki/Computer-aided_design) tools to automate many of their tasks; why not computer-aided composition tools for musicians?

## Personal goals

I'm specifically interested in how to make it easier and faster to do the following tasks:

* \*\*\*\*[**Sequencing**](https://en.wikipedia.org/wiki/Sequence_%28music%29) ****— beginning with a short musical phrase and changing it in various ways in order to create musical development.
* \*\*\*\*[**Arrangement**](https://en.wikipedia.org/wiki/Arrangement) ****— harmonizing each note of a melody into chords, transforming chord progressions into accompaniment, and distributing these among multiple instruments. 

## Scope of this project

I'm limiting the scope of this project to Western music, including classical and jazz, and styles that derive from them, that use the [equal-temperament](https://en.wikipedia.org/wiki/Equal_temperament) tuning system and [harmony](https://en.wikipedia.org/wiki/Harmony). This project is not meant to include [microtonal](https://en.wikipedia.org/wiki/Microtonal_music) music or music using non-Western scales or tuning systems.

## Goals of this document

This document attempts to:

* Introduce the key concepts of the problem domain as best I can
* Explain the current design decisions I've made
* Express the current challenges of the project as I work through it

