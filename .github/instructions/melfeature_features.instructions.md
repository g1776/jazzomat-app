---
description: Use these instructions when you need  to know the feature definition files available. Such as defining features for accents, intervals, tone, meter, rhythm, contour, sequences, etc.
# applyTo: 'Use these instructions when you need  to know the feature definition files available. Such as defining features for accents, intervals, tone, meter, rhythm, contour, sequences, etc.' # when provided, instructions will automatically be added to the request context when the pattern matches an attached file
---

List of Feature Definition Files
Features are organized and bundled into Feature Definition Files (FDF). Each of the 92 FDFs contains several single features which can be selected or de-selected individually. Moreover, FDFs are sorted in different categories with respect to the character and nature of the contained features. Accent features are mostly equivalent to binary structural markers for positions on which tonal events might be perceived as more salient than others. Auxiliary features are no features in the strict sense, but are useful for advanced and combined computations. Tone Formation features deal with articulations (staccato, legato etc.) and annotated modulations . Contour features try to capture aspects of a melody contour in time vs. pitch space. Interval features derive from differences of pitch and pitch class values. They come in four different levels of exactness: semitone intervals, fuzzy intervals (aka ‘refined contour’), Parson’s Codeyear (aka ‘contour’), as well as interval classes. Metadata features access annotated metadata of melodies. Meter features deal with metrical annotations and derived transformations. Rhythm deals with the time componente of melodies mostly durations and inter-onset intervals. Sequence features come in three different flavours: interval, pitch and rhythm. They try to catch aspects of sequentiality, such as bi- and trigrams and runlengths. Finally, Structure features are based on self-similarities of melodies on the level of individual phrases.

Note

FDFs are mostly of two different varieties: Those bundling single, scalar-valued features, and those containing vector or matrix-valued data. Vector-valued features are often either histograms or event-based features, which return for each event a certain value, e.g., a list of raw values of a certain transformation. For a better understanding of the transformation underlying many features, a look into basic transformations might be helpful.

Accents
Feature Bundle

Interval jump accents

Duration accents (Abs. IOI)

Structural accents (phrases)

Duration accents (Rel. IOI)

Pitch extrema accents

Metrical accents (on/offbeat)

Duration accents (Raw IOI)

Harmony accents

Auxiliary
Feature Bundle

Melody Export

Sections IDs and Labels

Contour
Feature Bundle

Waviness/Zig-Zagity.

Contour Descriptors

Interval
Feature Bundle

Parson’s Code Single Densities

Semitone Interval Single Features

Parson’s Code Distribution (“Contour”)

Semitone Interval Distribution

Fuzzy Interval Distribution (Refined Contour)

Fuzzy Interval (Refined Contour) Single Features

Interval Class Distribution

Interval Class Single Features

Parson’s Code Up/Down Ratio

MLA
Feature Bundle

MLA Exports

Metadata
Feature Bundle

Solo Metadata

EsAC Metadata

Meter
Feature Bundle

Metrical Circle Map Markov Distributions

Metrical Circle Map Markov Features

Meter Raw Exports

Pitch
Feature Bundle

Pitch Features

Tessitura Normalized Pitch

Chordal Diatonic Pitch Class Distribution

Number of Different Pitch Classes.

Tonal Pitch Class Single Features

Extended Chordal Diatonic Pitch Class Distribution

Chordal Diatonic Pitch Class Features

Pitch Class Single Features

Average Number of Pitch Classes per Phrase

Extended Chordal Diatonic Pitch Class Single Features

Tonal Pitch Class Distribution

Pitch Class Distribution

Chordal Pitch Class Feature

Chordal Pitch Class Distribution

Pitch Distribution

Chordal Pitch Class Circle Map Features (Experimental)

Rhythm
Feature Bundle

Variability Indices (Duration)

Microtiming Features

Duration Ratios

Inter-onset Interval Class Single Features

Inter-onset Interval Class Distribution

Event Densities

Duration Class Single Features

Duration Class Distribution

Variability Indices (IOI)

IOI Ratios

Tempo Features

Sequence/Interval
Feature Bundle

Interval Class Bigrams

Fuzzy Interval Trigrams

Average Run-lengths of arpeggios

Average Run-lengths of Chromatic passages

Fuzzy Interval Bigrams

Average Run-lengths of Chromatic Passages

Parson’s Code Bigrams

Percentage of Chromatic Passages

Average Run-length of Parson’s Code Segments

Average Run-length of Chromatic Passages

Average Run-lengths of Parsons Sequences

Semitone Interval Trigrams

Parson’s Code Trigrams

Semitone Interval Bigrams

Interval Class Trigrams

Sequence/Pitch
Feature Bundle

Pitch Class Bigrams

Chordal Diatonic Pitch Class Trigrams

Chordal Diatonic Pitch Class Bigrams

Pitch Class Trigrams

Tonal Pitch Class Bigrams

Pitch Bigrams

Pitch Pattern Lengths and Distances

Pitch Trigrams

Chordal Pitch Class Bigrams

Tonal Pitch Class Trigrams

Chordal Pitch Class Trigrams

Sequence/Rhythm
Feature Bundle

Duration Class Bigrams

Duration Class Trigrams

Duration Class Run-lengths

Inter-onset Interval Class Bigrams

Inter-onset Interval Class Run-lengths

Inter-onset Interval Class Trigrams

Structure
Feature Bundle

Form Structure of Phrases

Self-similarity Features

Self-similarity Matrix of Phrases

Tone Formation
Feature Bundle

Loudness

Articulation

Modulation

Accents
Interval jump accents
Description: Large pitch jumps are thought to convey accents, i.e., have a higher salience. However, no consensus is reached what means ‘large’ nor if it should be absolute or relative jumps nor if the tone before or after the jump or both should receive the accent. Some basic variants are collected here, but further research is needed to settle the issue.

Feature Definition File Name: ACCENTS_JUMPS

Category: Accents

Included Features:

Label

Type

Length

Description

jumpaft3

Integer [0,1]

N

Raw vector of accents for tones following a large pitch jump of at least 3 semi-tones (either direction).

jumpaft4

Integer [0,1]

N

Raw vector of accents for tones following a large pitch jump of at least 4 semi-tones (either direction).

jumpaft5

Integer [0,1]

N

Raw vector of accents for tones following a large pitch jump of at least 5 semi-tones (either direction).

jumpbef3

Integer [0,1]

N

Raw vector of accents for tones before a large pitch jump of at least 3 semi-tones (either direction).

jumpbef4

Integer [0,1]

N

Raw vector of accents for tones before a large pitch jump of at least 4 semi-tones (either direction).

jumpbef5

Integer [0,1]

N

Raw vector of accents for tones before a large pitch jump of at least 5 semi-tones (either direction).

jumpbea3

Integer [0,1]

N

Raw vector of accents for tones before and after a large pitch jump of at least 3 semi-tones (either direction).

jumpbea4

Integer [0,1]

N

Raw vector of accents for tones before and after a large pitch jump of at least 4 semi-tones (either direction).

jumpbea5

Integer [0,1]

N

Raw vector of accents for tones before and after a large pitch jump of at least 5 semi-tones (either direction).

jumploc

Integer [0,1]

N

Raw vector of accents for tones after a pitch interval that is at least 1 semi-tone larger than the previous interval.

jumploc2

Integer [0,1]

N

Raw vector of accents for tones after a pitch interval that is at least 2 semi-tone larger than the previous interval.

thom

Real [0, 1]

N

Raw vector of accents according to Thomassen’s algorithm (1982), which is based on the seven possible pitch direction patterns that can be formed by 2-interval chains (3-note patterns). Values are not binary, but probabilities.

thom_thr

Inetger[0,1]

N

Raw vector of Thomassen accents with exceed a certain threshold (.75 in this case).

Duration accents (Abs. IOI)
Description: Durations accent are based on the music-psychological observation, that for short-long (SL) patterns the second tone is perceived as accented (more pronounced, more salient). Included here are several accent features that operationalize the intuitive notion of short-long in several different ways based on IOI classification according to a absolute reference time of 0.5 s.

Feature Definition File Name: ACCENTS_DURATION_ABS

Category: Accents

Included Features:

Label

Type

Length

Description

longpr_abs

Integer [0,1]

N

Raw accent vector of tones with an higher (longer) IOI class than the previous one.

long2pr_abs

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes away from that of the previous one.

longmod_abs

Integer [0,1]

N

Raw accent vector of tones with a higher/longer IOI class than the most frequent (mode) IOI class.

long2mod_abs

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes away from the most frequent (mode) IOI class.

longmod_win5_abs

Integer [0,1]

N

Raw accent vector of tones with an IOI class longer than mode IOI class of the past 5 IOIs.

long2mod_win5_abs

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes longer than the mode IOI class of the past 5 IOIs.

Structural accents (phrases)
Description: Structurally important positions can give rise to accents (and vice versa). Currently, only phrases markers are implemented here.

Feature Definition File Name: ACCENTS_STRUCTURE

Category: Accents

Included Features:

Label

Type

Length

Description

phrasbeg

Integer [0,1]

N

Raw vector of markers for phrase beginnings (if available).

phrasend

Integer [0,1]

N

Raw vector of markers for phrase endings (if available).

phrasbor

Integer [0,1]

N

Raw vector of markers for phrase beginning & endings (if available).

Duration accents (Rel. IOI)
Description: Durations accent are based on the music-psychological observation, that for short-long (SL) patterns the second tone is perceived as accented (more pronounced, more salient). Included here are several accent features that operationalize the intuitive notion of short-long in several different ways, but always based on IOI classification according to a relative reference time of beat duration.

Feature Definition File Name: ACCENTS_DURATION_REL

Category: Accents

Included Features:

Label

Type

Length

Description

longpr_rel

Integer [0,1]

N

Raw accent vector of tones with an higher (longer) IOI class than the previous one.

long2pr_rel

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes away from that of the previous one.

longmod_rel

Integer [0,1]

N

Raw accent vector of tones with a higher/longer IOI class than the most frequent (mode) IOI class.

long2mod_rel

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes away from the most frequent (mode) IOI class.

longmod_win5_rel

Integer [0,1]

N

Raw accent vector of tones with an IOI class longer than mode IOI class of the past 5 IOIs.

long2mod_win5_rel

Integer [0,1]

N

Raw accent vector of tones with an IOI class at least two classes longer than the mode IOI class of the past 5 IOIs.

Pitch extrema accents
Description: Extreme pitch values (maxima and minima) are likely positions to stand out from the context. Some variations in operationalisation are possible (e.g., with respect to cambiatas and trillers).

Feature Definition File Name: ACCENTS_PITCH_EXTREMA

Category: Accents

Included Features:

Label

Type

Length

Description

pextrem

Real [0,1]

N

Raw accent vector of pitch extrema (no restrictions).

pextrmf

Real [0,1]

Var

Raw accent vector of pitch extrema (excluding proper cambiata).

pextrst

Real [0,1]

N

Raw accent vector of pitch extrema (sensu Steinbeck, with at least two intervals before and after the extrema leading strictly to it).

Metrical accents (on/offbeat)
Description: Metrical accents are one the most fundamental accents. Classically, meter is partly defined as an underlying regular accent structure. Syncopations are likely to give rise to accents as well, since they violate metrical expectations. Here, on-beat as well as off-beat (i.e., syncopation) accents collected.

Feature Definition File Name: ACCENTS_METER

Category: Accents

Included Features:

Label

Type

Length

Description

beat1

Integer [0,1]

N

Raw vector of accents on the primary accent (first beat) of a bar.

beat3

Integer [0,1]

N

Raw vector of accents on the secondary accent of a bar, if present, e.g. in on the 3rd beat in 4/4-measures (hence the name).

beat13

Integer [0,1]

N

Raw vector of accents on the primary and secondiry accent of a bar.

beatall

Integer [0,1]

N

Raw vector of accents on all beat positions in a bar.

sync1

Integer [0,1]

N

Raw vector of accents on all syncopations right before the primary accent in a bar (‘anticipated 1’).

sync3

Integer [0,1]

N

Raw vector of accents on all syncopations right before the secondary accent in a bar (‘anticipated 3’).

sync13

Integer [0,1]

N

Raw vector of accents on all syncopations right before primary and secondary accents in a bar (‘anticipated 1s and 3s’).

sync1234

Integer [0,1]

N

Raw vector of accents on all syncopations right before all beats in a bar.

syncall

Integer [0,1]

N

Raw vector of accents on all syncopations on every sub-beat metrical level (i.e., excluding half-beat level).

swing_markers

Integer [0,1]

N

Raw vector of structural markers for swing candidates.

Duration accents (Raw IOI)
Description: Durations accent are based on the music-psychological observation, that for short-long (SL) patterns the second tone is perceived as accented (more pronounced, more salient). Icnluded here are several accent features that operationalize the intuitive notion of short-long in several differnet ways based on raw IOIs.

Feature Definition File Name: ACCENTS_DURATION

Category: Accents

Included Features:

Label

Type

Length

Description

longpr

Integer [0,1]

N

Raw accent vector of tones with longer IOI than the previous tone.

long2pr

Integer [0,1]

N

Raw accent vector of tones with an at least twice longer IOI than the previous tone.

longmod

Integer [0,1]

N

Raw accent vector of tones with a longer IOI than mode IOI of all tones.

long2mod

Integer [0,1]

N

Raw accent vector of tones with an at least twice longer IOI than mode IOI of all tones.

longmod_win5

Integer [0,1]

N

Raw accent vector of tones with IOI that is at least 41% longer than mean of the past 5 IOIs.

long2mod_win5

Integer [0,1]

N

Raw accent vector of tones with IOI that is at least twice as long than mean of the past 5 IOIs.

Harmony accents
Description: Structural marker for in-chord or out-of-chord tones (only for melodies with annotated chords).

Feature Definition File Name: ACCENTS_HARMONY

Category: Accents

Included Features:

Label

Type

Length

Description

triad

Integer [0,1]

Var

Raw markers of chord tones (excluding upper structures).

inchord

Integer [0,1]

Var

Raw markers of chord tones (including upper structures).

outchord

Integer [0,1]

Var

Raw marker vector of non-chord tones.

Auxiliary
Melody Export
Description: Exports melody as lists of onset, duration, pitch, and metrical positions.

Feature Definition File Name: GENERAL_MELODY_RAW

Category: Auxiliary

Included Features:

Label

Type

Length

Description

onset

Real

N

Onsets (in seconds) of events.

norm_onset

Real

N

Normalized onsets [0-1] of events.

first_onset

Real

1

First onset (in seconds) of events.

last_offset

Real

1

Last offset (in seconds) of events.

duration

Real

N

Duration (in seconds) of events.

pitch

Real

N

Raw MIDI pitch values of events.

metrical_position

String

N

Metrical positions of events (MP-dot-notation).

phraseid

String

Var

ID of containing phrase.

offset

Real

N

Offsets (in seconds) of events.

Sections IDs and Labels
Description: Returns sequences of raw phrase IDs, form labels, chorus IDs, chord labels and chord types.

Feature Definition File Name: GENERAL_SECTION_IDS

Category: Auxiliary

Included Features:

Label

Type

Length

Description

phrase_id_raw

Integer

N_P

Sequence of event-wise phrase IDs.

chorus_id_raw

Integer

Var

Sequence of event-wise chorus IDs.

form_labels_raw

Integer

Var

Sequence of event-wise form labels (as annotated).

chords_raw

Integer

Var

Sequence of event-wise chord symbols (as annotated and normalized).

chord_types_raw

Integer

Var

Sequence of event-wise chord type labels (triad type + seventh).

chord_types_sections

Integer

Var

Type labels for chord sections (triad type + seventh).

Contour
Waviness/Zig-Zagity.
Description: This feature set contains features related to (pitch-)extremal points in a melody. A local extremum (or turning) point can be either a minimum or maximum. Hence, pitches right before and right after an extremal point are both lower or equal (maximum) or higher or equal (minimum). For this module only true extremal points are counted, where the pitches must be strictly higher or lower to both sides. The percentage of extremal points can be regarded as a measure for zig-zagity (or waviness) of a melody. The extreme case are two alternatine pitches, where each and every point is a local extremum resulting in an extrema ratio of 1.

Feature Definition File Name: PITCH_WAVINESS

Category: Contour

Included Features:

Label

Type

Length

Description

extrema_ratio

Real

1

Percentage of extremal points.

extrema_count

Integer

1

Number of extremal points.

note_count

Integer

1

Number of notes.

Contour Descriptors
Description: Calculates various contour descriptors. First, Huron contour in three different varieties is supported: Code, Reduced Code and Numeric. Huron contour is calculated on a sequence of pitches by size comparison of the first pitch to the mean inner pitch (MIP, i.e., mean of MIDI pitches except the first and last element), and the MIP to the last pitch. There are three possible relations between two numbers: Greater (>), equal (=), or less (<). Combining two comparisons gives a set of nine different contour values: descending (>>), descending-horizontal (>=), concave (<>), horizontal-descending (=>), horizontal (==), horizontal-ascending (=<), convex (><), ascending-horizontal (<=), and ascending (<<). Short mnemonic codes for them are desc, desc-hor, concave, hor-desc, hor, hor-asc, convex, asc-hor, asc. The reduced code is a mapping of the mixed-horizontal category to their non-horizontal partner, i.e., desc-hor and hor-desc become desc and asc-hor and hor-asc become asc, which leaves 5 categories. The numeric values range from -4 to 4 in the same order. (Cf. Huron (1994), The Melodic Arch in Western Folksongs.). Second, gradient countour measures the pitch gradient \Delta p/\Delta T between extreme points. Third, Abesser contour is similar to Huron contour, but uses more stable estimators and is more suitable for longer sequences.

Feature Definition File Name: CONTOUR

Category: Contour

Included Features:

Label

Type

Length

Description

huron_contour_code

String

1

Huron contour codes. One of desc, desc-hor, concave, hor-desc, hor, hor-asc, convex, asc-hor, asc.

huron_contour_redcode

String

1

Reduced Huron contour codes. One of desc, concave, hor, convex, asc.

huron_contour_num

Integer [-4:+4]

1

Numeric value of Huron contour.

gradient_contour

Real

Var

List of gradients \Delta p/\Delta T between extreme values of note track.

abesser_contour_code

String

1

Abesser contour codes. One of desc, desc-hor, concave, hor-desc, hor, hor-asc, convex, asc-hor, asc.

abesser_contour_redcode

String

1

Reduced Abesser contour codes. One of desc, concave, hor, convex, asc.

abesser_contour_num

Integer [-4:+4]

1

Numeric value for Abesser contour.

Interval
Parson’s Code Single Densities
Description: Normalized histogram densities, mode, entropy and Zipf coefficient for Parson’s code. Values: down (-1), repeat/unisone (0), up (+1).

Feature Definition File Name: PARSON_FEATURES

Category: Interval

Included Features:

Label

Type

Length

Description

parsons_hist_descending

Real

1

Relative frequency for down (-1).

parsons_hist_constant

Real

1

Relative frequency for repeat (0).

parsons_hist_ascending

Real

1

Relative frequency for up (+1).

parsons_mode

Real

Var

Mode of Parson’s Code distribution (can be list!).

parsons_entropy

Real

1

Normalized entropy of Parson’s Code distribution.

parsons_zipf

Real

1

Zipf coefficient of Parson’s Code distribution.

Semitone Interval Single Features
Description: Calculates set of basic statistical sample descriptors (mean, median, mode, min, max, range, var, std) for interval and absolute interval distribution.

Feature Definition File Name: INT_FEATURES

Category: Interval

Included Features:

Label

Type

Length

Description

int_mean

Real

1

Mean of interval distribution.

int_median

Real

1

Median of interval distribution.

int_var

Real

1

Variance of of interval distribution.

int_std

Real

1

Standard deviation of interval distribution.

int_min

Real

1

Minimum of of interval distribution.

int_max

Real

1

Maximum of of interval distribution.

int_range

Real

1

Range of of interval distribution.

int_mode

Real

Var

Mode of interval distribution (can be list!).

int_zipf

Real

1

Zipf coefficient of interval distribution.

int_entropy

Real

1

Entropy of interval distribution (bits).

abs_int_mean

Real

1

Mean of absolute interval distribution.

abs_int_median

Real

1

Median of absolute interval distribution.

abs_int_var

Real

1

Variance of absolute interval distribution.

abs_int_std

Real

1

Standard deviation of interval distribution.

abs_int_min

Real

1

Minimum of absolute interval distribution.

abs_int_max

Real

1

Maximum of absolute interval distribution.

abs_int_range

Real

1

Range of absolute interval distribution.

abs_int_mode

Real

1

Mode of interval absolute distribution (can be list!).

abs_int_zipf

Real

1

Zipf coefficient of absolute interval distribution.

abs_int_entropy

Real

1

Entropy of absolute interval distribution (bits).

abs_int_sum

Real

1

Sum of absolute intervals (= distance moved in pitch space).

Parson’s Code Distribution (“Contour”)
Description: Histogram and raw vector of Parson’s Code (contour). Values: down (-1), repeat/unisone (0), up (+1).

Feature Definition File Name: PARSON_HIST

Category: Interval

Included Features:

Label

Type

Length

Description

parsons_raw

Integer [-1:+1]

N

Raw output (Parson’s code values of all melody notes).

parsons_hist_values

Integer [-1:+1]

3

Histogram bins for Parson’s code.

parsons_hist_counts

Real

3

Histogram bin counts (abs. frequencies).

Semitone Interval Distribution
Description: Histogram and raw vector of semitone intervals, either limited to the range of -20 to 20 semitones or full range (only raw and with appended zero element).

Feature Definition File Name: INT_HIST

Category: Interval

Included Features:

Label

Type

Length

Description

int_raw

Integer [-127:+127]

N-1

ist of semitone intervals.

int_hist_values

Integer [-20:+20]

41

Bins of semitone intervals [-20:20].

int_hist_counts

Integer

41

Absolute frequencies of semitone intervals.

int_raw_full_pad

Integer [-127:+127]

N

List of semitone intervals with appended 0.

Fuzzy Interval Distribution (Refined Contour)
Description: Histogram and raw vector of fuzzy intervals (aka refined contour). Values: big jump up/down (+/-4), jump up/down (+/-3), leap up/down (+/-1), step up/down (+/-1), repetition (0).

Feature Definition File Name: FUZZYINT_HIST

Category: Interval

Included Features:

Label

Type

Length

Description

fuzzyint_raw

Integer [-4:4]

N-1

Raw output (Fuzzy interval values over the full melody).

fuzzyint_hist_values

Integer [-4:4]

5

Histogram bins.

fuzzyint_hist_counts

Real

5

Histogram bin counts (abs. frequencies).

Fuzzy Interval (Refined Contour) Single Features
Description: Histogram counts, mode, entropy and Zipf coefficient of distribution of all 9 fuzzy interval classes (FUZZYINT). Values: big jump up/down (+/-4), jump up/down\*\* (+/-3), leap up/down (+/-1), step up/down (+/-1), repetition (0).

Feature Definition File Name: FUZZYINT_FEATURES

Category: Interval

Included Features:

Label

Type

Length

Description

fuzzyint_hist_09_big_jump_down

Real

1

Relative frequency big jump down (-4).

fuzzyint_hist_08_jump_down

Real

1

Relative frequency jump down (-3).

fuzzyint_hist_07_leap_down

Real

1

Relative frequency leap down ( -2).

fuzzyint_hist_06_step_down

Real

1

Relative frequency step down (-1).

fuzzyint_hist_05_repeat

Real

1

Relative frequency repetition (0).

fuzzyint_hist_04_step_up

Real

1

Relative frequency step up (+1).

fuzzyint_hist_03_leap_up

Real

1

Relative frequency leap up (+2).

fuzzyint_hist_02_jump_up

Real

1

Relative frequency jump up (+3).

fuzzyint_hist_01_big_jump_up

Real

1

Relative frequency big jump up (+4).

fuzzyint_mode

Real

Var

Mode of FUZZYINT distribution (can be list!).

fuzzyint_zipf

Real

1

Zipf coefficient of FUZZYINT distribution.

fuzzyint_entropy

Real

1

Normalized entropy of FUZZYINT distribution.

Interval Class Distribution
Description: Histogram and raw vector of intervals classes. Interval classes are minimal differences between pitches classes (i.e., length of shortest path on the circle) and have values from 0 to 6.

Feature Definition File Name: INTCLASS_HIST

Category: Interval

Included Features:

Label

Type

Length

Description

ic_raw

Integer [0:+6]

N-1

List of interval classes.

ic_hist_values

Integer [0:6]

7

Bins of Interval classes [0:6].

ic_hist_counts

Integer

7

Absolute frequencies of interval classes.

ic_raw_pad

Integer [0:+6]

N

List of interval classes with appended 0.

Interval Class Single Features
Description: Normalized histogram count, and basic statistics of interval class distribution. Interval classes are minimal differences between pitches classes (i.e., length of shortest path on the circle) and have values from 0 to 6.

Feature Definition File Name: INTCLASS_FEATURES

Category: Interval

Included Features:

Label

Type

Length

Description

ic_mean

Real

1

Mean of interval class distribution.

ic_median

Real

1

Median of interval class distribution.

ic_var

Real

1

Variance of of interval class distribution.

ic_std

Real

1

Standard deviation of interval class distribution.

ic_min

Real

1

Minimum of of interval class distribution.

ic_max

Real

1

Maximum of of interval class distribution.

ic_range

Real

1

Range of of interval class distribution.

ic_mode

Real

Var

Mode of interval class distribution (can be list!).

ic_zipf

Real

1

Zipf coefficient of interval class distribution.

ic_entropy

Real

1

Entropy of interval class distribution (bits).

ic_hist_density_0

Real

1

Relative frequency IC = 0.

ic_hist_density_1

Real

1

Relative frequency IC = 1.

ic_hist_density_2

Real

1

Relative frequency IC = 2.

ic_hist_density_3

Real

1

Relative frequency IC = 3.

ic_hist_density_4

Real

1

Relative frequency IC = 4.

ic_hist_density_5

Real

1

Relative frequency IC = 5.

ic_hist_density_6

Real

1

Relative frequency IC = 6.

Parson’s Code Up/Down Ratio
Description: Ratio of number of ascending and descending intervals in a melody (ignoring unisones).

Feature Definition File Name: PARSON_UP_DOWN_RATIO

Category: Interval

Included Features:

Label

Type

Length

Description

ratio_ascending_descending

Real [0,1]

1

Ratio of ascending to descending intervals.

MLA
MLA Exports
Description: Exports several mid-level analysis (MLA) related features (section event-based).

Feature Definition File Name: MLA_RAW

Category: MLA

Included Features:

Label

Type

Length

Description

MLA_raw

String

Var

Raw list of mid-level units.

MLA_main_type

String

Var

Raw list of main types of mid-level units.

MLA_full_type

String

Var

Raw list of full types of mid-level units.

MLA_backref

String

Var

Raw list of back references for mid-level units.

MLA_glue

String

Var

Raw list of glue operators of mid-level units.

MLA_modifier

String

Var

Raw list of modifiere for mid-level units.

MLA_length

String

Var

Raw list of idea length as number of notes.

MLA_duration

String

Var

Raw list of idea duration in secs onset-offset.

MLA_duration_bars

String

Var

Raw list of idea duration in decimal bar time.

MLA_main_dir

String

Var

Raw list of main directions of mid-level units.

Metadata
Solo Metadata
Description: Export all metadata for Jazzomat solos (currently only a subset).

Feature Definition File Name: GENERAL_SOLO_METADATA

Category: Metadata

Included Features:

Label

Type

Length

Description

performer

String

1

Performer.

title

String

1

Title.

titleaddon

String

1

Add-on for title.

solopart

String

1

Running number of a solo in a piece.

full_title

String

1

Full title (including solo part and title addon).

instrument

String

1

Instrument of the soloist. One of ts, ts-c, as, bs, bsx, cbsx, ss, sss, cl, bcl, acl, tp, tpt, flgn, tb, fl, cor, ptp, frhn, ob, voc or empty.

style

String

1

Style of piece. One of TRADITIONAL, SWING, BEBOP, COOL, HARDBOP, POSTBOP, FREE, FUSION, OTHER, MIX or empty.

avgtempo

String

1

Avg. Tempo (bpm).

tempoclass

String

1

Tempo class. One of SLOW, MEDIUM SLOW, MEDIUM, MEDIUM UP, UP or empty.

rhythmfeel

String

1

Basic rhythmic feel/groove style. One of TWOBEAT, SWING, BALLAD, LATIN, FUNK or empty.

key

String

1

Key or tonal center of the piece.

filename_sv

String

1

Filename of originating SV project file.

status

String

1

Status of transcription. One of PREFINAL, FINAL, DRAFT, ASSIGNED or empty.

composer

String

1

Composer of the piece.

tonality_type

String

1

Tonality type of the composition. One of FUNCTIONAL, MODAL, COLOR, FREE, BLUES, JAZZ-BLUES or empty.

genre

String

1

Genre of the composition. One of TRADITIONAL, BLUES, GREAT AMERICAN SONGBOOK, WORMS, ORIGINAL, RIFF or empty.

form

String

1

Form of the composition.

signature

String

1

Signature(s) of solo.

mbzid

String

1

Music Brainz ID.

recordingdate

String

1

Recording date(s) of containing record.

recordingyear

String

1

Recording year of containing record.

recordbib

String

1

Bibliography of record.

recordtitle

String

1

Title of containing record.

label

String

1

Record label of containing record.

solostart

String

1

Start time of solo in full track.

soloend

String

1

End time of solo in full track.

lineup

String

1

Line-up of track.

chord_changes

String

1

Chord changes as compact string.

chorus_count

String

1

Number of full choruses in the solo.

harmony_template

String

1

Underlying harmony template of composition.

solo_time

String

1

Start/End of solo in surrounding track.

EsAC Metadata
Description: Export all metadata for EsAC tunes.

Feature Definition File Name: GENERAL_ESAC_METADATA

Category: Metadata

Included Features:

Label

Type

Length

Description

collection

String

1

Collection.

esac_title

String

1

Orignal EsAC title.

region

String

1

Region of origin.

esac_key

String

1

Annotated key (tonic).

unit

Integer (2,4,8,16,32)

1

Annotated minimal rhythmic unit.

signature

String

1

Annotated signature (possible more than one, space separate, or FREE).

source

String

1

Annotated key (tonic).

function

String

1

Annotated (ritual) function.

comment

String

1

Comment section.

cnr

String

1

CNR section (with yet unknown meaning!).

tunefamily

String

1

Tunefamily based on EsAC-Ids.

text

String

1

Annotated lyrics.

melstring

String

1

Original melody code.

Meter
Metrical Circle Map Markov Distributions
Description: Histogram for Metrical Circle Map (N=48) unigrams and bigrams (occurrence and transition probabilites). See this document or here for more details.

Feature Definition File Name: MCM_HIST

Category: Meter

Included Features:

Label

Type

Length

Description

mcm_unigram_values

Array of Integer [0:47]

48

Histogram bins (MCM:48 values).

mcm_unigram_freqs

Real [0,1]

48

Histogram bin densities (MCM:48 values).

mcm_bigram_values

Array of Integer

Var

Histogram bins (all unique MCM bigrams).

mcm_bigram_freqs

Real [0,1]

Var

Histogram bin densities (all unique MCM bigrams).

Metrical Circle Map Markov Features
Description: Histogram for Metrical Circle Map (N=48) unigrams and bigrams (occurrence and transition probabilites, entropies and Zipf coefficients). See this document or here for more details.

Feature Definition File Name: MCM_FEATURES

Category: Meter

Included Features:

Label

Type

Length

Description

mcm_mean_angle

Real

1

Angle of circular mean of MCM distribution.

mcm_mean_length

Real

1

Length of circular mean of MCM distribution.

mcm_var

Real

1

Circular variance of MCM distribution (=1-length of circular mean).

mcm_std

Real

1

Circular standard deviation of MCM distribution.

mcm_disp

Real

1

Circular dispersion of MCM distribution.

mcm_mode

Real

Var

Mode of MCM distribution (can be list!).

mcm_zipf

Real

1

Zipf coefficient of MCM distribution.

mcm_entropy

Real

1

Normalized entropy of MCM distribution.

Meter Raw Exports
Description: Exports several meter related features (event-based).

Feature Definition File Name: METER_RAW

Category: Meter

Included Features:

Label

Type

Length

Description

metrical_position

String

N

Metrical positions (in MPD-notation) of events.

bar

Integer

N

Event bar numbers.

beat

Integer

N

Event beat numbers.

tatum

Integer

N

Event tatum positions.

durtatum

Integer

N

Events durations measured in current tatums (handle with care!).

metrical_weight

Integer [0:2]

N

Metrical weight of event (0 for any subbeat event, 1 for metrical weak beat events, 2 for metrical strong events).

mcm_48

Integer [0:47]

N

Position in metrical circle map with N=48 divisions.

metrical_weight_transition_code

Integer [0:8]

N-1

Bigrams of metrical weights coded with ternary numbers. Let w*i, w*{i+1} be the weights of notes i, i+1. Then the metrical weight transition value is 3w*i + w*{i+1}.

period

Integer

N

Event-based periods.

division

Integer

N

Event-based beat divisions.

syncopation

Integer [0:1]

N

Marker if event is syncopated (0=not syncopated, 1=syncopated).

syncopicity

Real [0,1]

1

Ratio of syncopated events to non-syncopated events.

metric_complexity

Real [0,1]

1

Combined metric complexity after Frieler, in preparation.

metric_complexity_division

Real [0,1]

1

Division-based metric complexity after Frieler, in preparation.

metric_complexity_compression

Real [0,1]

1

Compression-based metric complexity after Frieler, in preparation.

Pitch
Pitch Features
Description: Calculates set of basic statistical sample descriptors (mean, median, mode, min, max, range, var, std).

Feature Definition File Name: PITCH_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

pitch_mean

Real

1

Mean of PITCH distribution.

pitch_median

Real

1

Median of PITCH distribution.

pitch_var

Real

1

Variance of of PITCH distribution.

pitch_std

Real

1

Standard deviation of PITCH distribution.

pitch_min

Real

1

Minimum of of PITCH distribution.

pitch_max

Real

1

Maximum of of PITCH distribution.

pitch_range

Real

1

Range of of PITCH distribution.

pitch_mode

Real

Var

Mode of PITCH distribution (can be list!).

pitch_zipf

Real

1

Zipf coefficient of PITCH distribution.

pitch_entropy

Real

1

Entropy of PITCH distribution (bits).

Tessitura Normalized Pitch
Description: Raw vector of scaled MIDI pitches with respect to pitch range.

Feature Definition File Name: TESS_NORM_PITCH

Category: Pitch

Included Features:

Label

Type

Length

Description

tess_norm_pitch

Real [0, 1]

N

Tessatura-scaled pitch values.

Chordal Diatonic Pitch Class Distribution
Description: Histogram and raw vector of chordal diatonic pitch classes (CDPC).

Feature Definition File Name: CDPC_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

cdpc_raw

Integer

N

Raw output of note-wise CDPC values.

cdpc_hist_bins

String

Var

Histogram bins (all unique CDPC values occurring in a melody).

cdpc_hist_density

Real

Var

Histogram bin counts (absolute frequencies).

cdpc_raw_all

Integer

N

Raw output of note-wise CDPC values including NC values.

Number of Different Pitch Classes.
Description: Number of different pitch classes.

Feature Definition File Name: PC_NUM_UNIQUE_PC

Category: Pitch

Included Features:

Label

Type

Length

Description

number_of_unique_pc

Integer

1

Average number of different pitch classes.

Tonal Pitch Class Single Features
Description: Histogram counts of all 12 TPC values (normalized to density), as well as basic circular statistics (cf. https://en.wikipedia.org/wiki/Directional_statistics ).

Feature Definition File Name: TPC_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

tpc_hist_density_00

Real

1

Relative frequency TPC = 0.

tpc_hist_density_01

Real

1

Relative frequency TPC = 1.

tpc_hist_density_02

Real

1

Relative frequency TPC = 2.

tpc_hist_density_03

Real

1

Relative frequency TPC = 3.

tpc_hist_density_04

Real

1

Relative frequency TPC = 4.

tpc_hist_density_05

Real

1

Relative frequency TPC = 5.

tpc_hist_density_06

Real

1

Relative frequency TPC = 6.

tpc_hist_density_07

Real

1

Relative frequency TPC = 7.

tpc_hist_density_08

Real

1

Relative frequency TPC = 8.

tpc_hist_density_09

Real

1

Relative frequency TPC = 9.

tpc_hist_density_10

Real

1

Relative frequency TPC = 10.

tpc_hist_density_11

Real

1

Relative frequency TPC = 11.

tpc_circ_mean_angle

Real

1

Angle of circular mean of TPC distribution.

tpc_circ_mean_length

Real

1

Length of circular mean of TPC distribution.

tpc_circ_var

Real

1

Circular variance of TPC distribution (=1-length of circular mean).

tpc_circ_std

Real

1

Circular standard deviation of TPC distribution.

tpc_circ_disp

Real

1

Circular dispersion of TPC distribution.

tpc_entropy

Real

1

Normalized entropy of TPC distribution.

Extended Chordal Diatonic Pitch Class Distribution
Description: Histogram and raw vector of extended multi-digit chordal diatonic pitch classes (CDPCX).

Feature Definition File Name: CDPCX_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

cdpcx_raw

Integer

N

Raw output of note-wise CDPCX values.

cdpcx_hist_bins

Integer

N

Histogram bins (all unique CDPCX values occurring in a melody).

cdpcx_hist_density

Real

N

Histogram bin counts (abs. frequencies).

cdpcx_raw_all

Integer

N

Raw output of note-wise CDPCX values including NC values.

Chordal Diatonic Pitch Class Features
Description: Normalized histogram counts, mode, entropy and Zipf coefficient of CDPC distribution.

Feature Definition File Name: CDPC_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

cdpc_density_1

Real

1

Relative frequency CDPC = ‘1’.

cdpc_density_2

Real

1

Relative frequency CDPC = ‘2’.

cdpc_density_3

Real

1

Relative frequency CDPC = ‘3’.

cdpc_density_4

Real

1

Relative frequency CDPC = ‘4’.

cdpc_density_5

Real

1

Relative frequency CDPC = ‘5’.

cdpc_density_6

Real

1

Relative frequency CDPC = ‘6’.

cdpc_density_7

Real

1

Relative frequency CDPC = ‘7’.

cdpc_density_T

Real

1

Relative frequency CDPC = ‘T’.

cdpc_density_B

Real

1

Relative frequency CDPC = ‘B’.

cdpc_density_L

Real

1

Relative frequency CDPC = ‘L’.

cdpc*density*<

Real

1

Relative frequency CDPC = ‘<’.

cdpc*density*>

Real

1

Relative frequency CDPC = ‘>’.

cdpc_mode

Real

Var

Mode of CDPC distribution (can be list!).

cdpc_entropy

Real

1

Normalized entropy of CDPC distribution.

cdpc_zipf

Real

1

Zipf coefficient of CDPC distribution.

Pitch Class Single Features
Description: Histogram counts of all 12 PC values (normalized to density), as well as basic circular statistics (cf. https://en.wikipedia.org/wiki/Directional_statistics ).

Feature Definition File Name: PC_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

pc_hist_density_00_C

Real

1

Relative frequency PC = C.

pc_hist_density_01_C#

Real

1

Relative frequency PC = C#.

pc_hist_density_02_D

Real

1

Relative frequency PC = D.

pc_hist_density_03_Eb

Real

1

Relative frequency PC = Eb.

pc_hist_density_04_E

Real

1

Relative frequency PC = E.

pc_hist_density_05_F

Real

1

Relative frequency PC = F.

pc_hist_density_06_F#

Real

1

Relative frequency PC = F#.

pc_hist_density_07_G

Real

1

Relative frequency PC = G.

pc_hist_density_08_Ab

Real

1

Relative frequency PC = Ab.

pc_hist_density_09_A

Real

1

Relative frequency PC = A.

pc_hist_density_10_Bb

Real

1

Relative frequency PC = Bb.

pc_hist_density_11_B

Real

1

Relative frequency PC = B.

pc_circ_mean_angle

Real

1

Angle of circular mean of PC distribution.

pc_circ_mean_length

Real

1

Length of circular mean of PC distribution.

pc_circ_var

Real

1

Circular variance of PC distribution (=1-length of circular mean).

pc_circ_std

Real

1

Circular standard deviation of PC distribution.

pc_circ_disp

Real

1

Circular dispersion of PC distribution.

pc_entropy

Real

1

Normalized entropy of PC distribution.

Average Number of Pitch Classes per Phrase
Description: Average number of different pitch classes per phrase.

Feature Definition File Name: PC_AV_NUM_UNIQUE_PC_PHRASES

Category: Pitch

Included Features:

Label

Type

Length

Description

mean_number_of_unique_pc

Real [0:11]

1

Average number of different pitch classes per phrase.

Extended Chordal Diatonic Pitch Class Single Features
Description: Normalized histogram counts, mode, entropy and Zipf coefficient of CDPCX distribution.

Feature Definition File Name: CDPCX_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

cdpcx_density_1

Real

1

Relative frequency CDPCX = ‘1’.

cdpcx_density_2

Real

1

Relative frequency CDPCX = ‘2’.

cdpcx_density_3

Real

1

Relative frequency CDPCX = ‘3’.

cdpcx_density_4

Real

1

Relative frequency CDPCX = ‘4’.

cdpcx_density_5

Real

1

Relative frequency CDPCX = ‘5’.

cdpcx_density_6

Real

1

Relative frequency CDPCX = ‘6’.

cdpcx_density_7

Real

1

Relative frequency CDPCX = ‘7’.

cdpcx_density_T

Real

1

Relative frequency CDPCX = ‘T’.

cdpcx_density_B

Real

1

Relative frequency CDPCX = ‘B’.

cdpcx_density_L

Real

1

Relative frequency CDPCX = ‘L’.

cdpcx*density*<

Real

1

Relative frequency CDPCX = ‘<’.

cdpcx*density*>

Real

1

Relative frequency CDPCX = ‘>’.

cdpcx_density_b2

Real

1

Relative frequency CDPCX = ‘-‘ (b2).

cdpcx_density_b6

Real

1

Relative frequency CDPCX = ‘%’ (b6).

cdpcx_mode

Real

Var

Mode of CDPCX distribution (can be list!).

cdpcx_entropy

Real

1

Normalized entropy of CDPCX distribution.

cdpcx_zipf

Real

1

Zipf coefficient of CDPCX distribution.

Tonal Pitch Class Distribution
Description: Histogram and raw vector of tonal pitch classes (TPC).

Feature Definition File Name: TPC_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

tpc_raw

Integer

N

Raw output of note-wise TPC values.

tpc_hist_bins

Integer [0:11]

12

Histogram bins (all unique TPC values occurring in a melody).

tpc_hist_counts

Integer

12

Histogram bin count values (abs. frequencies).

Pitch Class Distribution
Description: Histogram and raw vector of pitch classes.

Feature Definition File Name: PC_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

pc_raw

Integer [0:11]

N

Raw output (values for all melody notes).

pc_hist_values

Integer [0:11]

12

Histogram bins.

pc_hist_dens

Real

12

Histogram bin count (abs. frequencies).

Chordal Pitch Class Feature
Description: Normalized histogram count, and basic circular statistics (cf. https://en.wikipedia.org/wiki/Directional_statistics ) of CPC distribution.

Feature Definition File Name: CPC_FEATURES

Category: Pitch

Included Features:

Label

Type

Length

Description

cpc_hist_density_00

Real

1

Relative frequency CPC = 0.

cpc_hist_density_01

Real

1

Relative frequency CPC = 1.

cpc_hist_density_02

Real

1

Relative frequency CPC = 2.

cpc_hist_density_03

Real

1

Relative frequency CPC = 3.

cpc_hist_density_04

Real

1

Relative frequency CPC = 4.

cpc_hist_density_05

Real

1

Relative frequency CPC = 5.

cpc_hist_density_06

Real

1

Relative frequency CPC = 6.

cpc_hist_density_07

Real

1

Relative frequency CPC = 7.

cpc_hist_density_08

Real

1

Relative frequency CPC = 8.

cpc_hist_density_09

Real

1

Relative frequency CPC = 9.

cpc_hist_density_10

Real

1

Relative frequency CPC = 10.

cpc_hist_density_11

Real

1

Relative frequency CPC = 11.

cpc_circ_mean_angle

Real

1

Angle of circular mean of CPC distribution.

cpc_circ_mean_length

Real

1

Length of circular mean of CPC distribution.

cpc_circ_var

Real

1

Circular variance of CPC distribution (=1-length of circular mean).

cpc_circ_std

Real

1

Circular standard deviation of CPC distribution.

cpc_circ_disp

Real

1

Circular dispersion of CPC distribution.

cpc_zipf

Real

1

Zipf coefficient of CPC distribution.

cpc_entropy

Real

1

Normalized entropy of CPC distribution.

Chordal Pitch Class Distribution
Description: Histogram and raw vector of chordal pitch classes (CPC).

Feature Definition File Name: CPC_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

cpc_raw

Integer [0:11]

N

Raw output (CPC values of all melody notes).

cpc_raw_all

Integer [-1:11]

N

Raw output (CPC values of all melody notes, including undefined CPCs, set to -1).

cpc_hist_bins

Integer [0:11]

12

Histogram bins.

cpc_hist_densities

Real

12

Histogram bin count (absolute frequencies).

Pitch Distribution
Description: Histogram and raw vector of raw MIDI pitches.

Feature Definition File Name: PITCH_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

pitch_raw

Integer [0:127]

N

Raw output (values of all melody notes).

pitch_hist_values

Integer [0:127]

128

Histogram bins.

pitch_hist_counts

Real

128

Histogram bin counts (abs. frequencies).

Chordal Pitch Class Circle Map Features (Experimental)
Description: Histogram for Chordal Pitch Class Circle Map (N=12) unigrams and bigrams (occurrence and transition probabilites).

Feature Definition File Name: CPCCM_HIST

Category: Pitch

Included Features:

Label

Type

Length

Description

cpccm_unigram_values

Array of Integer [0:11]

12

Histogram bins (CPCCM:12 values).

cpccm_unigram_freqs

Real [0,1]

12

Histogram bin densities (CPCCM:12 values).

cpccm_bigram_values

Array of Integer

Var

Histogram bins (all unique CPCCM bigrams).

cpccm_bigram_freqs

Real [0,1]

Var

Histogram bin densities (all unique CPCCM bigrams).

Rhythm
Variability Indices (Duration)
Description: Normalized pairwise variability index, which measures the mean contrast of adjacents durations. The formula is \frac{1}{N-1}\sum*{i=1}^{N-1} 2\left| \frac{d*{i+1}-d*{i}}{d*{i+1}+d*{i}}\right|. It is the mean of the absolute value of ratios of duration difference to duration mean. This index originated in linguistic and is sometimes used by rhythm researchers as a variability measure. The coefficient of variation is another common index for variability. It is defined as the ratio of standard deviation and mean. A simple biased estimator is the corresponding ratio of sample standard deviation and sample mean. The coefficient of variation is only sensical for ratio scales, which applies to durations since they only assum positive values. The formula is: c_V = \frac{\sigma(d*{i})}{\mu(d\_{i})}.

Feature Definition File Name: VI_DUR

Category: Rhythm

Included Features:

Label

Type

Length

Description

nPVI_dur

Real [0,1]

1

Normalized pairwise variability index.

CV_dur

Real

1

Coefficient of variation.

Microtiming Features
Description: Features related to micro-timing in a solo.

Feature Definition File Name: GENERAL_MICROTIMING

Category: Rhythm

Included Features:

Label

Type

Length

Description

swing_ratios

Real

Var

Swing ratios of beats with a binary sub-division as the ratio duration of the first to the second eighth in a beat. Straight binary eigths have a value of 1 (1:1), whereas triplet eighths get 2 and dotted eighths + sixteenth get 3:1.

mean_swing_ratio

Real

1

Mean value of swing ratios.

median_swing_ratio

Real

1

Median of swing ratios.

std_swing_ratio

Real

1

Standard deviation of swing ratio.

swing_shapes

Real

Var

Swing shapes are the loudness difference between first and second eighth in a beat with binary subdivision.

mean_swing_shape

Real

1

Mean value of swing shapes.

median_swing_shape

Real

1

Median of swing shapes.

std_swing_shape

Real

1

Standard deviation of swing shapes.

number_binary_beats

Real

1

Number of fully occupied binary beats.

proportion_binary_beats

Real

1

Proportion of fully occupied binary beats.

nominal_metrical_onsets

Real

N

Nominal metrical onsets according to metrical annotation and beat track.

diff_nominal_metrical_onsets

Real

N

Difference of onsets to nominal metrical onsets.

abs_diff_nominal_metrical_onsets

Real

N

Absolute difference of onsets to nominal metrical onsets.

Duration Ratios
Description: Raw vector of duration ratios as well as duration ratio classification (-1: shorter, 0: equal, +1: longer) using thresholds 1.49 and .81.

Feature Definition File Name: DURRATIO_HIST

Category: Rhythm

Included Features:

Label

Type

Length

Description

dur_ratios

Float

N-2

Raw output of duration ratios.

dur_ratio_classes

Integer [-1:1]

N-2

Classified duration ratios.

Inter-onset Interval Class Single Features
Description: Normalzed histogram counts, mode,entropy and Zipf coefficent for all 5 duration classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2). Reference time-span is either local beat duration (“relative mode”) or 0.5 sec (“absolute mode”).

Feature Definition File Name: IOICLASS_FEATURES

Category: Rhythm

Included Features:

Label

Type

Length

Description

ioiclass_abs_hist_01_very_short

Real

1

Relative frequency very short (absolute mode).

ioiclass_abs_hist_02_short

Real

1

Relative frequency short (absolute mode).

ioiclass_abs_hist_03_medium

Real

1

Relative frequency medium (absolute mode).

ioiclass_abs_hist_04_long

Real

1

Relative frequency long (absolute mode).

ioiclass_abs_hist_05_very_long

Real

1

Relative frequency very long (absolute mode).

ioiclass_rel_hist_01_very_short

Real

1

Relative frequency very short (relative mode).

ioiclass_rel_hist_02_short

Real

1

Relative frequency short (relative mode).

ioiclass_rel_hist_03_medium

Real

1

Relative frequency medium (relative mode).

ioiclass_rel_hist_04_long

Real

1

Relative frequency long (relative mode).

ioiclass_rel_hist_05_very_long

Real

1

Relative frequency very long (relative mode).

ioiclass_abs_mode

Real

Var

Mode of absolute inter-onset interval class distributions (can be list).

ioiclass_abs_entropy

Real

1

Entropy of absolute inter-onset interval class distributions.

ioiclass_abs_zipf

Real

1

Zipf coefficient of absolute durations class distributions.

ioiclass_rel_mode

Real

Var

Mode of relative inter-onset interval classdistributions (can be list).

ioiclass_rel_entropy

Real

1

Entropy of relative inter-onset interval class distributions.

ioiclass_rel_zipf

Real

1

Zipf coefficient of relative inter-onset interval class distributions.

Inter-onset Interval Class Distribution
Description: Histogram and raw vector of IOI classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2). Reference time-span is either local beat duration (“relative mode”) or 0.5 sec (“absolute mode”).

Feature Definition File Name: IOICLASS_HIST

Category: Rhythm

Included Features:

Label

Type

Length

Description

ioiclass_abs_raw

Integer

N

Raw output of IOI classes of all melody notes (absolute mode).

ioiclass_abs_hist_values

Integer [-2:2]

5

Histogram bin values (absolute mode).

ioiclass_abs_hist_dens

Integer

5

Histogram bin counts (absolute mode).

ioiclass_rel_raw

Integer

N

Raw output of IOI classes of all melody notes (relative mode).

ioiclass_rel_hist_values

Integer [-2:2]

5

Histogram bin values (relative mode).

ioiclass_rel_hist_counts

Integer

5

Histogram bin counts (relative mode).

Event Densities
Description: Events per second and per bar.

Feature Definition File Name: GENERAL_EVENT_DENSITY

Category: Rhythm

Included Features:

Label

Type

Length

Description

event_density

Real

1

Event density (notes per seconds).

total_duration

Real

1

Total duration in seconds.

metrical_event_density

Real

1

Event density (notes per bar). WARNING: Might not be working properly with meter changes.

total_duration_bar

Real

1

Total duration in fractional bar units (e.g., 6 Quarter notes in 4/4 timing are 1.5 bars long).

number_notes

Integer

1

Number of events.

Duration Class Single Features
Description: Normalized histogram counts, mode, entropy and Zipf cofficient for distribution if all 5 duration classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2) in relative and absolute mode. Reference duration is either local beat duration (‘relative mode’) or 0.5 sec (‘absolute mode’).

Feature Definition File Name: DURCLASS_FEATURES

Category: Rhythm

Included Features:

Label

Type

Length

Description

durclass_abs_hist_01_very_short

Real

1

Relative frequency very short.

durclass_abs_hist_02_short

Real

1

Relative frequency short.

durclass_abs_hist_03_medium

Real

1

Relative frequency medium.

durclass_abs_hist_04_long

Real

1

Relative frequency long.

durclass_abs_hist_05_very_long

Real

1

Relative frequency very long.

durclass_rel_hist_01_very_short

Real

1

Relative frequency very short.

durclass_rel_hist_02_short

Real

1

Relative frequency short.

durclass_rel_hist_03_medium

Real

1

Relative frequency medium.

durclass_rel_hist_04_long

Real

1

Relative frequency long.

durclass_rel_hist_05_very_long

Real

1

Relative frequency very long.

durclass_abs_mode

Real

Var

Mode of absolute duration class distributions (can be list).

durclass_abs_entropy

Real

1

Entropy of absolute duration class distributions.

durclass_abs_zipf

Real

1

Zipf coefficient of absolute duration class distributions.

durclass_rel_mode

Real

Var

Mode of relative duration class distributions (can be list).

durclass_rel_entropy

Real

1

Entropy of relative duration class distributions.

durclass_rel_zipf

Real

1

Zipf coefficient of relative duration class distributions.

Duration Class Distribution
Description: Histogram and raw vector of duration classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2). Reference duration is either local beat duration (‘relative mode’) or 0.5 sec (‘absolute mode’).

Feature Definition File Name: DURCLASS_HIST

Category: Rhythm

Included Features:

Label

Type

Length

Description

durclass_abs_raw

Integer

N

Raw output of duration classes (absolute mode).

durclass_abs_hist_values

Integer [-2:2]

5

Histogram bin values (absolute mode).

durclass_abs_hist_counts

Integer

5

Histogram bin counts (abs. frequencies, absolute mode).

durclass_rel_raw

Integer

N

Raw output of duration classes (relative mode).

durclass_rel_hist_values

Integer [-2:2]

5

Histogram bin values (relative mode).

durclass_rel_hist_counts

Integer

5

Histogram bin counts (abs. frequencies, relative mode).

Variability Indices (IOI)
Description: Normalized pairwise variability index, which measures the mean contrast of adjacents inter-onset intervals. The formula is \frac{1}{N-1}\sum*{i=1}^{N-1} 2\left| \frac{I*{i+1}-I*{i}}{I*{i+1}+I*{i}}\right|. It is the mean of the absolute value of ratios of IOI difference to IOI mean. This index originated in linguistic and is sometimes used by rhythm researchers as a variability measure. The coefficient of variation is another common index for variability. It is defined as the ratio of standard deviation and mean. A simple biased estimator is the corresponding ratio of sample standard deviation and sample mean. The coefficient of variation is only sensical for ratio scales, which applies to durations since they only assum positive values. The formula is: c_V = \frac{\sigma(I*{i})}{\mu(I\_{i})}.

Feature Definition File Name: VI_IOI

Category: Rhythm

Included Features:

Label

Type

Length

Description

nPVI_ioi

Real [0,1]

1

Normalized pairwise variability index.

CV_ioi

Real

1

Coefficient of variation.

IOI Ratios
Description: Raw vector of IOI ratios as well as IOI ratio classification (-1: shorter, 0: equal, +1: longer) using thresholds 1.49 and .81.

Feature Definition File Name: IOIRATIO_HIST

Category: Rhythm

Included Features:

Label

Type

Length

Description

ioi_ratios

Float

N-2

Raw output of IOI ratios.

ioi_ratio_classes

Integer [-1:1]

N-2

Classified IOI ratios.

Tempo Features
Description: Statistical descriptors of tempo distribution (mean, stddev, min, max, range) for inter-beat intervals (IBI) measured in seconds or BPM counts (beats per minute). BPM=60/IBI.

Feature Definition File Name: GENERAL_TEMPO

Category: Rhythm

Included Features:

Label

Type

Length

Description

mean_tempo

Real

1

Mean tempo of a melody measured in seconds (average IBI).

std_tempo

Real

1

Standard devitation of IBI distribution in seconds.

ibi_range

Real

1

Range of IBI distribution (max-min) in seconds.

ibi_min

Real

1

Minimum of IBI distribution (min) in seconds.

ibi_max

Real

1

Maximum of IBI distribution (max) in seconds.

mean_tempo_bpm

Real

1

Mean tempo of a melody measured in BPM (beats per minute, BPM = 60/IBI).

std_tempo_bpm

Real

1

Standard devitation of BPM distribution.

bpm_range

Real

1

Range (max.min) of BPM distribution.

bpm_min

Real

1

Minimum of BPM distribution.

bpm_max

Real

1

Maximum of BPM distribution.

beat_track

Real

Var

Raw annotated beat positions.

Sequence/Interval
Interval Class Bigrams
Description: Histogram features for intervals classes (IC) bigrams: all unique IC bigrams and all IC bigrams occurring at least twice.

Feature Definition File Name: INTCLASS_2GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

ic_bigram_values

Array of Integer

Var

Histogram bins (all unique IC bigrams).

ic_bigram_counts

Integer

Var

Histogram bin counts (all unique IC bigrams).

ic_bigram_patterns

Array of Integer

Var

Histogram bins (all unique IC bigrams occurring at least twice).

ic_bigram_pattern_counts

Integer

Var

Histogram bin counts (all unique IC bigrams occurring at least twice).

ic_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

ic_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Fuzzy Interval Trigrams
Description: Histogram features for fuzzy intervals (FUZZYINT, also known as refined contour) trigrams: all unique FUZZYINT trigrams and all FUZZYINT trigrams occurring at least twice.

Feature Definition File Name: FUZZYINT_3GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

fuzzyint_trigram_values

Array of Integer [-4:4]

Var

Histogram bins (all unique FUZZYINT trigrams).

fuzzyint_trigram_counts

Integer

Var

Histogram bin count (all unique FUZZYINT trigrams).

fuzzyint_trigram_pattern

Array of Integer [-4:4]

Var

Histogram bins (all unique FUZZYINT trigrams occurring at least twice).

fuzzyint_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique FUZZYINT trigrams occurring at least twice).

Average Run-lengths of arpeggios
Description: Run-lengths and means of arpeggios with intervals of size +3/+4 or -3/-4 (fuzzy interval classes leap up/down.).

Feature Definition File Name: ARPEGGIOS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_length_arpeggio_ascending

Real

1

Mean length of ascending arpeggios.

mean_length_arpeggio_descending

Real

1

Mean length of descending arpeggios.

mean_length_arpeggio

Real

1

Mean length of arpeggios (mixed up/down thirds).

Average Run-lengths of Chromatic passages
Description: Run-lengths and means of chromatic sequences with intervals of size +1 or -1.

Feature Definition File Name: STEP_SEQUENCES

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_length_step_ascending

Real

1

Mean length of ascending step passages.

mean_length_step_descending

Real

1

Mean length of descending step passages.

mean_length_step

Real

1

Mean length of step passages (up and down steps).

Fuzzy Interval Bigrams
Description: Histogram features for fuzzy intervals (FUZZYINT, also known as refined contour) bigrams: all unique FUZZYINT bigrams and all FUZZYINT bigrams occurring at least twice.

Feature Definition File Name: FUZZYINT_2GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

fuzzyint_bigram_values

Array of Integer [-4:4]

Var

Histogram bins (all unique FUZZYINT bigrams).

fuzzyint_bigram_counts

Integer

Var

Histogram bin count (all unique FUZZYINT bigrams).

fuzzyint_bigram_pattern

Array of Integer [-4:4]

Var

Histogram bins (all unique FUZZYINT bigrams occurring at least twice).

fuzzyint_bigram_pattern_counts

Integer

Var

Histogram bin count (all unique FUZZYINT bigrams occurring at least twice).

fuzzyint_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

fuzzyint_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Average Run-lengths of Chromatic Passages
Description: Run-lengths and means of chromatic sequences with intervals of size +1 or -1.

Feature Definition File Name: CHROMATIC_SEQUENCES

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_length_chromatic_ascending

Real

1

Mean length of ascending chromatic passages.

mean_length_chromatic_descending

Real

1

Mean length of descending chromatic passages.

mean_length_chromatic_mixed

Real

1

Mean length of chromatic passages (up and down combined).

Parson’s Code Bigrams
Description: Histogram features for Parson’s Code (PARSON) bigrams: all unique PARSON bigrams and all PARSON bigrams occurring at least twice.

Feature Definition File Name: PARSON_2GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

parson_bigrams_values

Array of Integer [-1:+1]

Var

Histogram bins (all unique PARSON bigrams).

parson_bigrams_hist

Integer

Var

Histogram bin count (all unique PARSON bigrams).

parson_bigrams_pattern

Array of Integer [-1:+1]

Var

Histogram bins (all unique PARSON bigrams occurring at least twice).

parson_bigrams_pat_freq

Integer

Var

Histogram bin count (all unique PARSON bigrams occurring at least twice).

parsons_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

parsons_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Percentage of Chromatic Passages
Description: Computes the percentage of chromatic passages (interval sequences with values +1 or -1 with at least three notes), in the set of all passages (sequences of constant interval).

Feature Definition File Name: INT_CHROMATIC_SEQUENCES_RATIO

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

ratio_chromatic_sequences

Real

1

Percentage of of chromatic passages.

Average Run-length of Parson’s Code Segments
Description: Means of run-length of segments of notes with constant interval direction.

Feature Definition File Name: PARSON_CONST_DIRECTION_AV_LEN

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_segment_length_constant_interval_direction

Real

1

Mean run-length of unisone sequences.

mean_segment_length_constant_positive_interval_direction

Real

1

Mean run-length of strictly ascending sequences.

mean_segment_length_constant_negative_interval_direction

Real

1

Mean run-length of strictly descending sequences.

Average Run-length of Chromatic Passages
Description: Mean run-length of sequences with intervals of size +1 or -1.

Feature Definition File Name: INT_CHROMATIC_SEQUENCES_AV_LEN

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_length_chromatic_sequences

Real

1

Mean run-length of chromatic passages.

Average Run-lengths of Parsons Sequences
Description: Run-lengths and means of sequences of all (Parson’s) intervals directions.

Feature Definition File Name: PARSON_SEQUENCES

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

mean_length_seq_ascending

Real

1

Mean length of ascending passages.

mean_length_seq_descending

Real

1

Mean length of descending passages.

mean_length_seq_repitition

Real

1

Mean length of repetitions.

Semitone Interval Trigrams
Description: Histogram features for semitone intervals (INT) trigrams: all unique INT trigrams and all INT trigrams occurring at least twice.

Feature Definition File Name: INT_3GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

int_trigram_values

Array of Integer

Var

Histogram bins (all unique INT trigrams).

int_trigram_counts

Integer

Var

Histogram bin counts (all unique INT trigrams).

int_trigram_patterns

Array of Integer

Var

Histogram bins (all unique INT trigrams occurring at least twice).

int_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique INT trigrams occurring at least twice).

Parson’s Code Trigrams
Description: Histogram features for Parson’s Code (PARSON) trigrams: all unique PARSON trigrams and all PARSON trigrams occurring at least twice.

Feature Definition File Name: PARSON_3GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

parson_3grams_values

Array of Integer [-1:+1]

Var

Histogram bins (all unique PARSON trigrams).

parson_3grams_hist

Integer

Var

Histogram bin count (all unique PARSON trigrams).

parson_3grams_pattern

Array of Integer [-1:+1]

Var

Histogram bins (all unique PARSON trigrams occurring at least twice).

parson_3grams_pat_freq

Integer

Var

Histogram bin count (all unique PARSON trigrams occurring at least twice).

Semitone Interval Bigrams
Description: Histogram features for semitone intervals (INT) bigrams: all unique INT bigrams and all INT bigrams occurring at least twice.

Feature Definition File Name: INT_2GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

int_bigram_values

Array of Integer

Var

Histogram bins (all unique INT bigrams).

int_bigram_counts

Integer

Var

Histogram bin counts (all unique INT bigrams).

int_bigram_patterns

Array of Integer

Var

Histogram bins (all unique INT bigrams occurring at least twice).

int_bigram_pattern_counts

Integer

Var

Histogram bin counts (all unique INT bigrams occurring at least twice).

int_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

int_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Interval Class Trigrams
Description: Histogram features for interval class (IC) trigrams: all unique IC trigrams and all IC trigrams occurring at least twice.

Feature Definition File Name: INTCLASS_3GRAMS

Category: Sequence/Interval

Included Features:

Label

Type

Length

Description

ic_trigram_values

Array of Integer

Var

Histogram bins (all unique IC trigrams).

ic_trigram_counts

Integer

Var

Histogram bin counts (all unique IC trigrams).

ic_trigram_patterns

Array of Integer

Var

Histogram bins (all unique IC trigrams occurring at least twice).

ic_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique IC trigrams occurring at least twice).

Sequence/Pitch
Pitch Class Bigrams
Description: Histogram features for pitch class (PC) bigrams: all unique PC bigrams and all PC bigrams occurring at least twice.

Feature Definition File Name: PC_2GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

pc_2grams_values

Array of Integer [0:11]

Var

Histogram bins (all unique PC bigrams).

pc_2grams_hist

Integer

Var

Histogram bin count (all unique PC bigrams).

pc_2grams_pattern

Array of Integer [0:11]

Var

Histogram bins (all unique PC bigrams occurring at least twice).

pc_2grams_pat_freq

Integer

Var

Histogram bin count (all unique PC bigrams occurring at least twice).

pc_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

pc_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Chordal Diatonic Pitch Class Trigrams
Description: Histogram features for Chordal Diatonic Pitch Class (CDPC) trigrams: all unique CDPC trigrams and all CDPC trigrams occurring at least twice.

Feature Definition File Name: CDPC_3GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

cdpc_trigrams

List of Strings

Var

Histogram bins (all unique CDPC 3-grams).

cdpc_trigram_counts

Integer

Var

Histogram bin count (all unique CDPC 3-grams).

cdpc_trigram_pattern

List of String

Var

Histogram bins (all unique CDPC 3-grams occurring at least twice).

cdpc_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique CDPC 3-grams occurring at least twice).

Chordal Diatonic Pitch Class Bigrams
Description: Histogram features for Chordal Diatonic Pitch Class (CDPC) bigrams: all unique CDPC bigrams and all CDPC bigrams occurring at least twice.

Feature Definition File Name: CDPC_2GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

cdpc_bigrams

String

Var

Histogram bins (all unique CDPC bigrams).

cdpc_bigram_counts

String

Var

Histogram bin counts (all unique CDPC bigrams).

cdpc_bigram_patterns

String

Var

Histogram bins (all unique CDPC bigrams occurring at least twice).

cdpc_bigram_pattern_counts

Integer

Var

Histogram bin counts (all unique CDPC bigrams occurring at least twice).

cdpc_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

cdpc_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Pitch Class Trigrams
Description: Histogram features for pitch class (PC) trigrams: all unique PC trigrams and all PC trigrams occurring at least twice.

Feature Definition File Name: PC_3GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

pc_3grams_values

Array of Integer [0:11]

Var

Histogram bins (all unique PC trigrams).

pc_3grams_hist

Integer

Var

Histogram bin count (all unique PC trigrams).

pc_3grams_pattern

Array of Integer [0:11]

Var

Histogram bins (all unique PC trigrams occurring at least twice).

pc_3grams_pat_freq

Integer

Var

Histogram bin count (all unique PC trigrams occurring at least twice).

Tonal Pitch Class Bigrams
Description: Histogram features for raw MIDI pitch (TPC) bigrams: all unique TPC bigrams and all TPC bigrams occurring at least twice.

Feature Definition File Name: TPC_2GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

tpc_bigrams_values

Array of Integer [0:11]

Var

Histogram bins (all unique TPC bigrams).

tpc_bigrams_hist

Integer

Var

Histogram bin count (all unique TPC bigrams).

tpc_bigrams_pattern

Array of Integer [0:11]

Var

Histogram bins (all unique TPC bigrams occurring at least twice).

tpc_bigrams_pat_freq

Integer

Var

Histogram bin count (all unique TPC bigrams occurring at least twice).

tpc_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

tpc_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Pitch Bigrams
Description: Histogram features for raw MIDI pitch (PITCH) bigrams: all unique PITCH bigrams and all PITCH bigrams occurring at least twice.

Feature Definition File Name: PITCH_2GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

pitch_bigrams_values

Array of Integer [0:127]

Var

Histogram bins (all unique PITCH bigrams).

pitch_bigrams_hist

Integer

Var

Histogram bin count (all unique PITCH bigrams).

pitch_bigrams_pattern

Array of Integer [0:127]

Var

Histogram bins (all unique PITCH bigrams occurring at least twice).

pitch_bigrams_pat_freq

Integer

Var

Histogram bin count (all unique PITCH bigrams occurring at least twice).

pitch_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

pitch_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Pitch Pattern Lengths and Distances
Description: Average length and occurrence distance between exact pitch patterns. Uses the edit distance based self-similarity matrix alogorithm.

Feature Definition File Name: PITCH_PATTERN_DIST_LEN_FEATURES

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

mean_pattern_length

Real

1

Mean length of exact pitch patterns.

mean_pattern_distance

Real

1

Mean distance between exact pitch patterns.

Pitch Trigrams
Description: Histogram features for raw MIDI pitch (PITCH) trigrams: all unique PITCH trigrams and all PITCH trigrams occurring at least twice.

Feature Definition File Name: PITCH_3GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

pitch_3grams_values

Array of Integer [0:127]

Var

Histogram bins (all unique PITCH trigrams).

pitch_3grams_hist

Integer

Var

Histogram bin count (all unique PITCH trigrams).

pitch_3grams_pattern

Array of Integer [0:127]

Var

Histogram bins (all unique PITCH trigrams occurring at least twice).

pitch_3grams_pat_freq

Integer

Var

Histogram bin count (all unique PITCH trigrams occurring at least twice).

Chordal Pitch Class Bigrams
Description: Histogram features for Chordal Pitch Class (CPC) bigrams: all unique CPC bigrams and all CPC bigrams occurring at least twice.

Feature Definition File Name: CPC_2GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

cpc_bigrams

String

Var

Histogram bins (all unique CPC bigrams).

cpc_bigram_counts

String

Var

Histogram bin counts (all unique CPC bigrams).

cpc_bigram_patterns

String

Var

Histogram bins (all unique CPC bigrams occurring at least twice).

cpc_bigram_pattern_counts

Integer

Var

Histogram bin counts (all unique CPC bigrams occurring at least twice).

cpc_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

cpc_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Tonal Pitch Class Trigrams
Description: Histogram features for tonal pitch class (TPC) trigrams: all unique TPC trigrams and all TPC trigrams occurring at least twice.

Feature Definition File Name: TPC_3GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

tpc_3grams_values

Array of Integer [0:11]

Var

Histogram bins (all unique TPC trigrams).

tpc_3grams_counts

Integer

Var

Histogram bin count (all unique TPC trigrams).

tpc_3grams_pattern

Array of Integer [0:11]

Var

Histogram bins (all unique TPC trigrams occurring at least twice).

tpc_3grams_pattern_counts

Integer

Var

Histogram bin count (all unique TPC trigrams occurring at least twice).

Chordal Pitch Class Trigrams
Description: Histogram features for Chordal Pitch Class (CPC) trigrams: all unique CPC trigrams and all CPC trigrams occurring at least twice.

Feature Definition File Name: CPC_3GRAMS

Category: Sequence/Pitch

Included Features:

Label

Type

Length

Description

cpc_trigrams

List of Strings

Var

Histogram bins (all unique CPC 3-grams).

cpc_trigram_counts

Integer

Var

Histogram bin count (all unique CPC 3-grams).

cpc_trigram_pattern

List of String

Var

Histogram bins (all unique CPC 3-grams occurring at least twice).

cpc_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique CPC 3-grams occurring at least twice).

Sequence/Rhythm
Duration Class Bigrams
Description: Histogram features for (absolute) duration classes (DURCLASS) bigrams: all unique DURCLASS bigrams and all DURCLASS bigrams occurring at least twice.

Feature Definition File Name: DURCLASS_2GRAMS

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

durclass_bigrams

String

Var

Histogram bins (all unique DURCLASS bigrams).

durclass_bigram_counts

Integer

Var

Histogram bin count (all unique DURCLASS bigrams).

durclass_bigram_pattern

String

Var

Histogram bins (all unique DURCLASS bigrams occurring at least twice).

durclass_bigram_pattern_count

Integer

Var

Histogram bin count (all unique DURCLASS bigrams occurring at least twice).

durclass_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

durclass_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Duration Class Trigrams
Description: Histogram features for (absolute) duration classes (DURCLASS) trigrams: all unique DURCLASS trigrams and all DURCLASS trigrams occurring at least twice. Reference time-span is 0.5s.

Feature Definition File Name: DURCLASS_3GRAMS

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

durclass_trigram_values

String

Var

Histogram bins (all unique DURCLASS trigrams).

durclass_trigram_hist

Integer

Var

Histogram bin count (all unique DURCLASS trigrams).

durclass_trigram_pattern

String

Var

Histogram bins (all unique DURCLASS trigrams occurring at least twice).

durclass_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique DURCLASS trigrams occurring at least twice).

Duration Class Run-lengths
Description: Mean run-length of duration classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2). Reference time-span is either local beat duration (“relative mode”) or 0.5 sec (“absolute mode”).

Feature Definition File Name: DURCLASS_RUNLENGTH

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

durclass_mean_seg_len

Real

1

Mean run-length averaged over all classes.

mean_seg_len_01_very_short

Real

1

Mean run-length for very short events.

mean_seg_len_02_short

Real

1

Mean run-length for short events.

mean_seg_len_03_medium

Real

1

Mean run-length for medium long events.

mean_seg_len_04_long

Real

1

Mean run-length for long events.

mean_seg_len_05_very_long

Real

1

Mean run-length for very long events.

seg_len

Integer

Var

Raw vector of run-lengths for all classes.

Inter-onset Interval Class Bigrams
Description: Histogram features for rel. IOI classes (IOICLASS) bigrams: all unique IOICLASS bigrams and all IOICLASS bigrams occurring at least twice.

Feature Definition File Name: IOICLASS_2GRAMS

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

ioiclass_bigrams

String

Var

Histogram bins (all unique IOICLASS bigrams).

ioiclass_bigram_counts

Integer

Var

Histogram bin count (all unique IOICLASS bigrams).

ioiclass_bigram_pattern

String

Var

Histogram bins (all unique IOICLASS bigrams occurring at least twice).

ioiclass_bigram_pattern_count

Integer

Var

Histogram bin count (all unique IOICLASS bigrams occurring at least twice).

ioiclass_bigram_entropy

Real

1

Unnormalized Entropy of bigram distribution in bits.

ioiclass_bigram_entropy_norm

Real [0,1]

1

Normalized Entropy of bigram distribution.

Inter-onset Interval Class Run-lengths
Description: Mean run-length of inter-onset interval classes (very short: -2, short: -1, medium: 0, long: 1, very long: 2). Reference time-span is either local beat duration (“relative mode”) or 0.5 sec (“absolute mode”).

Feature Definition File Name: IOICLASS_RUNLENGTH

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

aic_mean_seg_len

Real

1

Mean run-length averaged over all classes (absolute mode).

aic_mean_seg_len_01_very_short

Real

1

Mean run-length for very short events (absolute mode).

aic_mean_seg_len_02_short

Real

1

Mean run-length for short events (absolute mode).

aic_mean_seg_len_03_medium

Real

1

Mean run-length for medium long events (absolute mode).

aic_mean_seg_len_04_long

Real

1

Mean run-length for long events (absolute mode).

aic_mean_seg_len_05_very_long

Real

1

Mean run-length for very long events (absolute mode).

aic_seg_len

Integer

Var

Raw vector of run-lengths for all classes (absolute mode).

ric_mean_seg_len

Real

1

Mean run-length averaged over all classes (relative mode).

ric_mean_seg_len_01_very_short

Real

1

Mean run-length for very short events (relative mode).

ric_mean_seg_len_02_short

Real

1

Mean run-length for short events (relative mode).

ric_mean_seg_len_03_medium

Real

1

Mean run-length for medium long events (relative mode).

ric_mean_seg_len_04_long

Real

1

Mean run-length for long events (relative mode).

ric_mean_seg_len_05_very_long

Real

1

Mean run-length for very long events (relative mode).

ric_seg_len

Integer

Var

Raw vector of run-lengths for all classes (relative mode).

Inter-onset Interval Class Trigrams
Description: Histogram features for (absolute) IOI classes (IOICLASS) trigrams: all unique IOICLASS trigrams and all IOICLASS trigrams occurring at least twice. Reference time-span is 0.5s.

Feature Definition File Name: IOICLASS_3GRAMS

Category: Sequence/Rhythm

Included Features:

Label

Type

Length

Description

ioiclass_trigram_values

String

Var

Histogram bins (all unique IOICLASS trigrams).

ioiclass_trigram_hist

Integer

Var

Histogram bin count (all unique IOICLASS trigrams).

ioiclass_trigram_pattern

String

Var

Histogram bins (all unique IOICLASS trigrams occurring at least twice).

ioiclass_trigram_pattern_counts

Integer

Var

Histogram bin count (all unique IOICLASS trigrams occurring at least twice).

Structure
Form Structure of Phrases
Description: Calculates form strings based on self-similarity between phrases using edit distance based on interval and duration classes.

Feature Definition File Name: GENERAL_PHRASE_FORM

Category: Structure

Included Features:

Label

Type

Length

Description

form_by_interval

String

1

Phrase form structure based on self-similarity matrix of interval edit distances.

form_by_durclass

String

1

Phrase form structure based on self-similarity matrix of duration class edit distances.

Self-similarity Features
Description: Features derived from self similarity-matrix between phrases. These are basically statistical descriptors (max, median, stddev, range, entropy) either of the set of adjacent or non-adjacent cells in the self-similarity matrix. For instance, a high median of adjacent cells could indicate developing variation, the same value for non-adjacent cells hints at long-range correlations, i.e. form thinking.

Feature Definition File Name: GENERAL_SELF_SIM_MATRIX_PHRASES_FEATURES

Category: Structure

Included Features:

Label

Type

Length

Description

adjacent_phrase_similarity_max

Real [0,1]

1

Maximum of adjacent similarity values.

adjacent_phrase_similarity_median

Real [0,1]

1

Median of adjacent similarity values.

adjacent_phrase_similarity_std

Real [0,1]

1

Standard deviaation of adjacent similarity values.

adjacent_phrase_similarity_range

Real [0,1]

1

Range of adjacent similarity values.

adjacent_phrase_similarity_entropy

Real [0,1]

1

Entropy of adjacent similarity values.

nonadjacent_phrase_similarity_median

Real [0,1]

1

Median of non-adjacent similarity values.

nonadjacent_phrase_similarity_std

Real [0,1]

1

Standard deviation of non-adjacent similarity values.

nonadjacent_phrase_similarity_range

Real [0,1]

1

Range of non-adjacent similarity values.

nonadjacent_phrase_similarity_entropy

Real [0,1]

1

Maximum of adjacent similarity values.

Self-similarity Matrix of Phrases
Description: Similarity between phrases using edit distance based similarity on pitch values.

Feature Definition File Name: GENERAL_SELF_SIM_MATRIX_PHRASES

Category: Structure

Included Features:

Label

Type

Length

Description

ssm

Real [0,1]

N_P \times N_P

Interval-based self-similarity matrix of phrases.

ssm_thresh

Real [0,1]

N_P \times N_P

Thresholded interval-based self-similarity matrix of phrases.

Tone Formation
Loudness
Description: Loudness (resp. intensity) related values for single tone events have been extracted from jazz solos by means of sophisticated MIR techniques and are stored in the WJazzD SQLITE database. Currently, five different values are available: Maximum, median and standard deviation of loudness, relative position of loudness peak and temporal centroid. Might not be avaibable for every solo.

Feature Definition File Name: GENERAL_LOUDNESS

Category: Tone Formation

Included Features:

Label

Type

Length

Description

loudness_max

Float [-120, 0]

N

Maximum loudness values per tone.

loudness_med

Real [-120, 0]

N

Median loudness values per tone.

loudness_sd

Real

N

Standard deviation of loudness per tone.

loudness_rel_peak_pos

Real [0, 1]

N

Relative position of maximum loudness value, duration of tone equals 1.

loudness_temp_cent

Real [0, 1]

N

Normed temporal centroid of loudness curve per tone, duration of tone equals 1.

loudness_s2b

Real

N

Ratio of solo loudness (median) to backing track loudness (median).

Articulation
Description: Articulation of notes as measured by the ratio of duration and inter-onset interval. (Be careful at phrase endings, though). The higher the ratio, the more legato, the lower the ratio, the more staccato.

Feature Definition File Name: GENERAL_ARTICULATION

Category: Tone Formation

Included Features:

Label

Type

Length

Description

ioi_raw

Real

N-1

Raw interonset-interval values.

duration_raw

Real

N

Raw durations.

articulation_raw

Real

N-1

Ratios of durations to interonset-intervals.

art_mean

Real

1

Mean of articulation distribution.

art_median

Real

1

Median of articulation distribution.

art_var

Real

1

Variance of of articulation distribution.

art_std

Real

1

Standard deviation of articulation distribution.

art_min

Real

1

Minimum of of articulation distribution.

art_max

Real

1

Maximum of of articulation distribution.

art_range

Real

1

Range of of articulation distribution.

Modulation
Description: F0-modulation of notes. Possible annoated values are fall-off, slide, vibrato, bend, straight, or an empty string, which might indicate that either no modulation is present or that no articulation was annotated. There are furthermore three automatically extracted value available: f0_mod_range_cents (Modulations in cents), f0_mod_freq_hz (Modulation frequency in Hz), f0_median_dev (Median devation from nominal 12TET pitch in cents).

Feature Definition File Name: GENERAL_F0MODULATION

Category: Tone Formation

Included Features:

Label

Type

Length

Description

modulation

String

N

Annonated modulation per tone.

modulation_short

String

N

Annonated modulation per tone (short label).

f0_mod_range_cents

Real

N

Extracted modulation range (cents).

f0_mod_freq

Real

N

Extracted modulation range (Hz).

f0_median_dev

Real

N

Extracted median deviation from nominal 12TET pitch (cents).
