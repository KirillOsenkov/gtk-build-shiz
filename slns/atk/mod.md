 * Download [ATK 2.14.0](http://ftp.gnome.org/pub/gnome/sources/atk/2.14/atk-2.14.0.tar.xz)
 * Extract to `C:\mozilla-build\hexchat`
 * In `build\win32\vs12\atk-build-defines.props`, replace:
	* `intl.lib` with `libintl.lib`
 * In `build\win32\vs12\atk-install.props`:
	*  add to `AtkDoInstall` `copy $(BinDir)\*.pdb $(CopyDir)\bin`
 * In `build\win32\vs12\atk-version-paths.props`, replace:
	* `<GlibEtcInstallRoot>$(SolutionDir)\..\..\..\..\vs$(VSVer)\$(Platform)</GlibEtcInstallRoot>` with
`<GlibEtcInstallRoot>$(SolutionDir)\..\..\..\..\..\..\gtk\$(Platform)</GlibEtcInstallRoot>`
	* `<CopyDir>$(GLibEtcInstallRoot)</CopyDir>` with
`<CopyDir>..\..\..\..\atk-2.14.0-rel</CopyDir>`
	* `<AtkSeparateVSDllSuffix>-1-vs$(VSVer)</AtkSeparateVSDllSuffix>` with
`<AtkSeparateVSDllSuffix>-1.0</AtkSeparateVSDllSuffix>`
 * In `build\win32\vs12\atk.vcxproj`:
	*  add `<Import Project="..\..\..\..\stack.props" />`
	* Remove all `<Optimization>` lines
 * In `build\win32\vs12\install.vcxproj`:
	* replace `AtkEtcInstallRoot` with `GlibEtcInstallRoot`
 * Open `build\win32\vs12\atk.sln` with VS
 * Select `Release|Win32` configuration
 * Build in VS
 * Release with `release-x86.bat`
 * Extract package to `C:\mozilla-build\hexchat\build\Win32`
