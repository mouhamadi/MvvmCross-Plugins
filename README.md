## MvvmCross-Plugins

MvvmCross provides a plugin system to allow developers to provide IoC-injectable functionality at run-time.

This functionality can include both portable and platform-specific code, and can easily be substituted for mock implementations during tests.

Plugins are really just a layer on top of MvvmCross's IoC/Service Resolution implementation - they use a filename-based convention to make it easier to share cross-platform blocks of functionality.

For more background on the MvvmCross IoC and Service Resolution APIs, see [Service Location and Inversion of Control](https://github.com/slodge/MvvmCross/wiki/Service-Location-and-Inversion-of-Control).

**See the Readme.md file of each plugin for more details about that plugin**

### Questions & support

* [StackOverflow](http://stackoverflow.com/questions/tagged/mvvmcross)
* [Xamarin forums](http://forums.xamarin.com)
* [Slack](https://xamarinchat.herokuapp.com/) join the mvvmcross channel after you are in


### Documentation and Examples

**The [MvvmCross-Samples](https://github.com/MvvmCross/MvvmCross-Samples) repo contains the latest samples. See the [MvvmCross Wiki](https://github.com/MvvmCross/MvvmCross/wiki) for additional articles and information.**

### FAQ: Why use lots of small plugins?

This question is asked quite frequently.

Why does MvvmCross contain lots of small plugins rather than just including the functionality within the core package? I quite frequently hear the (valid) complaint that Mvx would be easier to use if there weren't so many individual assemblies to reference and so many namespaces to use. 

The motivation for using lots of separate small modules for this is partly to do with good software architecture, and partly to do with performance.

On the architectural side, providing small self-contained (tightly-coupled) plugins as individual modules makes them easier to write, easier to modify, easier to test and easier to replace.

On the performance side, making the plugins optional means that less unnecessary code is required in apps both at build time and at startup time. If an app doesn't need a module - for example, geo-location - then it simply doesn't reference that plugin.

As for the main complaint - about the referencing of so many assemblies - I do agree that the need to reference additional plugins can make 'getting started' with MvvmCross more difficult than the v1 of MvvmCross where all plugin-type functionality was baked into a single assembly for each platform. However, I hope this difficulty can be lessened through the use of package managers like nuget and the Xamarin component store, and I believe that once over the 'getting started' hump, then the plugins deliver significant benefits which were worth any initial pain.

Further, because MvvmCross itself is so heavily based on replaceable, extensible plugins, I hope that this will encourage others to author, modify and share additional components and extensions, and that these components will be shareable with other platforms beyond MvvmCross.

### Contribute!

Some of the best ways to contribute are to try things out, file bugs, and join conversations.

* [Pull requests](https://github.com/MvvmCross/MvvmCross-Plugins/pulls): [Open](https://github.com/MvvmCross/MvvmCross-Plugins/pulls?q=is%3Aopen+is%3Apr)/[Closed](https://github.com/MvvmCross/MvvmCross-Plugins/pulls?q=is%3Apr+is%3Aclosed)
* [Issues](https://github.com/MvvmCross/MvvmCross-Plugins/issues): [Open](https://github.com/MvvmCross/MvvmCross-Plugins/issues?q=is%3Aopen+is%3Aissue)/[Closed](https://github.com/MvvmCross/MvvmCross-Plugins/issues?q=is%3Aissue+is%3Aclosed)

If you would like to help make MvvmCross even better, then please do:

* new code - including pull requests via GitHub - or you can fork the project and build your own extensions
* new plugins - can be hosted in the [MvvmCross-Plugins](https://github.com/MvvmCross/MvvmCross-Plugins) repository
* please do blog about your adventures with MvvmCross - we're currently light on documentation!
* if you use the framework, then please let me know - we love to see what people are doing with it

### Acknowledgements

* Thanks to [benschi11](https://github.com/benschi11) for the SQLite-PCL plugin

### Licensing

MvvmCross is licensed under the [MS-PL License](http://opensource.org/licenses/ms-pl.html)

System.Collections.Immutable.ImmutableDictionary used in the [DownloadCache plugin][https://github.com/MvvmCross/MvvmCross-Plugins/tree/master/DownloadCache/MvvmCross.Plugins.DownloadCache] is licensed under the [MIT-X11 License][https://opensource.org/licenses/MIT].
