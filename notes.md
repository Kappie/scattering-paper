# Presentation on scattering transform


Signals contain lots and lots of data that we don't need. Getting the relevant
parts can be like finding a needle in a haystack. Our quest is to build a
representation that is sparse, while being invariant to some things intra-class
differences, yet remains sensitive to other things.

In this introduction, we will start with considering 1D and 2D signals: sound
and 2D image signals, respectively.

The most wide-spread signal representation is the Fourier transform. It converts
the signal into a frequency representation. For some signals, that is very illuminating,
since they consist of only a few frequencies.

There is no function f which is both highly localized in time and has a Fourier
transform with its energy highly localized in frequency. (That means, there is
a fundamental limit, given by the Heisenberg uncertainty principle.)

For a signal representation of chords, this would be a very good transform. A
huge benefit of this transform is that it's translation invariant, it doesn't
matter if the time signal is shifted. But for audio recognition or
classification of instruments or musical pieces, say, we are interested in a lot
more than frequency information. We are interested in, say, onsets, variation in
amplitude, tone quality, phrasing, duration. We hear clearly time variation of
frequencies. All this cannot be adequately captured by the Fourier transform.
So for these types of signal, we need to decompose our original signal over elementary
functions that have a narrow support in both time and frequency.

A common solution is to cut the signal up in many separate signals of time T,
and take separate Fourier transforms. This is called the short-term Fourier transform.
This is shown here for a violin note, bowed 14 times. It works wonderfully for this signal, but since we have introduced a single timescale
T, we again run into the Heisenberg uncertainty principle: if we want to be able
to separate events that are closely spaced together, we won't be able to distinguish frequency
components that are very close together.

The message is that there will always be a tradeoff. But many real-world signals,
for example sounds, are made up of a short "attack", which has a high spatial localisation,
followed by a steady, sustained signal, which is delocalized in space, but has a
high frequential localisation.

This is one of the reasons for the creation of the wavelet transform and
multiresolution analysis, which can give good time resolution for high-frequency
events and good frequency resolution for low-frequency events, the combination
best suited for many real signals.
