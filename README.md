# Adobe Connect Exporter

Developed by Franck Dernoncourt and edited and customized by Parsa Hejabi. Further modification was done for other universities by Parsa Nasirimehr.
An exporter for Adobe Connect recorded sessions for virtual classes held for Universities using Adobe Connect.

## How to use

**CAUTION:** This script is a work in progress. The code does work for Shahid Beheshti but other universities have not been tested ( mainly because i do not have their server ips :D ) .

- First of all grab a link provided by university for one of the classes and append `output/felan.zip?download=zip` to the end of the link.

  - For example: <http://194.225.24.94/p9uxd7gt6zoc/> (This is a link provided by university.)

  - Changed link would be like:
  <http://194.225.24.94/p9uxd7gt6zoc/output/felan.zip?download=zip>

- When you hit enter you have to provide your `username` and your `password`. Make sure before hitting `login` button open developer view on your browser and go to the `network` section.

![Chrome network section](https://github.com/TheRogue76/AdobeConnectExporter/blob/master/images/Chrome.png)

- When you hit enter your browser starts downloading a zip file and a record is added in the `network` section. click on that record and in the `headers` tab see `Request Headers` and copy the ```Cookie: ...``` text completely.

- Create `cookie.txt` file beside your python file and paste the copied text in there, save it and close it.

- Make sure that you have `wget`, `unzip` and `ffmpeg` installed and accessable from your `terminal` or `cmd` because this script is using these tools.

- Now you can enter ```python3 AdobeConnectExporter.py http://194.225.24.94/po68hagu1ncb/``` OR ```python3 AdobeConnectExporter.py po68hagu1ncb``` OR ```python3 AdobeConnectExporter.py http://194.225.24.94/p9uxd7gt6zoc/output/felan.zip```

- At this point, a prompt is shown asking you to define which university you are from. You can select Shahid beheshti, KNTU or just select the third option and give the server ip yourself and output would be a single video file
