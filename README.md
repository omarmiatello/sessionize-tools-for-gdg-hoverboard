# Load data from Sessionize to Hoverboard v2
[https://sessionize.com]() --> [https://github.com/gdg-x/hoverboard]()

### Project Status
Experiment

## Examples: How to use

- [Configure Hoverboard](https://github.com/gdg-x/hoverboard/blob/master/docs/tutorials/set-up.md) first
- Make sure `yarn` is installed
- Start `firestore_download.sh`
- Configure options in [SessionizeTools.kt](src/main/kotlin/SessionizeTools.kt)

```kotlin
// Example Config

const val HOVERBOARD_DAY1 = "2018-10-06"
const val isFirestoreBackupEnabled = false  // generate new files for backup
const val isForceUpdateSessionize = false   // update sessionize.json every launch?
const val canUpdateSpeakerData = false      // can update speaker data (es: new bio)
const val sessionizeUrl = "https://sessionize.com/api/v2/y2kbnktu/view/all"
```

- Start `main()` in [SessionizeTools.kt](src/main/kotlin/SessionizeTools.kt) (note you can execute only some function)

```kotlin
// Example Run!

fun main() {
    // NOTE: You can comment/remove
    // SessionizeTools.sessionizeToHoverboard() // REMOVED IN THIS EXAMPLE!
    // SessionizeTools.buildSocialMessage()     // REMOVED IN THIS EXAMPLE!
    SessionizeTools.buildAgenda()               // Build agenda from backup folder!
}
```

- Verify that everything is fine and then run `firestore_upload.sh` (NOTE: uncomment line `#yarn firestore:copy backup/schedule.json schedule` if needed)


### Used by:
- [GDG Milano](https://www.meetup.com/it-IT/GDG-Milano/)
   - [DevFest Milano 2018](https://devfest2018.gdgmilano.it/) | [https://github.com/gdgmilano/devfest2018/tree/devfest2018/tools-data-sessionize](https://github.com/gdgmilano/devfest2018/tree/devfest2018/tools-data-sessionize)
