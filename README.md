As the first step in a small research project, I have been looking into automated transcription of recorded speech. What follows is merely notes on a published workflow by a sound engineer.

In summary, automated transcription from a recording works reasonably well (about 91% accuracy in a few tests), but my workflow requires use of several programs, one of which costs some money.

One small irritation is that you can't use your computer for anything else while the Dictation software is at work.

## Workflow

The workflow I used follows what is described in this [2013 post by Frank Lowney](http://telestreamblog.telestream.net/2013/12/using-dictation-to-turn-recorded-audio-to-text-2/) on Lucas Bischofberger's blog. Basic steps:

 1. Install Soundflower and Audio Hijack, to handle communication between the audio-playback application and Apple's Dictation tool. Together these allow the use of whatever audio-playback application you choose.
 1. Pipe audio output to Soundflower as "auxiliary device output" in Audio Hijack.
 1. Set both the input of Dictation tool and the output of main audio-playback application to Soundflower.
 1. For transcription from a recording, begin audio playback and then quickly turn on Dictation in a text editor that supports it.

Third-party software I used: Audio Hijack Pro (v. 2.11.6), Soundflower (v. 1.5.1), Audacity (v. 2.1.0), BBEdit (v. 11.5.2). Points for attention:

 1. **Audio Hijack** costs money and was necessary for the workflow. Efforts to circumvent the need for this tool failed.
 
 1. **Soundflower** is the actual driver that enables output from an audio-playback application to be piped to Dictation.
 
 1. **Audacity** is free and open-source, and it is helpful for editing recordings, increasing volume, adding seconds of silence at the start of the recording (ensures Dictation doesn't miss the start of the recording), and slowing down fast-talking interviewees. 
 
 1. **Dictation** is to be enabled in Apple's System Preferences (`Dictation & Speech` pane). That pane also allows use of a keyboard shortcut to start dictation,
 
 1. **BBEdit** is what I used for receiving the output of Dictation. It has a no-cost parallel release, **TextWrangler**. Both support Dictation (menu `Edit => Start Dictation…`). It is useful to be able to turn Dictation on very rapidly. My keyboard is old and doesn't have the key needed for Dictation's keyboard shortcut; instead, I assigned a key-binding to the "`Start Dictation…`" menu command in BBEdit (`Preferences => Menus & Shortcuts`). 
 
 1. **Operating system**. I am on Apple OS 10.9.5. I don't know whether or not Soundflower works on later versions of the OS.
 
 1. **Hardware**. When recording the sample text, I used a headset to ensure clarity. I honestly have no idea whether Apple's built-in microphone will do better or worse for this purpose; Dictation may well be optimized for use with that hardware. 
 
 1. Transcription takes place in real time, so an hour-long interview will take about an hour to transcribe. The computer apparently can't be used for any other tasks that might alter focus from the text editor.
 
 1. Apple's Dictation functionality doesn't produce identical transcriptions on multiple runs, even from the same original recording. Under "Transcription", below, are examples, all from the same original recording.
 
 1. Comparing the original text to the transcription, by use of Python's `Difflib` library:
 
 
    ```python
    difflib.SequenceMatcher(isjunk=None, string_1, string_2, autojunk=False).ratio()
    ```

    the average "accuracy" is about 91% for the examples shown here, with QuickTime doing slightly worse in the two cases where the speed of the recording was changed.

## Data

The original text I read from: 

> There are those who consider that studies in harmony, counterpoint, and fugue are the exclusive province of the intended composer. But if we reflect that theory must follow practice, rarely preceding it except by chance, we must realize that musical theory is not a set of directions for composing music. It is rather the collected and systematized deductions gathered by observing the practice of composers over a long time, and it attempts to set forth what is or has been their common practice. It tells not how music will be written in the future, but how music has been written in the past. — Walter Piston, Introduction to _Harmony_ (1941)

The recordings I used, edited to remove a garbled word and with five seconds of silence prepended, are also present in this repository.

## Transcription

### Transcription by Dictation of original recording, speed unchanged

#### Audacity (v. 2.1.0) playback:

 1. > There are those who consider that studies in harmony counterpoint a few of the exclusive province of the intended conference but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's wrapping the collected and systematize deductions gathered by observing the practice of composers over a long time and it is something that it attempts to set forth what is or has been there coming practice the tells not how music share but how music has been written in the past Walter piston introduction to Harmony making 41

 1. > There are those who consider that studies in harmony counterpoint in a few of the exclusive province of the intended components but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's wrapping the collected and systematize deductions gathered by observing the practice of composers over long time and it is something that it attempts to set forth what is or has been there coming practice the tells not how music sure but how music has been written in the past Walter piston introduction to Harmony making 41

 1. > There are those who consider that studies in harmony counterpoint in a few of the exclusive province of the intended components but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's rather the collected and systematize deductions gathered by observing the practice of composers over long time and it is something that it attempts to set forth what is or has been there coming practice the tells not how music share but how music has been written in the past Walter piston introduction to Harmony making 41

#### QuickTime (v. 10.3) playback:

 1. > There are those who consider that studies in harmony counterpoint a few are the exclusive province of the intended but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's routing the collected and systematize deductions gathered by observing the practice of composers overlong hot and it attempts to set forth what is old has been there common practice it tells not how music but how music has been written in the past is the introduction to Harmony

 1. > There are those who consider that studies in harmony counterpoint a few are the exclusive province of the intended but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's rocking the collected and systematize deductions gathered by observing the practice of composers over Time and it attempts to set forth what is old has been there common practice it tells not how music but how music has been written in the past is the production harmony

 1. > There are those who consider that studies in harmony counterpoint you are the exclusive province of the intended components but if they reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's wrapping the collected and systematize deductions gathered by observing the practice of composers overwhelmed by and it attempts to set forth what is old has been there coming practice details not how music but how music has been written in the past is the introduction to Harmony

### Transcription by Dictation of original recording, slowed 15%

#### Audacity (v. 2.1.0) playback:

> There are those who consider that studies in harmony counterpoint a few are the exclusive province of the intended components but if we reflect that theory must follow practice rarely proceeding it except by chance we must realize that musical theory is not a set of directions for composing music it's robbing the collected and systematized productions gathered by observing the practice of composers over long time but it attempts to set forth what is rule has been there, practice it tells not how music chair but how music has been written in the past is introduction to Harmony biking 41

#### QuickTime (v. 10.3) playback:

> There are those who consider the studies and harmony counterpoint a few are the exclusive province of the intended but if we reflect back theory must follow practice rarely proceeding except for chance we must realize that musical theory is not a set of directions for composing music it's Robin the collective and systematize productions gathered by observing the practice of composers fool talk and it attempts to set forth what is role has been there, practice it tells not how music but how music has been written in the past is the production harmony

### Transcription by Dictation of original recording, sped up 15%

#### Audacity (v. 2.1.0) playback:

> There are those who consider that studies in harmony counterpoint if you are the exclusive province of the intended but if they reflect that theory must follow practice rarely proceeding by chance we must realize that musical theory is not a set of directions for composing music it's rather the collected and systematize deductions gathered budgeting the practice of composers over a long time any attempt to set forth what is has been there come practice it tells not how music but her music has been written in the past what is the introduction to Harmony

#### QuickTime (v. 10.3) playback:

> There are those who consider that studies in harmony counterpoint if you are the exclusive province of the intended but if they reflect that theory must follow practice rarely proceeding into a chance we must realize that musical theory is not a set of directions for composing music it's rather the collected and systematize deductions gathered budgeting the practice of composers over Time and attempt to set forth what is O has been there compact it tells not how music but her music has been written in the past is the introduction to Harmony

[end]
