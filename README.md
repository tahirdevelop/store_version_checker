# store_version_checker

### Installing

Add App Version Checker to your pubspec:

```yaml
dependencies:
  store_version_checker: any # or the latest version on Pub
```

### Usage

```dart
  final _checker = StoreVersionChecker();

  @override
  void initState() {
    super.initState();
    checkVersion();
  }
  
  void checkVersion() async {
    _checker.checkUpdate().then((value) {
      print(value.canUpdate); //return true if update is available
      print(value.currentVersion); //return current app version
      print(value.newVersion); //return the new app version
      print(value.appURL); //return the app url
      print(value.errorMessage); //return error message if found else it will return null
    });
  }
```