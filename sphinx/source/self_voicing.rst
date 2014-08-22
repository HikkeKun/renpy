.. _self-voicing:

============
Self Voicing
============

Ren'Py supports a self-voicing mode in which a speech synthesizer is used
to read out text and other interface elements. This is intended to make
Ren'Py games accessible to the vision impaired.

The Self-voicing mode can be toggled by pressing the ``v`` key.

When in self-voicing mode, keyboard navigation is changed so that the
up and down arrow keys with iterate through all focusable displayables
on the screen.

When a displayable is focused, Ren'Py will read the text associated with that
displayable out loud. If no displayable is focused, Ren'Py will read on-screen
text that cannot be focused. This will generally include dialogue and other
text that comprises the game.

Speech Synthesis
----------------

Ren'Py relies on the operating system to provide speech synthesis
services. To adjust the speed of speech synthesis and the voice used,
adjust your platform's speech settings.

Windows
    On Windows, Ren'Py uses the Microsoft Speech API. Speech synthesis
    settings can  be changed on the "Text to Speech" tab of the "Speech
    Recognition" control panel.

Mac OS X
    On Mac OS X, Ren'Py uses the ``say`` command. Speech synthesis settings
    can be changed on the "Text to Speech" tab of the "Dictation & Speech"
    control panel.

Linux
    On Linux, Ren'Py uses the ``espeak`` command. Espeak may need to be
    installed using your package manager before self-voicing mode will
    work.

Android
    Self-voicing mode is not supported on Android

Creator Concerns
----------------

Ren'Py's self-voicing works by extracting text from displayables and
reading it to the player. Ren'Py extracts this text from two places.

Text displayables
    Ren'Py will extract text from a Text displayable, and make it
    available to be read to the player.

Alternative text
    Alternative text is supplied by a displayable's :propref:`alt` style
    property. It can also be supplied by actions supplied to buttons
    and values supplied to bars. Explicitly supplied alternative takes
    precedence over text supplied by actions or values, and both take
    precedence over text extracted from Text displayables.

    Alternative text is translated using Ren'Py's string translation
    mechanism. Alternative text takes precedence over text extracted
    from a displayable's children, but such child text is made
    available as the "[text]" string substitution. No other string
    substitutions are allowed.
