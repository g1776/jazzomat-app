---
description: Load these instructions when asked about the Jazzomat database
# applyTo: 'Load these instructions when asked about the Jazzomat database' # when provided, instructions will automatically be added to the request context when the pattern matches an attached file
---

# SQL database information (wjazzd.db)

The database is designed to hold different melody types, which basically differ only in the available metadata. The type of a melody is stored in the table melody_type (Table: melody_type). Currently three types are supported: Weimar Jazz Database (WJD), EsAC and POP-type. The first types are used in the WJD and the EsAC-DB deployed with the MeloSpySuite/GUI. POP songs are implemented for future use.

WJD type melodies use the tables transcription_info (Table: transcription_info (WJD)), record_info (Table: record_info (WJD)), composition_info (Table: composition_info (WJD)) and solo_info (Table: solo_info (WJD)) for meta data. The structure of the metadata reflects the fact that a solo is part of some track, which can contain more than one solo. Tracks are contained on some record, which can contain several tracks with solos included in the WJD. Atrack and hence each solo taken from this track is based on some composition, which might be also used for other tracks, e.g., a jazz standard such as “Body and Soul”.

EsAC-type melodies use esac_info (Table: esac_info (ESAC)), which contains the metadata originally used for EsAC folk songs. POP song type melodie use (Table: popsong_info (POP)) for storing rather sparse metadata for pop songs. In future, there might be an extension or alternative solution to this. For EsAC and POP melodies, only phrase sections in table sections (Table: sections) are used.

The beats table (Table: beats (WJD)) is solely used for WJD-type melodies to store (tapped) beats along with chord, form, bass pitch and other annotations.

Description of SQLite3 database tables
Table: Overview of tables
Table name

Description

beats

Table for beat annotation of WJD melodies, referenced by melody(melid)

composition_info

Infos regarding the underlying composition of a WJD solo, referenced by melody(melid)

db_info

Information regarding the distributed database file like version information, license, etc

esac_info

EsAC infos for EsAC melodies, referenced by melody(melid)

melody

Main table for all melody events

melody_type

Indicated type of melody: WJD solos or EsAC (Folk songs using Essen Associative Code), referenced by melody(melid)

popsong_info

Pop song infos, referenced by melody(melid)

record_info

Infos regarding the specific audio recording of a WJD solo was taken from, referenced by melody(melid)

sections

All sections (phrase, chorus, form, chords, etc.), referenced by melody(melid)

solo_info

Solo infos for WJD solos, referenced by melody(melid)

track_info

Information specific to a track on a record (or CD)

transcription_info

Transcription infos for WJD solos, referenced by melody(melid)

Table: beats (WJD)
Field

Type

Description

beatid

INTEGER

Unique ID of beat event, PRIMARY KEY

melid

INTEGER

References melody(melid)

onset

REAL

Onset (in secs) of beat

bar

INTEGER

Number of bar

beat

INTEGER

Number of beat in a bar

signature

TEXT

Signature of this and all subsequent beats and bars, resp.

chord

TEXT

Accompanying chord

form

TEXT

Form part of this and all subsequent beats (e.g. A1, B2)

bass_pitch

INTEGER

Bass pitch (fractional MIDI) of the beat

chorus_id

INTEGER

Number of chorus this and all subsequent beats are belonging to

Table: composition_info (WJD)
Field

Type

Description

compid

INTEGER

Unique ID of composition_info, PRIMARY KEY

title

TEXT

Title of the composition

composer

TEXT

Composer(s) of the underlying tune

form

TEXT

Basic form the song (e.g. AABA), including labels and length (in bars)

template

TEXT

Template

tonalitytype

TEXT

Tonality type of the song. Possible values: FUNCTIONAL, BLUES, JAZZ-BLUES, MODAL, COLOR, FREE. See Tonality Type for more information.

genre

TEXT

Genre of the solo. Possible values: TRADITIONAL, BLUES, GREAT AMERICAN SONGBOOK, WORMS, ORIGINAL, RIFF. See Genre for more information.

Table: db_info
Field

Type

Description

name

TEXT

Descriptive name for the database

creator

TEXT

Person/project who created the database

major

INTEGER

Major version of database schema

minor

INTEGER

Minor version of database schema

release

TEXT

Release version of database content

created

TEXT

Date and time of the creation of the database

license

TEXT

License text

status

TEXT

Current status of the database content. (Possible values: FINAL, PREFINAL)

Table: esac_info (ESAC)
Field

Type

Description

melid

INTEGER

References melody(melid)

collection

TEXT

Folk song collection of an EsAC-type melody (orignally first line in a EsAC file)

title

TEXT

Title of an EsAC-type melody (orignal CUT-field)

esacid

TEXT

Original EsAC ID of an EsAC-type melody

key

TEXT

Original key of an EsAC-type melody (from KEY-field)

unit

TEXT

Original base rhythmical unit for of an EsAC-type melody (from KEY-field)

signature

TEXT

Original signature of an EsAC-type melody (from KEY-field)

region

TEXT

Original REG-field of an EsAC-type melody

function

TEXT

Original FCT/FKT-field of an EsAC-type melody

comment

TEXT

Original CMT-field of an EsAC-type melody

source

TEXT

Original SRC-field of an EsAC-type melody

cnr

TEXT

Original CNR-field of an EsAC-type melody

tunefamily

TEXT

Deducted tune family of an EsAC-type melody (derived from orignal EsAC ID)

text

TEXT

Original TEXT-field of an EsAC-type melody

melstring

TEXT

Original MEL-field of an EsAC-type melody

lcm_tatum

INTEGER

Least common multiple of all beat divisions

Table: melody
Field

Type

Description

eventid

INTEGER

Unique ID of a melody event, PRIMARY KEY, Event IDs must be incrementally increasing with respect to the onsets of the melody they belong to.

melid

INTEGER

Unique ID of the melody containing the event

onset

REAL

Onset (in sec) of the event

pitch

REAL

Pitch (fractional MIDI) of the event

duration

REAL

Duration (in sec) of the event

period

INTEGER

Period of the metrical context of the event

division

INTEGER

Division of current beat of the event

bar

INTEGER

Bar number of the event

beat

INTEGER

Beat number of the event

tatum

INTEGER

Tatum number of the event

subtatum

INTEGER

Subtatum number of the event

num

INTEGER

Numerator of orginal signature of the metrical context of the event

denom

INTEGER

Denominator of orginal signature of the metrical context of the event

beatprops

TEXT

Beat proportions of the metrical context of the event. Text of form '('<int>'+')+<int>')' or None.

beatdur

REAL

Duration of the current beat (in secs)

tatumprops

TEXT

Tatum proportions of the current beat. Text of form '('<real>',')+<real>')' or None.

loud_max

REAL

Maximum of loudness per tone

loud_med

REAL

Median of loudness per tone

loud_sd

REAL

Standard deviation of loundess per tone

loud_relpos

REAL

Relative position of loudness peak

loud_cent

REAL

Normalized temporal centroid of loudness per tone

loud_s2b

REAL

Signal-to-background ratio of loudness

f0_mod

TEXT

Annonated modulation per tone. One of the following values vibrato, fall-off, bend, slide, or empty string

f0_range

REAL

Modulation range in cents

f0_freq_hz

REAL

Modulation frequency in Hertz

f0_med_dev

REAL

Median deviation of the fundamental frequency from standard 12-tone equal tempered pitch (corrected for overall tuning)

Table: melody_type
Field

Type

Description

melid

INTEGER

References melody(melid)

type

TEXT

Type of melody. Valid types: ESAC, SOLO, SV.

Table: popsong_info (POP)
Field

Type

Description

melid

INTEGER

References melody(melid)

artist

TEXT

Name of the artist

title

TEXT

Title of the song

avgtempo

REAL

Average tempo (BPM) of the solo as determined by the Sonic Visualiser project file

tempoclass

TEXT

Rough classification of tempo of the solo. Possible values. SLOW, MEDIUM SLOW, MEDIUM, MEDIUM UP, UP. See Tempo Classes for more information.

signature

TEXT

Signature(s) of the solo.

key

TEXT

Key of the solo (if applicable) or tonal center. See Key for more information.

filename

TEXT

Filename of melody source

chordchanges

TEXT

Chord changes

year

INTEGER

Year

country

TEXT

Country of artist/performer

style

TEXT

Style/genre of the song

Table: record_info (WJD)
Field

Type

Description

recordid

INTEGER

Unique ID of record_info, PRIMARY KEY

artist

TEXT

Name of the artist of the record containing the track with the solo

recordtitle

TEXT

Title of the record containing the track with the solo

label

TEXT

Record label

recordbib

TEXT

Discographic entry for the record

mbzid

TEXT

MusicBrainz Identifier for the track containing the solo

releasedate

TEXT

Date of release of the record

Table: sections
Field

Type

Description

melid

INTEGER

References melody(melid)

type

TEXT

Type of section. Valid types: PHRASE, CHORD, FORM, CHORUS, KEY for WJD type melodies, PHRASE for EsAC and POP type melodies.

start

INTEGER

ID of first event in section (relative to the corresponding melody, not melody(eventid)!)

end

INTEGER

ID of last event in section (relative to the corresponding melody, not melody(eventid)!)

value

TEXT

Value of section. Valid values are : PHRASE:integer, CHORD: chord label, FORM: form label, CHORUS: integer, KEY: Key label.

Table: solo_info (WJD)
Field

Type

Description

melid

INTEGER

References melody(melid)

trackid

INTEGER

References track_info(trackid)

compid

INTEGER

References composition_info(compid)

recordid

INTEGER

References record_info(recordid)

performer

TEXT

Performer for WJD type melodies

title

TEXT

Title of tune for WJD type melodies

titleaddon

TEXT

Additional information appended to the title

solopart

INTEGER

Number of solo of corresponding track

instrument

TEXT

Instrument used in the solo

style

TEXT

Style of the solo. Possible values: TRADITIONAL, SWING, BEBOP, COOL, HARDBOP, POSTBOP, FREE, FUSION, OTHER, MIX. See Style for more information.

avgtempo

FLOAT

Average tempo (BPM) of the solo as determined by the beat track of the Sonic Visualiser project file

tempoclass

TEXT

Rough classification of tempo of the solo. Possible values. SLOW, MEDIUM SLOW, MEDIUM, MEDIUM UP, UP. See Tempo Classes for more information.

rhythmfeel

TEXT

Basic rhythmic groove of the solo. Possible values: TWOBEAT, SWING, BALLAD, LATIN, FUNK. See Rhythm Feel for more information.

key

TEXT

Key of the solo (if applicable) or tonal center. See Key for more information.

signature

TEXT

Signature(s) of the solo

chord_changes

TEXT

Chord changes of solo (as a compact string, as defined by one chorus)

chorus_count

INTEGER

Number of choruses played

Table: track_info (WJD)
Field

Type

Description

trackid

INTEGER

Unique ID of track_info, PRIMARY KEY

compid

INTEGER

References composition_info(compid)

recordid

INTEGER

References record_info(recordid)

filename_track

TEXT

Filename of the track

lineup

TEXT

Lineup

mbzid

TEXT

MusicBrainz Identifier for the track containing the solo

trackno

INTEGER

Number of the track on the record

recordingdate

TEXT

Date of recording

Table: transcription_info (WJD)
Field

Type

Description

melid

INTEGER

References melody(melid)

trackid

INTEGER

References track_info(trackid)

filename_sv

TEXT

Name of the originating Sonic Visualiser file for WJD type melodies

filename_solo

TEXT

Name of the solo cut from the original track (internal use only)

solotime

TEXT

Start/Endtime of the solo in the original track; Format mm:ss-mm:ss

solostart_sec

FLOAT

Start of the solo in seconds with nanoseconds resolution

status

TEXT

Status of the Sonic Visualiser file. Valid values: ASSIGNED, DRAFT, PREFINAL, FINAL.
