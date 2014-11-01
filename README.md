domdombash
==========

Unofficial interface to DomDomSoft Anime Downloader for bash (and therefore *nix systems)

This is an unofficial client application for DomDomSoft Anime Downloader that works on *nix systems.

It depends on xmlstarlet and curl. The path to xmlstarlet should be set in the script itself (the line is near the top, commented).

### Usage

Upon first run, the script will ask a few questions about your setup; where to download anime to, what your domdomsoft anime downloader serial key is (if you have one), and so forth. These are saved in `~/.domdom` so you can delete this folder if you need to change them again later.
Please take note that if you don't have a serial key, you can only download 5 episodes in a 24-hour period.

The script can run interactively or in a batch mode, and is pretty straightforward. In interactive mode, it will first ask for the title of an anime to download. At this point you can also enter `?` to download the anime list and grep through it. Once you've found the anime you're looking for, you can return back to the title selection and input it. The titles need to be entered exactly as they appear in the anime list, so I suggest you just copy and paste it from your search.
Once you've chosen the anime to download, a list of files under that title will be shown, prepended with numbers. You're asked to define a number range to download. You can use `-` and `,` to define this range, so some valid ranges might be `1-12,15,19`, `4-6,3,8`, `1-24`, or just `8`. It's pretty straightforward.
The application will present you with a download directory based on the name of the anime and allow you to change it before it downloads all the files there. Then, off it goes! It will automatically exit when the download is completed.
Some files are in multiple parts, in which case the application will download all the parts and merge them. You can see which part of the current file is being downloaded from the `Downloading...(1/2)` text; in this example, the first part of two total parts is being downloaded.

To run the script in batch mode, execute it with command line arguments. The first argument should be the anime title and the second should be the episode range. So, for example
> `$ ./domdom.bsh "Sword Art Online" "1-2,5"
The episode range can be omitted in which case it will just input the title for you and go to the episode range selection.
Please note that in batch mode, the default download directory is used, and there is no confirmation dialog to change it.

Here's a small sample of it in use:

<pre>
$ ./domdom.bsh
Welcome to Unofficial Bash DomDomSoft Anime Downloader
Original by DomDomSoft, bash version by Suchipi
This script depends on xmlstarlet and curl.

Enter the title of the anime you want to download (or enter "?" to search) and press [ENTER]: ?
Would you like to update the anime list? Enter y or n and press [ENTER]: y
Fetching anime list (this can take some time)...
List downloaded
Enter a search term (or leave blank to exit search) and press [ENTER]: iDOLM@STER
Search Results:
Puchimas!: Petit iDOLM@STER
Puchimas!!: Petit Petit iDOLM@STER
The iDOLM@STER Movie: Kagayaki no Mukougawa e!
Enter a search term (or leave blank to exit search) and press [ENTER]:
Enter the title of the anime you want to download (or enter "?" to search) and press [ENTER]: Puchimas!: Petit iDOLM@STER
Fetching files for Puchimas!: Petit iDOLM@STER...
65 files were found.
1: [Chibiki] Puchimas! - 01 [360p][EB76BA61].mkv
2: [Chibiki] Puchimas! - 02 [360p][1D687174].mkv
3: [Chibiki] Puchimas! - 03 [360p][703CAE68].mkv
4: [Chibiki] Puchimas! - 04 [360p][5D44CECD].mkv
5: [Chibiki] Puchimas! - 05 [360p][18E216D9].mkv
6: [Chibiki] Puchimas! - 06 [360p][EEB42F7D].mkv
7: [Chibiki] Puchimas! - 07 [360p][7AFB4778].mkv
8: [Chibiki] Puchimas! - 08 [360p][FC970609].mkv
9: [Chibiki] Puchimas! - 09 [360p][FA33DEC5].mkv
10: [Chibiki] Puchimas! - 10v2 [360p][52C98E2E].mkv
11: [Chibiki] Puchimas! - 11 [720p][45F21860].mkv
12: [Chibiki] Puchimas! - 12 [360p][BCB94179].mkv
13: [Chibiki] Puchimas! - 13 [360p][3FBF2D9C].mkv
14: [Chibiki] Puchimas! - 14 [360p][3757FD76].mkv
15: [Chibiki] Puchimas! - 15 [360p][D7BCEB3C].mkv
16: [Chibiki] Puchimas! - 16 [360p][545E7F7D].mkv
17: [Chibiki] Puchimas! - 17 [360p][C5B11130].mkv
18: [Chibiki] Puchimas! - 18 [360p][E4A158E0].mkv
19: [Chibiki] Puchimas! - 19 [360p][59562B47].mkv
20: [Chibiki] Puchimas! - 20 [360p][A6CE044B].mkv
21: [Chibiki] Puchimas! - 21 [360p][4CD5C0F3].mkv
22: [Chibiki] Puchimas! - 22 [360p][01A9FE6A].mkv
23: [Chibiki] Puchimas! - 23 [360p][AAE2425C].mkv
24: [Chibiki] Puchimas! - 24 [360p][13B47D7D].mkv
25: [Chibiki] Puchimas! - 25 [360p][6E6CA748].mkv
26: [Chibiki] Puchimas! - 26 [360p][3242C367].mkv
27: [Chibiki] Puchimas! - 27 [360p][1F930F36].mkv
28: [Chibiki] Puchimas! - 28 [360p][1AEB6E9A].mkv
29: [Chibiki] Puchimas! - 29 [360p][3FDF82F5].mkv
30: [Chibiki] Puchimas! - 30 [360p][6A3812E8].mkv
31: [Chibiki] Puchimas! - 31 [360p][6899C764].mkv
32: [Chibiki] Puchimas! - 32 [360p][58199514].mkv
33: [Chibiki] Puchimas! - 33 [360p][A3BB6D56].mkv
34: [Chibiki] Puchimas! - 34 [360p][7E1F6C4B].mkv
35: [Chibiki] Puchimas! - 35 [360p][9157E21D].mkv
36: [Chibiki] Puchimas! - 36 [360p][8E105354].mkv
37: [Chibiki] Puchimas! - 37 [360p][8D9408C9].mkv
38: [Chibiki] Puchimas! - 38 [360p][FE7B67F0].mkv
39: [Chibiki] Puchimas! - 39v2 [360p][C3F4B7E2].mkv
40: [Chibiki] Puchimas! - 40 [360p][F2346E91].mkv
41: [Chibiki] Puchimas! - 41 [360p][AB42AC0B].mkv
42: [Chibiki] Puchimas! - 42 [360p][433184F1].mkv
43: [Chibiki] Puchimas! - 43 [360p][73DCB748].mkv
44: [Chibiki] Puchimas! - 44 [360p][139F3F24].mkv
45: [Chibiki] Puchimas! - 45 [360p][6E3C5666].mkv
46: [Chibiki] Puchimas! - 46 [360p][91C433B7].mkv
47: [Chibiki] Puchimas! - 47 [360p][A823D4F3].mkv
48: [Chibiki] Puchimas! - 48 [360p][0B3BC2DA].mkv
49: [Chibiki] Puchimas! - 49 [360p][C1EF81EA].mkv
50: [Chibiki] Puchimas! - 50 [360p][B544C087].mkv
51: [Chibiki] Puchimas! - 51 [360p][8DE39483].mkv
52: [Chibiki] Puchimas! - 52 [320p][BBE13B64].mkv
53: [Chibiki] Puchimas! - 53 [360p][585A6505].mkv
54: [Chibiki] Puchimas! - 54 [360p][A2E6E431].mkv
55: [Chibiki] Puchimas! - 55 [360p][919AF512].mkv
56: [Chibiki] Puchimas! - 56 [360p][C2997AEC].mkv
57: [Chibiki] Puchimas! - 57 [360p][006E2CE2].mkv
58: [Chibiki] Puchimas! - 58 [360p][E30DE54F].mkv
59: [Chibiki] Puchimas! - 59 [360p][1467AC9F].mkv
60: [Chibiki] Puchimas! - 60 [360p][52738E94].mkv
61: [Chibiki] Puchimas! - 61 [360p][33EABFF7].mkv
62: [Chibiki] Puchimas! - 62 [360p][04DDB4AD].mkv
63: [Chibiki] Puchimas! - 63 [360p][871C3D2A].mkv
64: [Chibiki] Puchimas! - 64 [360p][240B5BE4].mkv
65: [Chibiki] Puchimas! OVA [DVD][480p][205D8295].mkv
Please enter the file number you would like to download and press [ENTER]: 1-65
Files will be downloaded to /mnt/3tb/Media/Anime/Puchimas!: Petit iDOLM@STER. Is this okay? Enter y or n and press [ENTER]: y
File Selected: [Chibiki] Puchimas! - 01 [360p][EB76BA61].mkv
Downloading...(1/1)
######################################################################## 100.0%
File Selected: [Chibiki] Puchimas! - 02 [360p][1D687174].mkv
Downloading...(1/1)
######################################################################## 100.0%
File Selected: [Chibiki] Puchimas! - 03 [360p][703CAE68].mkv
Downloading...(1/1)
######################################################################## 100.0%
File Selected: [Chibiki] Puchimas! - 04 [360p][5D44CECD].mkv
Downloading...(1/1)
##################################################                        70.8%
</pre>
