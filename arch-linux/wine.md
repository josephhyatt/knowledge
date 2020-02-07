# Wine

* Make directory
  * `mkdir wine`
* Move to `wine` directory
  * `cd wine`
* Create fresh `wine bottle`
  * `WINEARCH=win32 WINEPREFIX=~/wine/<bottle name> winetricks`
* In `winetricks`
  * `Select the default wineprefix`
  * `Install a Windows DLL or component`
    * `d3dx9`
    * `dotnet35`
    * `dotnet452`
    * `vcrun2003` - `vcrun2013`
  * \`\`

