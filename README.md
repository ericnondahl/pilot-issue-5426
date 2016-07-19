# pilot-issue-5426
Sample libgdx app for pilot issue https://github.com/fastlane/fastlane/issues/5426

App Setup
* Add app ID `com.pilotissue.game` to your apple dev account
* Create and install a distribution provisioning profile for the app ID `com.pilotissue.game`
* Create an itunesconnect app using the `com.pilotissue.game` ID

Create IPA
* Clone repo
* Replace values in lines 59 and 60 of `libgdx-game/build.gradle` with your provisioning profile UUID and the ID of your distribution security identity found by running `security find-identity`
* To build IPA, cd to libgdx-game directory and run gradle build: `./gradlew createIPA`, wait patiently
* You should see an IPA file in `libgdx-game/ios/build/robovm`

Upload via pilot
* Install fastlane pilot `sudo gem install pilot`
* `pilot upload --ipa ios/build/robovm/IOSLauncher.ipa --username something@something.com --skip_submission --skip_waiting_for_build_processing`

