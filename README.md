Subtitle Edit Help/FAQ
========

* * *

  

Mini FAQ
--------

Q: When I try to open a video in format "...", SE cannot play video or there's no sound. What do I do?  
A: Try [setting up MPV as your video player](#settings_video).  
Also be sure that you have [maximized the sound in SE](/gfx/no_audio1.png) and [maximized the sound in Windows](/gfx/no_audio2.png).  
  
Q: Is it possible to move a subtitle to the top of the screen?  
A: Yes, right-click on selected lines in the list view and choose **Alignment...**, and then choose e.g. **Top center**.  
You will only see position changes in SE if you use "**mpv**" as video player - see **Options -> Settings -> Video player** .  
Note: Not all video players/converters will use this positioning.  
  
Q: Where is the delay tool?  
A: Use **Show earlier/later** in the **Synchronization** menu. Shortcut is **Ctrl+Shift+A**. It's a tool window, so you can keep it open while working - or checking subtitle preview in video player.  
  
Q: Why can't Subtitle Edit change frame rate?  
A: Well, it can. Check **Synchronization -> Change frame rate**.  
  
Q: Why can't Subtitle Edit split/append subtitles?  
A: Try **Tools -> Split/append**.  
  
Q: Can Subtitle Edit offset times - but not from the very beginning?  
A: Yes, you can work with a selection of subtitle lines. Select the lines in the list view you want to work on (hint: click on the first line, then shift+click on the last) and then right-click in the list view (context menu) - now you can adjust the selected lines in "visual sync selected lines" or just "show selected lines earlier/later".  
  
Q: Can Subtitle Edit play video fullscreen?  
A: Yes, press ALT+ENTER. Use space for play/pause and ALT+ARROW UP/DOWN for next/previous subtitle.  
  
Q: When translating/editing subtitles, can Subtitle Edit navigate quickly to next line?  
A: Yes, press ALT+ARROW UP/DOWN for next previous subtitle - also textbox will keep focus.  
  
Q: Can Subtitle Edit add the subtitles to the video file?  
A: There are two ways of adding subtitles into the video file - hardcoding (cannot be turned off ever, so this _might_ be a bad idea) or embedding (only for some formats like mkv or mp4).  
SE can hardcode via the menu "Video" - "Generate video with burned-in subtitle" (requires FFmpeg).  
SE can softcode via the menu "Video" - "Generate video with added/removed embedded subtitles" (requires FFmpeg).  
  
Read more about [adding subtitles to video](/subtitleedit/AddSubtitlesToVideo) or perhaps a tutorial called [Using Handbrake to Burn in Subtitles from MKV to MP4 for Apple TV](https://www.epinionated.net/handbrake-burn-in-subtitles-mkv-mp4-apple-tv/).  
   
Q: How to make a good Github issue?  
A: Please add the following:

*   State where and what you were doing.
*   Attach a screen shot (use e.g. Alt+PrtScr or Win+Shift+S, please just use copy-paste and no image hosts) + text also (you can copy the text from an error message box with Ctrl+C)
*   Attach a subtitle (either whole or a sample, attach on Github as a .zip file)
*   Check if the file "error\_log.txt" contains useful information (and attach the file on Github if relevant)
*   Only one bug/request/question in one Github issue

  
  
  

* * *

  

Help index
----------

[Subtitle Edit main window](#Menu-in-main-window)  
[Subtitle Edit main window - resize/un-dock](#main_resize)  
[Subtitle Edit main window - edit original](#main_edit_original)  
[Video/wave form modes](#video_modes)  
[Wave form](#waveform)  
[Export](#Export)  
[Synchronization](#Synchronization)  
[Visual sync](#Visual-sync)  
[Auto-translation](#Auto-translation)  
[Fix common errors](#Fix-common-errors)  
[Remove text for hearing impaired](#remove-text-for-hearing-impaired)  
[Spell check](#Spell-check)  
[Import/OCR image based subtitles - like DVD Sub/idx or Blu-ray sup](#Import/OCR-image-based-subtitles---like-DVD-Sub/idx-or-Blu-ray-sup)  
[Edit Blu-ray sup/TS-images/BdnXml image based subtitles](#bdsupedit)  
[Settings](#Settings)  
[\- Shortcuts](#shortcuts)  
[\- Video player](#settings_video)  
[\- Tools](#settings_tools)  
[\- Appearance](#settings_font)  
[Bookmarks](#bookmarks)  
[Generate background box (for Advanced Sub Station Alpha)](#assa_bg_box)  
[Translating Subtitle Edit to another language](#translate)  
[Networking - online collaboration](#networking)  
[Beautify time codes](#beautify_time_codes)  
[Batch convert via UI](#batchconvert)  
[Audio to text (Whisper/Vosk)](#audio_to_text)  
[Text to speech](#text_to_speech)  
[Command line conversion](#commandline)  
[Portable version and VLC](#portable)  
[Make your own plugin](#plugins)  
[Subtitle Edit on Linux](#linux)  
[Compiling Subtitle Edit](#compile)  
[Known issues](#issues)  

  

* * *

  

Subtitle Edit main window
-------------------------

  

### Menu in main window

In the menu you can find many tools like change casing, split, append, spell check, synchronization, change frame rate, Google translate, find, replace, remove text for hearing impaired, and much more!  
You can import subtitles from Blu-ray sup, transport streams, DVD, vobsub, text and images - even subtitles inside Matroska files can be imported.  
  
![Menu](/gfx/main_menu.png)  
  
NOTE: Many tools are also available via right click in the list view.  
  
The toolbar can use external images. Create a folder called "Icons" (besides the "Dictionaries" and the "Waveforms" folder).  
Png files (32x32 pixels) with these names are used if exists: New, Open, Save, SaveAs, Find, Replace, FixCommonErrors, RemoveTextForHi, VisualSync, SpellCheck, Netflix, AssaStyle, AssaProperties, Settings, Help, WaveformToggle, VideoToggle  
  
  
  

### Subtitle/file formats

![Subtitle format](/gfx/FormatAndEncoding.png)  
  
In the top menu you can choose format and encoding. The first dropdown list shows subtitle formats. SubRip (extension is ".srt") is the most widely used format today, so it is recommended to save subtitles in this format.  
Originally SubRip was a text only format, but in recent years html tags have been common. Especially the italic and font tags are widely used. For a list of SubRip support in players [check this out](https://ale5000.altervista.org/subtitles.htm).  
  
File encoding is auto detected in most cases. ANSI is the old, formerly the most common found format, but it requires your system to have a specific culture setting. UTF-8 is recommended for new subtitles, as it can handle non English letters better than ANSI (UTF-8 subtitles will work on all computers no matter what culture settings a computer has), and can display other symbols like music nodes. The only drawback of using UTF-8 is, that some older programs do not support UTF-8.  
If you have an ANSI file in another language than the current culture/language (or you have an invalid UTF/Unicode file) then you can use the menu item: _File_ -> _Import subtitle with manual chosen encoding_.  
  
_Import subtitle with manual chosen encoding_ with preview:  
![ChooseEncoding](/gfx/ChooseEncoding.gif)

  
  

### Frame rate

![Frame rate](/gfx/help_framerate.png)  
  
Frame rate is not displayed by default, but you can enable it via the menu _Options_ -> _Settings: Toolbar: Show frame rate in toolbar_.  
Frame rate is used when converting between subtitle formats based on frames and formats based on time. SubRip is based on time. MicroDvd (widely used 7-9 years ago, and still widely used in some countries) is based on frames.  
Subtitles based on time is preferred as videos may not have a constant frame rate - which makes working with subtitles based on frames not very flexible at all.  
To change the frame rate use _Synchronization_ -> _Change frame rate_ - or use one of the other [synchronizations tools](#sync).

  
  

### Subtitle view - List view or source view

There are two ways of looking at a subtitle - list view or source view.  
You can switch between list view and source view with the F2 key or via the context menu.

**List view** is the default. This view is column based and has customizable columns:

![List view](/gfx/help_listview.png)

The list view gives an excellent overview of the subtitle - the same for all formats.  
You can edit text and time codes here, delete and insert lines easily.  

To select multiple lines in a block, select the first one, and then <Shift+click> on the last line (standard Windows functionality).  
<Ctrl+a> is "select all" and <Ctrl+Shift+i> is "inverse selection". <Ctrl+click> adds clicked line to selection.

  

  
It is also possible to select several lines and use tools like _Google translate_ or _Visual sync_ on the selected lines.  
  
![Listview](/gfx/help_listview2.png)

  
  

**Source view** (F2 toggles between source view and list view):

![Source view](/gfx/help_sourceview.png)

This is how the subtitle file actually looks - different for all formats.  
You can edit text and time codes here, but be careful - it's easy to mess things up.  
You can make Subtitle Edit start in Source view under Settings.

  

  
  

### Text box

Above the text box where you can type the actual subtitle is a label called "Chars/sec".  
If it's higher than your max CPS (CPS=Characters Per Second, e.g. 25), it will be colored red.  
  

![Text box](/gfx/TextBox.png)  
  
Below the text box is a label called "Single line length". First line is 32 characters and second line is 28 characters.  
If this label turns red, then one of the lines has exceeded your single line max length.  
This single line max length value can be adjusted in Options - Settings - General via "Single line max length" (43 is default).  
  
SE will default only allow one line break with the normal 'Enter' key - if you want more line breaks you must use 'Ctrl+Enter'.  
You can change the max number of lines to e.g. 3 in Options - Settings - General via "Max. number of lines".  
  

  
  

### Show video and/or waveform/spectrogram

  
The main window can show video and/or wave form. Video controls can even be un-docked - nice if you have two monitors!  
The horizontal/vertical red lines shows where you can resize inside the main window (via splitters).  
  
![Main window - with video/waveform](/gfx/main_video1.png)

  
  
 You can edit both new translation and original subtitle at the same time. You can make the original read-only Options -> Settings:General:Allow edit of original subtitle.  
When editing both original and translated subtitle, changing start time/duration/deleting/inserting will affect both subtitles!  
In Options - Settings - Shortcuts, you can find shortcuts for toggle original subtitle and switching translated / original subtitle.  
  
![Main window - with video/waveform](/gfx/main_edit_original.png)

  
  

### Play rate (speed)

The play rate can be adjusted from a slow 50% to a very fast 300% via the green double arrow in the waveform controls or via shortcuts.  
The play rate will not be remembered when re-starting Subtitle Edit.  
When the play rate is not 100% (which is normal speed), the green double arrow will have a darker background - like this: ![Play rate changed](/gfx/play_rate_changed.png)  
.

![Play rate](/gfx/play_rate.png)  
  

* * *

  
  
  

### Search

You can search by pressing Ctrl+F (F3 is find next). Regular expression search is available for nerds ;)

![Search](/gfx/help_search.png)  
  

* * *

  
  
  

### Find and replace

You can find and replace by pressing Ctrl+H. Regular expression search is available for nerds ;)

To change something to a new line via the replace string use "**\\n**".

  

* * *

  
  
  

### Multiple Replace

In _Edit -> Multiple replace_ you can create your own rules for fixing a subtitle - even advanced rules using [regular expressions](https://en.wikipedia.org/wiki/Regular_expression)!

When writing regular expressions grouping and backreferences are very useful. Parts of a regular expression inside parentheses are groups and can be referenced in the replace string where $1 is a reference to the first group and $2 is a reference to the second and so on.  

Example 1:

**^J( .+)** + replace string **♪ $1**

Only the starting "J" will be replaced, so if the text is "J Music Playing J" it will become "♪ Music Playing J"

Example 2:

**(\[a-z\]+)(\[0-9\]+)** + replace string **$2$1**

Two groupings that will be switched, so if the text is "number26" it will become "26number".

Example 3:

**\[.\\s\\S\]\*www.addsite.com\[.\\s\\S\]\*** + empty replace string

Will remove any subtitles containing "www.addsite.org"

Example 4:

**\\p{L}** + empty replace string

Will remove all Unicode letters (e.g. also Danish letter like æ, ø, and å).  
**\\p{Lu}** will match an uppercase letter that has a lowercase variant  
**\\p{Ll}** will match a lowercase letter that has an uppercase variant  

Example 5:

**<\[^>\]\*>** + empty replace string

Will remove all html tags.

Example 6:

**\\A** + replace string **{\\an8}**

**\\A** will match only first line in each subtitle (unlike **^** that will match all lines).  
E.g. "Hallo world" will become "{\\an8}Hallo world" and "Hallo\\r\\nworld" will become "{\\an8}Hallo\\r\\nworld".

Example 7:

**(.+)\\n(.+)** + replace string **$1**

E.g. "Hallo world **new-line** Bye world" will become "Hallo world".

You can test/build regular expressions on many web pages, like [http://regexstorm.net](http://regexstorm.net/tester).  
If the result of a replace rule is an empty string, the subtitle will be removed.  
  

![Multiple replace](/gfx/main_edit_multiple_replace.png)  
  

* * *

  

Video/wave form modes
---------------------

  
When using video and/or wave form three different modes (tabs) are available: Translate, Create, and Adjust.

### Translate mode

![Translate mode](/gfx/mode_translate.png)  
  
In translate mode you can translate a subtitle from one language to another manually (or correct a machine translated subtitle) while watching the video - and hearing the audio.  
If "Auto repeat" is on, then the subtitle will be repeated x-times while you are typing in the correct text.  
Use _File_ -> _Open original subtitle (translator mode)_ to also display the original text.  
Hint: Do use the <alt+arrow up/down> for going to previous/next subtitle.  
  
  

### Create mode

![Create/adjust lines](/gfx/mode_create.png)  
  
This is the place to create subtitle lines from scratch or manually adjust existing lines.  
  
To create subtitle lines from scratch, pause the video file where the subtitle line should start and press the button "Insert new subtitle at video pos". Then enter the text - duration is auto suggested. Now press the button "Play from just before text" and if the text does not start exactly when the speech starts, then adjust "Start time" via the up/down arrows until it does. The duration can be set via the button "Set end time" while the video is playing or via the "Duration up/down arrows.  
To insert a subtitle right after the current line, press the Insert button (while the list view is focused).  
  
You can also right click on the audio wave form or in the list view to insert/merge/split/delete lines.  
  
  

### Adjust mode

![Adjust mode](/gfx/mode_adjust.png)  
  
This is the place to adjust existing lines.  
  
To adjust subtitle lines manually one by one starting from the top. Use the buttons "Set start and offset the rest" (F9) and "Set end & go to next" (F10). Fine-tuning of "Start time" and "Duration" should be done by using the up/down arrows.  
  
You can also right click on the audio wave form or in the list view to insert/merge/split/delete lines.  
  

* * *

  

Wave form
---------

The wave form control makes it easy to see exactly where speech starts/ends.  
![Wave form](/gfx/Waveform1.png)  
  
  
With the right click menu, you can split/merge/delete subtitles.  
![Wave form - right click menu](/gfx/Waveform2.png)  
  
  
To create a new paragraph, make a new selection with the mouse and press **Enter**  
(or right click + choose "Add text here").  
![Wave form - new selection](/gfx/Waveform3.png)  
  

### Wave form mouse/keys usage:

*   Mouse single click: Go to position
*   Mouse double click on existing subtitle: Select clicked subtitle
*   Mark area + right click on marked area: Prompt for add new paragraph / play current selection
*   Mouse drag left/right border of subtitles (adjusting start or end time)
*   Move/drag on middle of subtitle (adjusting both start and end time - but not duration)
*   Mouse right click can either add new subtitle or perform delete/split/merge on existing subtitle line
*   Mouse wheel scrolls waveform forward/back
*   alt+arrow left/right moves video position
*   alt+arrow up/down goes previous/next subtitle
*   Numeric +/- will zoom in/out
*   Mouse single click+Shift will set start for selected line (not moving end time)
*   Mouse single click+Ctrl will set end for selected line (not moving start time)
*   Mouse single click+Alt will set start for selected line (and keep duration)
*   Mouse double click on non-paragraph - toggle play
*   **Mouse single click+Ctrl+Shift will set of start selected line + offset all lines after selected line (keeping durations)**
*   Holding down ALT when moving start/end will move nearest subtitle start/end too if it's closer than 500 milliseconds - [like this.](/gfx/WaveformMoveNextPrev.gif)

  

### Waveform extraction

The extracting of wave data can be done with FFmpeg (configure in Options - Settings - Waveform) or [VLC](https://www.videolan.org/), and then a very small wave file (with a VERY low samplerate) is generated and saved in the "WaveForms" folder.  
  
Note: You cannot use waveform without the video or the audio.  

* * *

  
  

## Export


Subtitle Edit can save via "Save as..." in many different text formats, but if you want to save a subtitle in a binary format (like pac or 890) or an image based format (like png or Blu-ray sup) you must use File -> Export.  
  
Many settings like font, colors and also box style can be chosen.  
These tags are preserved when exporting a subtitle to an image based format:

*   **i** - for setting font to italic
*   **font color** - for setting the font color
*   **&123;\\an1&125;**\-**&123;\\an9&125;** - alignment tags
*   ASSA (Advanced Sub Station alpha) or SSA styles like color, font size and box (only ASSA has color alpha/translucency)

![Export screenshot](/gfx/help_export.png)  
Note: Arabic might require "Simple rendering".  
Note: SE requires TTS fonts, and does not support OTF font files.  

* * *

  

# Synchronization
---------------

![Sync menu](/gfx/SyncMenu.png)

  
Subtitle Edit offers several ways to synchronize subtitles.  

Adjust all times (show earlier/later): This is useful if you for example need to show all texts 3 seconds earlier.

[Visual sync](#visual_sync): Sync by matching start/end scene (more below).

Point sync: This allows synchronization by using 2 or more points - sync point time codes can be entered manually which makes it easy to use time codes from another subtitle already in sync.

Point sync via other subtitle: If you have another subtitle in sync (perhaps in another language - it helps if you can understand it a bit) you can match one of the first lines, match one of the last lines, sync, and then all lines should be in sync.

Change frame rate: This makes it easy to match text from a video with one frame rate to a video with another frame rate (can also be done by visual sync or point sync).

  
  
  

## Visual sync
-----------

![Visual Sync controls](/gfx/vissync.png)

  
Visual sync is a really easy way to synchronize a subtitle with a video file.  
Match one of the first subtitle lines with the start scene. Then match one of the last subtitle lines with the end scene. Press "Sync!" - and that's it :)  
There are a few helper buttons which will help find the right place in the video where the subtitle should start (just about where the first word comes out). The "Play 1 sec and back" button is a test button, so you can easily verify that the current position really is correct. Also check the [Shortcuts](#shortcuts).  
  
In some cases a subtitle is impossible to synchronize because one or more scenes have been removed/added. In these cases you can select a number of subtitles in the subtitle [list view](#listview), right click and choose _Visual sync selected lines_. This way you can adjust the subtitle in smaller parts.

  
  

* * *

  

## Translation (auto)


Subtitle Edit can translate a subtitle by using [Google translate](https://translate.google.com), [Bing Microsoft translator](https://www.bing.com/translator), or [Facebook's NLLB (No Language Left Behind)](https://huggingface.co/docs/transformers/model_doc/nllb).  
Automatic translation works fairly well, but translated subtitles will still need manual correction (hint: use main window [translate mode](#video_modes)).  
  
For Google translate you need to set up a [Google Cloud API key](https://www.google.com/search?q=google+cloud+get+api+key) (or use the limited free quota) and for Microsoft translate you need to setup an [cognitive services 'Translator Text' key](https://docs.microsoft.com/en-us/azure/cognitive-services/translator/translator-text-how-to-signup) and be sure to use the correct [token endpoint](https://github.com/MicrosoftDocs/azure-docs/blob/master/includes/cognitive-services-speech-service-endpoints-token-service.md).  
Note that if you do get an API key for Google Cloud (read more [here](https://github.com/SubtitleEdit/subtitleedit/discussions/6773#discussioncomment-5417761)) you need to add billing info - even for the free trial period.  
After getting the key, you need to paste it into the "API Key" field for "Google translate" via the menu Options - Settings - Tools.  
  
  
Running Facebook's NLLB (with support for 200 languages) works via [nllb-serve](https://github.com/thammegowda/nllb-serve) or [nllb-api](https://github.com/winstxnhdw/nllb-api) running as a local web API:  
[nllb-serve](https://github.com/thammegowda/nllb-serve) requires [git](https://www.google.com/search?q=git+download) and [Python/pip](https://www.google.com/search?q=python+download).  
Install with these commands:  

git clone https://github.com/thammegowda/nllb-serve  
cd nllb-serve  
pip install -e .  

Run with this command line:  

nllb-serve

  
[nllb-api](https://github.com/winstxnhdw/nllb-api) requires [Docker](https://www.google.com/search?q=Docker+download). Start the docker container with this command line:  

docker run --rm -e SERVER\_PORT=5000 -e APP\_PORT=7860 -p 7860:7860 -v C:\\Windows\\Temp\\cache.bin:/home/user/.cache ghcr.io/winstxnhdw/nllb-api:main

  
  
Running [LibreTranslate](https://libretranslate.com/) works via a local web API (requires [Python/pip](https://www.google.com/search?q=python+download)):  
Install with this commands:  

pip install libretranslate

Run with this command line:  

libretranslate

  
  
Running [Ollama](https://github.com/ollama/ollama) works via a large language models locally.  
Install their program and pull the model you want to use via cmd line:  

ollama pull llama3

  
  
Also do check the translate plug-ins, see **File -> Plugins**.  
  
![Create/add lines](/gfx/help_googletranslate.png)  
  

* * *

  

## Fix common errors


  
![Fix common errors](/gfx/help_fixcommonerrors1.png)  
  
Some subtitles have a lot of errors (often these subtitles are created using OCR software).  
"Tools -> Fix common errors" provides an easy way to fix a lot of these errors.  
The first window shows a list of actions to fix, just tick the check boxes you want fixed and click "Next".  
  
  
![Fix common errors](/gfx/help_fixcommonerrors2.png)  
  
Now you can choose which fixes to apply. Selected fixes are will be remembered in future sessions.  
The log tab gives an overview of what will be done - and what was not possible to fix.  
The "Apply selected fixes" button applies the fixes.  
  

* * *

  
## Remove text for hearing impaired

Many subtitles include text for hearing impaired (also known as "[SDH](https://en.wikipedia.org/wiki/Subtitle_%28captioning%29#SDH)" in the American movie industry which is an initialism for "Subtitles for the deaf or hard-of-hearing").  
For people with perfect hearing (and no noisy kids) these texts can be annoying - and easily removed with **Tools -> Remove text for hearing impaired**.  
  
SE offers many options for configuring removal of text for HI and in the preview you can see what changes will be made - and skip any wrongly made removals.  
You can also remove [interjections](https://en.wikipedia.org/wiki/Interjection) and you can maintain your own interjections. Interjections are not case sensitive and SE will try to remove them by descending text length.  
  
![Remove text for hearing impaired](/gfx/remove_text_for_hi.png)  
  

* * *

  
## Spell check
  
Spell check uses [Hunspell](http://hunspell.sourceforge.net/) (which is also used by Open/LibraOffice, Firefox, Chrome, and Opera).  
Only English dictionary is included, but you can easily find more dictionaries via the toolbar menu _Spell check_ -> _Get dictionaries..._!  
If you download [Open Office 3.x dictionaries](http://extensions.services.openoffice.org/en/dictionaries) with the extension .oxt, then rename to .zip, and then unpack the .dic file and the .aff file to the Subtitle Edit _Dictionary_ folder.  
  
The spell check will show this window when it encounters an unknown word:  
![spell check](/gfx/spell_check.png)  
**_Edit whole text_** will enable editing of the whole text (and not only the current word) - for this one sub only.  
**_Change all / Use always_** will change current word in always - also in future works (saved in the OCR Fix Replace list - take a look at Dictionaries/eng\_OCRFixReplaceList.xml to learn more about this file).  
**_Change / Use_** will change current word just this once.  
**_Add to names/noise list (case sensitive)_** will remember the name in the edit text box with current casing - also in future works.  
**_Add to user dictionary_** will remember the word in the edit text box and not prompt for it any more - also in future works. User dictionary is not case sensitive.  
  
All buttons in the "Word not found" groupbox will use the word in the "Word not found" textbox.  
  

* * *

  

## Import/OCR image based subtitles - like DVD Sub/idx or Blu-ray sup

  
  
If you open an image based subtitle like Blu-ray sup or sub/idx (vobsub) this screen will come up:  
  
![Import/ocr image based subtitles](/gfx/help_importvobsub.png)  
  
  
The list view now contains empty subtitle text lines with only timestamps. You can enter the text manually, but it's much easier to let one of the OCR engines do the work:

*   OCR via binary image compare (recommended): This option does not require any third party software installed, but it does require the user to manually enter letters based on image parts.  
    "No of pixels is space" should be decreased if not all translated words are separated (like "_wearefine._"), and increased if there are too many separations (like "_w e ar e fi n e._").  
      
    
*   OCR via **Tesseract 3.02** (recommended): [Tesseract](https://github.com/tesseract-ocr/tesseract) is an open source OCR engine.  
    You can find additional language data files at [Github](https://github.com/tesseract-ocr/tesseract/wiki/Data-Files#data-files-for-version-302). These Tesseract dictionary files need to be unpacked to \[Subtitle Edit folder\]\\Tesseract302\\tessdata.  
      
    If you right-click in the list view, you will get a context menu with these options:  
    ![OCR list view context menu](/gfx/ocr_context_menu.png)  
    **_Import text with matching time codes..._** can be used to continue working on an earlier created subtitle.  
    **_Save subtitle image as..._** allows for saving current image as either png, gif, bmp, or tiff.  
    **_Save all images with html index_** display all subtitles images in an html page - for easy proof reading.  
      
    OCR via Tesseract will work best if you also have [spell check](#spellcheck) dictionaries.  
    ![OCR dictionary](/gfx/ocr_dictionary.png)  
    **_prompt for unknown words_** and **_Try to guess unknown words_** will only work if a dictionary is available. **_Fix OCR errors_** will also benefit from a dictionary.  
    If you think Tesseract is too slow, you could set the spell check dictionary to "None" for better performance and then fix errors e.g. via "Fix common errors" plus spell check afterwards.  
      
    The **_prompt for unknown words_** will look like this (window is re-sizable):  
    ![OCR spell check](/gfx/ocr_spell_check.png)  
    **_Edit whole text_** will enable editing of the whole text (and not only the current word) - for this one sub only.  
    **_Change all / Use always_** will change current word always - also in future works (saved in the OCR Fix Replace list - take a look at Dictionaries/eng\_OCRFixReplaceList.xml to learn more about this file).  
    **_Change / Use_** will change current word just this once.  
    **_Add to names/noise list (case sensitive)_** will remember this name with current casing - also in future works.  
    **_Add to user dictionary_** will remember this word and not prompt for it any more - also in future works.  
      
      
    
*   OCR via **Tesseract 5** (recommended for text without italics or languages not available for Tesseract 3.02): [Tesseract](https://github.com/tesseract-ocr/tesseract) is an open source OCR engine.  
    You can find additional language data files at [Github](https://github.com/tesseract-ocr/tesseract/wiki/Data-Files#updated-data-files-for-version-400-september-15-2017). These Tesseract dictionary files need to be unpacked to \[Subtitle Edit folder\]\\Tesseract4\\tessdata.  
      
    Tesseract 5 uses a new OCR engine that uses neural network system based on LSTMs.  
    Note that Tesseract 5 is a bit slower and has **limited support for detecting italic font style** - but it does bring accuracy gains, especially for smaller/unclear fonts.  
    Note that Tesseract works best with black letters on a white background, or white letters on black background (try to avoid an outline).  
    You'll need to install [Visual C++ 2017 runtime](https://aka.ms/vs/15/release/vc_redist.x86.exe) to run Tesseract 5 (otherwise SE will complain about a missing VCOMP140.dll file).  
      
      
    
*   OCR via **[nOCR](/subtitleedit/nocr)** (recommended for larger subtitles like blu-ray .sup)  
    You can train nOCR with our own fonts fairly easy/quick.  
      
      
    

Select one of the OCR methods and click on the button "Start OCR".  
When you are done just click "OK" and do remember that an OCR'ed subtitle most likely contains some errors that need correction.  
If a VobSub/TS subtitle contains more than one language, you will be prompted for language.  
  

* * *

  
  

Edit Blu-ray sup/TS-images/BdnXml image based subtitles
-------------------------------------------------------

  

In **File - Import - Blu-ray (.sup) subtitle file for edit** it's possible to edit and re-save while keeping existing positions.  
You can change color/size/alpha/position/forced/sync/duration of lines/insert and even replace a whole image and much more:  
  
![Edit Blu-ray sup screenshot](~/gfx/se-sup-edit.png)  
  
In the preview to the right, you can see subtitles in a black box (the black box only shows the size of the image).  
The subtitle preview box can be moved with the mouse or via the position number up/down controls.  
  
In **File - Save as...** you can save as **Blu-ray sup** or **BdnXml**.  
  

* * *

  
  

## Settings
  

In Settings you can adjust how Subtitle Edit will behave, so it's pretty important to take a look at these settings - especially single line maximum length and maximum characters per second as these settings will be used throughout all functionality, like "Fix common error" and other tools like syntax coloring in the main window list view (see the "Syntax coloring" settings for adjustments).  
  
![Settings](/gfx/help_settings.png)  
  
The most important rules are grouped in a "Profile" - you can use the default, choose one of the pre-defined profiles, or define your own. ![Settings - profiles](/gfx/help_settings_profile.png)  
  
  

* * *

  
  
   

Settings - Shortcuts
--------------------

  
A few of the most important ones are:

Window

Control

Shortcuts

Function

Main

\*

Ctrl+F (customizable)

Open the Find dialog

Main (customizable)

\*

F3

Find next

Main

\*

Ctrl+Z (customizable)

Show history/undo

Main

\*

Ctrl+G (customizable)

Go to subtitle number dialog

Main

\*

Alt+Arrow up

Go one line up in subtitle list view

Main

\*

Alt+Arrow down

Go one line down in subtitle list view

Main

Subtitle list view

Ctrl+A

Select all lines

  
  
[Complete list of shortcuts!](/subtitleedit/shortcuts)  
  
Shortcuts are configurable via _Options -> Settings -> Shortcuts_ (let me know if you need more):  
  
![Configurable shortcuts](/gfx/shortcuts.png)  
Note: Shortcuts in menus has a stricter validation than hidden shortcuts (e.g. \[Shift+N\] is not allowed in a menu but is fine for a hidden shortcut).  
  

* * *

  
   

Settings - Video player
-----------------------

In the "Video player" section you can choose which video player to use inside SE.  
![Settings - video player](/gfx/help_settings_video.png)  
Currently "mpv" is recommended as it has precise seeking and on-video-preview.  
Click on "Download mpv lib" to download and use "mpv".  
  
If you have problems downloading mpv via the download button, you can download the file directly from [Github](https://github.com/SubtitleEdit/support-files/tree/master/mpv).  
Download the [libmpv2-64.zip](https://github.com/SubtitleEdit/support-files/raw/master/mpv/libmpv2-64.zip) file if you have a 64-bit OS.  
Unpack the zip file and copy "mpv-2.dll" to the SE data folder (press Ctrl+Shift+Alt+D in the SE main window to open the SE data folder).  
You can get cutting edge versions of mpv here: [https://sourceforge.net/projects/mpv-player-windows/files/libmpv/](https://sourceforge.net/projects/mpv-player-windows/files/libmpv/)  
  

* * *

  
   

Settings - Tools
----------------

Here you can setup/tweak different tools:  
  
![Settings - Font](/gfx/help_settings_tools.png)  
  
If you often use "Fix common errors" and always use the same fix rules, then enable "Skip step one" to save time.  
  
Often people want to customize line split, so many options are available for this incl. do-not-break-after list.  
The "auto br" line split settings are used in "Fix common errors", the main window "Auto br" button, and the list view context menu "Auto balance selected lines".  
Note that the "Auto br" button works on selected lines.  
  

* * *

  
   

Settings - Appearance
---------------------

Here you can set font and other UI properties for the SE interface.  
![Settings - Font](/gfx/help_settings_font.png)  
  
**Use syntax coloring** will enable syntax coloring of html tags and optional spelling errors: ![Settings - Appearance - Text box syntax coloring](/gfx/help_settings_font_textbox.png)  
  
**Dark theme / Dark mode** will switch color theme to something like this: ![Settings - Appearance - Dark theme](/gfx/help_settings_font_darktheme.png)  
  
  

* * *

  
   

Bookmarks
---------

  
You can add a bookmark for a line by activating one of the "Toggle bookmark" shortcuts (see Options - Settings - Shortcuts).  
In the "Add bookmark with comment" window you can enter a comment to the bookmark (use Shift+Enter for more than one line).  
Bookmarks are saved in a separate file. If you're working on "video.srt", then SE will save the bookmarks in a file called "Video.srt.SE.bookmarks", so you can actually email both files to other people using SE, and they can also see the bookmarks.  
  
![Bookmark](/gfx/bookmark.png)  
  
Tip 1: You can right click on the bookmark image left of the text box to get a context menu.  
Tip 2: You can double click on the yellow text label to edit the text.  
  
  

* * *

  
   

Generate background box (for Advanced Sub Station Alpha)
--------------------------------------------------------

  
Generate a box with e.g. rounded corners behind the text.  
  
It's also possible to add a drawing (logo/flag/etc.) to each background box or even instead of the box.  
Drawings can use a little scripting inside brackets (\[\]) with these constants which are calculated from current subtitle text: **left, top, right, bottom, width, height**  
Example of coordinate: \[left+width\*0.9\],\[top+10\]  
The preview will update if the drawing source file is changed, e.g. if you edit it in notepad.  
  
**Important note**: Background box should be made when finishing a subtitle. Box sizes will reflect the text at the time of generation!  
  
![Generate background box](/gfx/assa_bg_box.png)  
  
  

* * *

  

Translating Subtitle Edit to another language
---------------------------------------------

  
To translate Subtitle Edit first download [the English xml language file](https://raw.githubusercontent.com/SubtitleEdit/subtitleedit/main/LanguageBaseEnglish.xml) and save it to your "Subtitle Edit\\Languages" folder. Translate the content of all tags with an xml editor or just notepad. You can also use [Xml Content Translator](/XmlContentTranslator)!  
Save your edited xml file as 'CultureName'.xml ('CultureName' must be an [existing culture name](http://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo%28v=vs.80%29.aspx) - and also a tag in the xml file) in the SubtitleEdit\\Languages folder. In Options > Choose language, you can now test your translation by choosing your language as language.  
Please do send any translations to me, so I can include them in Subtitle Edit - thx :)  
Tip 1: [WinMerge](http://winmerge.org) is an excellent tool for comparing files.  
Tip 2: In the About section you can put your email (with "mailto:" before to make a clickable link) or homepage.  
Tip 3: The help file tag can point to an url where the help is - keep it blank to just point to the English help file.  
  
The installer can localized by translating [this file](https://github.com/SubtitleEdit/subtitleedit/blob/main/installer/Subtitle_Edit_Localization.iss).  
  

* * *

  

Networking - online collaboration
---------------------------------

  
If you and a few friends want to translate the same subtitle at the same time over the internet, then do try the "Networking" feature.  
First load the subtitle you want translated (and optionally the original subtitle). Then choose "Start new session" in the "Networking" menu:  
  
![Start network session](/gfx/NetworkingStart.png)  
  
The "session key" is your subtitle id (can be any text you like) - other people need this in order to join (via menu Networking -> Join session) your session.  
The "username" will be displayed when updating/inserting/deleting lines and in the chat window  
The "webservice url" points to a small server program hosting the session (I initially developed this via direct p2p, but decided to use a webservice instead, as it works much better with stuff like firewalls). [Source code for this webservice is available](/gfx/SeNetworkingServiceCore.zip) (also for [dotnet 6](/gfx/SeNet6.zip) and [dotnet 7](/gfx/SeNet6.zip)) and should make it easy to use your own server for hosting the networking session.  
  
  
Subtitle Edit running in networking mode below. In the "User/action" column in the list view you can follow the translation progress - this might sparkle some synergistic effect!  
  
![Subtitle Edit running in networking mode](/gfx/networking.jpg)  
  

* * *

  

Beautify time codes
-------------------

  
Beautify time codes can round time codes to frame time codes, and/or put cues on shot changes if they are near enough.  
  
With ffprobe (in-program download) you can round time code milliseconds to frame time codes.  
Snap to shot changes with advanced rules. Shot changes can be generated by ffmpeg (ffmpeg is an in-program download).  
![Beautify time codes UI](https://user-images.githubusercontent.com/3516155/242400082-c3fc17fd-70a3-4243-872d-5d4ff98c0b5a.png)  
  
The rules are very configurable, and can e.g. be configured to support Netflix rules:  
![Beautify time codes UI](https://user-images.githubusercontent.com/3516155/242400192-de57c7b4-5e60-477c-b97c-c88dee39c902.png)  
  

* * *

Batch convert via UI
--------------------

  
**Batch convert** is accessible via **Tools** -> **Batch convert...** or you can start the batch convert directly via _SubtitleEdit /batchconvertui_  
  
Batch convert is a powerful tool that can convert between 300 different subtitle formats with a lot of options.  
Many formats can also be read from mkv/mp4/ts/m2ts files.  
  
Some of the batch convert options have their own settings, e.g. "Merge short lines". To show the settings for "Merge short lines", the list box line with the "Merge short lines" option should be selected like below (note: it's not enough to click on the check box, a click on the text is needed).  
  
Transport streams (.ts/.m2ts) can only be converted to Blu-ray sup files - check the **TS settings** if you want to resize or do re-positioning.  
  
![Batch convert UI](/gfx/batch_convert.png)  
  

* * *

Audio to text
-------------

  
**Audio to text** (also called "speech to text" or "speech recognition") is accessible via **Video** -> **Audio to text...** or you can make a custom shortcut.  
  
  
**Audio to text (Whisper)** is a new experimental speech recognition framework that works on around 100 languages.  
  
![Audio to text](/gfx/audio_to_text_whisper.png)  
  
You can use one of these Whisper versions:

*   The original [OpenAI Whisper](https://github.com/openai/whisper) (requires Python)
*   Purfview's [Faster-Whisper](https://github.com/Purfview/whisper-standalone-win) (Windows only)
*   A simplified/optimized version called [whisper.cpp](https://github.com/ggerganov/whisper.cpp) (written in C++)
*   A GPU optimized version of CPP with [cuBLAS support](https://github.com/ggerganov/whisper.cpp) (written in C++)
*   A GPU optimized version called [Whisper Const-me](https://github.com/Const-me/Whisper) (written in C++)
*   A optimized version called [Whisper CTranslate2 (also known as FasterWhisper)](https://github.com/jordimas/whisper-ctranslate2) (requires Python)
*   Another Python version called [stable-ts](https://github.com/jianfch/stable-ts) (requires Python)
*   Another Python version called [whisperX](https://github.com/m-bain/whisperX) (requires Python)

  
To install and run the OpenAI Python version, you will need to follow [the installation instructions](https://github.com/openai/whisper#setup).  
Before installing Whisper Python versions, do [install Python](https://www.python.org/ftp/python/3.10.11/python-3.10.11-amd64.exe) and **remember to check "Add Python to PATH"** and you also might need [Git](https://gitforwindows.org/) too.  
Manual model download links for OpenAI Python version: [tiny.en](https://openaipublic.azureedge.net/main/whisper/models/d3dd57d32accea0b295c96e26691aa14d8822fac7d9d27d5dc00b4ca2826dd03/tiny.en.pt)  [tiny](https://openaipublic.azureedge.net/main/whisper/models/65147644a518d12f04e32d6f3b26facc3f8dd46e5390956a9424a650c0ce22b9/tiny.pt)  [base.en](https://openaipublic.azureedge.net/main/whisper/models/25a8566e1d0c1e2231d1c762132cd20e0f96a85d16145c3a00adf5d1ac670ead/base.en.pt)  [base](https://openaipublic.azureedge.net/main/whisper/models/ed3a0b6b1c0edf879ad9b11b1af5a0e6ab5db9205f891f668f8b0e6c6326e34e/base.pt)  [small.en](https://openaipublic.azureedge.net/main/whisper/models/f953ad0fd29cacd07d5a9eda5624af0f6bcf2258be67c92b79389873d91e0872/small.en.pt)  [small](https://openaipublic.azureedge.net/main/whisper/models/9ecf779972d90ba49c06d968637d720dd632c55bbf19d441fb42bf17a411e794/small.pt)  [medium.en](https://openaipublic.azureedge.net/main/whisper/models/d7440d1dc186f76616474e0ff0b3b6b879abc9d1a4926b7adfa41db2d497ab4f/medium.en.pt)  [medium](https://openaipublic.azureedge.net/main/whisper/models/345ae4da62f9b3d59415adc60127b97c714f32e89e936602e85993674d08dcb1/medium.pt)  [largev2](https://openaipublic.azureedge.net/main/whisper/models/81f7c96c852ee8fc832187b0132e569d6c3065a3252ed18e56effd0b6a73e524/large-v2.pt) [large (v3)](https://openaipublic.azureedge.net/main/whisper/models/e5b1a55b89c1367dacf97e3e19bfd829a01529dbfdeefa8caeb59b3f1b81dadb/large-v3.pt)  
  
Manual model download links for Purfview's Faster-Whisper/CTranslate2 versions: [Faster-Whisper models](https://huggingface.co/guillaumekln)   
  
Manual model download links for CPP versions: [tiny.en](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-tiny.en.bin)  [tiny](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-tiny.bin)  [base.en](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-base.en.bin)  [base](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-base.bin)  [small.en](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-small.en.bin)  [small](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-small.bin)  [medium.en](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-medium.en.bin)  [medium](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-medium.bin)  [largev2](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-large-v2.bin) [large (v3)](https://huggingface.co/ggerganov/whisper.cpp/resolve/main/ggml-large-v3.bin)  
  
Requirements for "CPP cuBLAS": https://developer.nvidia.com/cuda-downloads  
  
Requirements: Requirements vary depending of Whisper engine and model. The large model can require up to 16 GB of ram.  
Whisper CPP/Const-me require a newer CPU with AVX instruction set.  
If you do not want to install Python, Purfview has Whisper OpenAI and Whisper CTranslate2 [compiled binaries](https://github.com/Purfview/whisper-standalone-win/releases).  
  
Note: A whisper log is written to the file "whisper\_log.txt" in the "SE data folder" (press Ctrl+Alt+Shift+D in the SE main window to open the SE data folder).  
Note: You can press F2 in the Whisper windows too see the actual command line output during transcribe.  
Note: All Python Whisper can be very difficult to install, so follow the authors installation instructions very carefully. It's probably best to use Python 3.10 and often different Whisper versions cannot requires different versions of the same packages so do use something like [Anaconda](https://www.anaconda.com/download).  
  
  
  
**Audio to text (Vosk/Kaldi)** can convert speech to text for more that 20 languages.  
The resulting quality depends on how clear the speech is and how good the model is.  
  
  
Batch conversion is available and you can also use **Audio to text** on selected lines in the list view via context menu (right click).  
  
  
![Audio to text](/gfx/audio_to_text.png)  
  
**Audio to text (Vosk/Kaldi)** requires [libvosk](https://github.com/alphacep/vosk-api) and [audio to text models](https://alphacephei.com/vosk/models) as well as [FFmpeg](https://ffmpeg.org).  
  
libvosk, FFmpeg and models download should be handled by the SE UI, and the folder structure will be like this:  

*   FFmpeg: \[SE Data folder\]\\ffmpeg (should contain ffmpeg.exe)
*   libvosk: \[SE Data folder\]\\Vosk (should contain libvosk.dll etc.)
*   models: \[SE Data folder\]\\Vosk\\\[model name\] (should contain final.mdl in the "am" folder)

![Audio to text](/gfx/audio_to_text_folders.png)  
  
On Linux you need to [install vosk](https://github.com/SubtitleEdit/subtitleedit/issues/6071) with "pip3 install vosk" and setup a symlink file like "sudo ln -s /usr/local/lib/python3.8/dist-packages/vosk/libvosk.so ~/Downloads/SubtitleEdit/libvosk.so".  
  
  

* * *

Text to speech
--------------

  
**Text to speech** (TTS) is accessible via **Video** -> **Text to speech and add to video...** or you can make a custom shortcut.  
Note that split sentences should be merged before using TTS. Formatting should also be removed.  
CPS (characters per second) should not be too high or the audio will sound bad (too fast).  
Will convert all texts from a subtitle and convert to audio and optionally add this new audio track to your video file.  
For ASSA format, you can assign a voice to each actor.  
  
**[Piper TTS](https://github.com/rhasspy/piper)**: Requires an in-program download for Windows + requires model downloads. Good quality and speed. Includes many voices.  
  
**[Tortoise TTS](https://github.com/neonbjb/tortoise-tts)**: Requires an installation via Python. Good but very slow, especially without CUDA.  
  
**[Coqui AI TTS](https://github.com/coqui-ai/TTS)**: SE will run against the api (tts-server), see [the docker images](https://docs.coqui.ai/en/latest/docker_images.html) page.  
Only one voice at a time.  
  
**[ElevenLabs](https://elevenlabs.io/api)**: Online. Requires an API key. Good quality and many voice.  
  
**Microsoft Speech Synthesizer TTS**: Old, fast, and very robotic. Included with Windows (probably).  
  

* * *

Subtitle Edit command line conversion
-------------------------------------

  
Subtitle Edit can do command line conversion between formats listed in the main window format drop down list.  
  
Syntax: SubtitleEdit /convert "pattern" "name-of-format-without-spaces" \[/encoding:?\] \[/fps:?\] \[/outputfolder:?\]:  
  
Example 1:

SubtitleEdit /convert sub1.srt sami

Result: Will convert sub1.srt to sub1.sub to SAMI format  
  
Example 2:

SubtitleEdit /convert \*.srt adobeencore

Result: Will convert all .srt files to Adobe Encore format  
  
Example 3:

SubtitleEdit /convert \*.srt adobeencore /encoding:windows-1252

Result: Same as above but using windows-1252 file encoding (see [Info.Name list](http://msdn.microsoft.com/en-us/library/system.text.encodinginfo.getencoding.aspx) for more encodings)  
  
Example 4:

SubtitleEdit /convert a.sub subrip /fps:25

Result: Converts frame based a.sub to time based a.srt via a frame rate of 25  
  
Example 5:

SubtitleEdit /convert a.sub subrip /outputfolder:C:\\Temp

Result: Converts a.sub to C:\\Temp\\a.srt  
  
Example 6:

SubtitleEdit /convert a.sub CustomText:MyFormat

Result: Converts a.sub to a.txt in a custom format named "MyFormat"  
  
To list supported formats:

SubtitleEdit /convert /list

Result: Show the more than 300 supported formats in command line conversion!  
  
  

* * *

Portable version and VLC
------------------------

  
To use Subtitle Edit portable with VLC portable, download VLC portable (at least version 1.1.0, like [VLC 3.0.8 64-bit](https://get.videolan.org/vlc/3.0.8/win64/vlc-3.0.8-win64.exe) or [VLC 3.0.8 32-bit](https://get.videolan.org/vlc/3.0.8/win32/vlc-3.0.8-win32.exe)).  
Now you can unpack to a sub folder in the Subtitle Edit folder called "VLC" or go to **Options -> Settings -> Video player** and browse to VLC portable version.  
Note: You need VLC 64-bit on 64-bit operating systems, and VLC 32-bit on 32-bit operating systems.  
  

* * *

Make your own plugin
--------------------

  
If you can code C# or VB.net you can make your own plugins for SE (SE 3.3 and later).  
  
You can [visit the GitHub plugin page](https://github.com/SubtitleEdit/plugins) for more information and download.  
"Haxor" is a very very basic example.  
"Fix Hyphens" is a more complete example with a form and some basic helper classes.  
At the moment it is possible to use plugins here: File, Tools, Sync, Translate, and "Spell check".  
Compile to "Any CPU" and not x86 or x64.  
  
  

* * *

Subtitle Edit on Linux
----------------------

  
Even though Subtitle Edit is a Windows program, it runs (mostly) well on Linux via [Mono](https://www.mono-project.com/docs/gui/winforms/).  
Note that a dotnet [CLI version](https://github.com/SubtitleEdit/subtitleedit-cli) is also available (no mono).  
  
  
![SE running on Linux](/gfx/se_on_linux.png)  
  
Download the portable version of SE (and not the installer).  
  
Packages required for Ubuntu based distros:

*   sudo apt-get install mono-complete
*   sudo apt-get install libhunspell-dev
*   sudo apt-get install libmpv-dev (libmpv.so)
*   sudo apt-get install tesseract-ocr
*   sudo apt-get install vlc (already installed on some distros, SE uses (libvlc.so))
*   sudo apt-get install ffmpeg (already installed on some distros)

  
Packages required for Arch based distros (like Manjaro):

*   sudo pacman -S mono
*   sudo pacman -S mpv
*   sudo pacman -S hunspell
*   sudo pacman -S ttf-dejavu (Unicode font)
*   sudo pacman -S tesseract
*   sudo pacman -S tesseract-data-eng (or install via "sudo mono SubtitleEdit.exe")

  
Packages required for Fedora:

*   sudo dnf -y install mono-complete hunspell dejavu-sans-fonts tesseract tesseract-langpack-eng vlc vlc-extras ffmpeg

Fedora: To use libmpv you will need to enable [rpmfusion](https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/) and install "mpv mpv-libs" packages + Change "<MpvVideoOutputLinux />" to "<MpvVideoOutputLinux>x11</MpvVideoOutputLinux>" in Settings.xml.  
To use spell check you will need to make a symlink link like this: sudo ln -s /usr/lib64/libhunspell-1.7.so.0 ~/Downloads/SubtitleEdit/libhunspell.so  
  
After unpacking SE and installing the packages, you can start SE by running "mono SubtitleEdit.exe" in a terminal.  
(The "Tesseract302" folder and the two hunspell dll files can be deleted as they are for Windows only.)  
Tesseract languages must be installed via a package - e.g. on Ubuntu "sudo apt-get install tesseract-ocr-eng".  
  
Note that these lib are required (a symlink file may be needed): libc.so.6, libdl.so (libdl.so.2 in SE 3.5.16) Adding a missing symlink for libvlc could look like this: sudo ln -s /usr/lib/x86\_64-linux-gnu/libvlc.so.5.6.0 ~Downloads/SubtitleEdit/libvlc.so  
  
  
Known issues:

*   Setting focus on a control programatically does not work
*   The letter **è** (and some other Unicode characters) will crash SE - read more [in this Github issue](https://github.com/mono/mono/issues/17029)
*   Some languages like Chinese or Arabic might require a different font.
*   Text to bitmap rendering is not working well. In image exporting try "Simple rendering" if you have problems.
*   Winforms layout...

  
  

* * *

Compiling Subtitle Edit
-----------------------

  
Compiling your own version of Subtitle Edit is not that hard :)  
  
If you don't have MS Visual Studio, then download and install [MS Visual Studio Community](https://visualstudio.microsoft.com/vs/community). Then download the Subtitle Edit source code and edit the file "SubtitleEdit.csproj" and remove the following line: _<Exec Command="%22$(SolutionDir)..\\build\_helpers.bat%22 rev %22$(ConfigurationName)%22" />_  
Open "SubtitleEdit.csproj" in Visual Studio, go to Tools -> NuGet Packet Manager -> Manage NuGet packages for Solution... - and click "Restore" (this will download required components).  
Hit F5 and you should be up and running.  
  
Now you can change/add features you want or fix my bugs - if there were any ;)  
  

* * *

Known issues
------------

  
Subtitle Edit has a few known problems!  
  

Problem

Solution

Subtitle Edit does not detect VLC in options (it's grayed out)

SE requires VLC 64-bit version on 64-bit operating systems (use VLC 32-bit on 32-bit operating systems)

Subtitle Edit portable is not working properly in "Program files" folder

Use the installer if you want to have Subtitle Edit in "Program files" (remove portable version before installing)  
The portable version requires write access to it's own folder.

Tesseract 3.0.2 will not run properly

You might need the Microsoft Visual C++ 2008 Redistributable Package: [https://www.microsoft.com/en-us/download/details.aspx?id=29](https://www.microsoft.com/en-us/download/details.aspx?id=29)  
If it still don't work, try to delete "C:\\Program files\\Subtitle Edit", "C:\\Program files (x86)\\Subtitle Edit" and "C:\\Users\\\[Username\]\\App Data\\Roaming\\SubtitleEdit" before re-installing.

Subtitle Edit fails to run from a network drive ("The publisher could not be verified")

If you do not have sufficient access to run Subtitle Edit from a network drive, then copy it to your local hard disk or obtain the needed access

Subtitle Edit fails to display some non-English lines in waveform.

Known error

Whisper will not run on some computers.

Whisper might require a CPU with AVX support and up to 16GB of free RAM.

  
  
Did you not find what you were looking for? Feel free to [email me](mailto:nikse.dk@gmail.com).  
  

* * *

  

### Useful links

Do check out the [Subtitle Edit videos](/subtitleedit/video).  
  
[VideoHelp subtitle forum](https://forum.videohelp.com/forums/42-Subtitle)  
General subtitle forum  
  
[Subtitle Edit forum thread](https://forum.doom9.org/showthread.php?t=162721) on doom9.org  
Forum, mostly related to ripping and encoding  
  
[Ask me anything about subtitling](https://www.proz.com/forum/subtitling/283471-ask_me_anything_about_subtitling.html) by Max Deryagin  
Forum thread about subtitling (mostly related to working as a translator)  
  
[Sub-Talk.net](https://www.sub-talk.net/)  
Forum for [Addic7ed](https://www.addic7ed.com/) - also has [SE tread](https://www.sub-talk.net/topic/107-subtitle-edit-open-source-subtitle-editor/) and [an interesting thread about sync](https://www.sub-talk.net/topic/2827-how-to-resync-subtitles-using-subtitle-edit/?do=findComment&comment=39189)
