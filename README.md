# Adobe Connect Exporter

Developed by Franck Dernoncourt and edited and customized by Parsa Hejabi. A further modification was done for other universities by Parsa Nasirimehr.
An exporter for Adobe Connect recorded sessions for virtual classes held for Universities using Adobe Connect.

## How to use

**CAUTION:** This script is a work in progress. The code does work for Shahid Beheshti but other universities have not been tested (mainly because I do not have their server IP addresses :D).

Please add the URL provided by your university in the `ipAddresses.txt` file.

- First of all grab a link provided by university for one of the classes and append `output/felan.zip?download=zip` to the end of the link.

  - For example <http://194.225.24.94/p9uxd7gt6zoc/> (This is a link provided by the university.)

  - A changed link would be like:
    <http://194.225.24.94/p9uxd7gt6zoc/output/felan.zip?download=zip>

- When you hit enter you have to provide your `username` and your `password`. Make sure before hitting the `login` button open developer view on your browser and go to the `network` section.

![Chrome network section](https://github.com/ParsaHejabi/AdobeConnectExporter/blob/master/images/Chrome.png)

- When you hit enter your browser starts downloading a zip file and a record is added in the `network` section. Click on that record and in the `headers` tab see `Request Headers` and copy the `Cookie: ...` text completely.

- Create `cookie.txt` file beside your python file and paste the copied text in there, save it and close it.

  - Your `cookie.txt` file should look like:
    `Cookie: ...`

- Make sure that you have `wget`, `unzip` and `FFmpeg` installed and accessible from your `terminal` or `cmd` because this script is using these tools.

- Now you can enter commands like:

  - `python3 AdobeConnectExporter.py http://194.225.24.94/po68hagu1ncb/`
  - `python3 AdobeConnectExporter.py po68hagu1ncb`
  - `python3 AdobeConnectExporter.py po68hagu1ncb.zip`

- At this point, a prompt is shown asking you to define which university you are from. You can select Shahid Beheshti, KNTU or just select the third option and give the server IP yourself and output would be a single video file

**Attention:** If you open the zip file downloaded from the URL you will see different `.flv` files. Ones started with `screenshare_*.flv` and `cameraVoip_*.flv` are the ones containing voices and videos of the live class. This script tries to combine these voices and videos and output one video file. In numerous cases there may be no `screenshare_.flv` files or the sum of voices and videos doesn't match. these cases lead to failure in outputting a correct video.
