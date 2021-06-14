To start interlok you can use one of the two scripts in this directory; 'start-interlok.bat' on Windows or 'start-interlok' otherwise.

If you want to "run as Windows services" then we suggest using something like https://github.com/winsw/winsw to wrap the java process.

We advise to follow their documentation but one way of doing it is as follow:

- Download the appropriate WinsSw.exe (you can rename it if you want) and put it into this directory.
- Add a new file WinsSw.xml (with the same name as the exe file) next to  it with the following content:

<service>
  <id>interlok</id>
  <name>Interlok</name>
  <description>This service runs Interlok.</description>
  <executable>C:\path\to\Interlok\bin\start-interlok.bat</executable>
  <log mode="reset"></log>
  <logpath>C:\path\to\Interlok\logs</logpath>
</service>

- Don't forget to change the executable and logpath paths.
- Run as an administrator: WinsSw.exe install.
- There should now be a service called Interlok.
- You can start and stop this service as any other Windows services.


Id you want to run Interlok on Mac or Linux you can use the 'start-interlok' script.
However the executable permission may not alway be set up and you may need to do that manually by entering: 'chmod +x ./start-interlok' in a terminal.