[![Donation](https://img.shields.io/badge/donate-please-brightgreen.svg)](https://www.paypal.me/janrabe) [![About Jan Rabe](https://img.shields.io/badge/about-me-green.svg)](https://about.me/janrabe) 
# TimeBomb [![](https://jitpack.io/v/kibotu/TimeBomb.svg)](https://jitpack.io/#kibotu/TimeBomb) [![Javadoc](https://img.shields.io/badge/javadoc-SNAPSHOT-green.svg)](https://jitpack.io/com/github/kibotu/TimeBomb/master-SNAPSHOT/javadoc/index.html) [![Build Status](https://travis-ci.org/kibotu/TimeBomb.svg?branch=master)](https://travis-ci.org/kibotu/TimeBomb) [![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)  [![Gradle Version](https://img.shields.io/badge/gradle-3.1-green.svg)](https://docs.gradle.org/current/release-notes) [![Retrolambda](https://img.shields.io/badge/java-8-green.svg)](https://github.com/evant/gradle-retrolambda) [![Licence](https://img.shields.io/badge/licence-Apache-blue.svg)](https://raw.githubusercontent.com/kibotu/BloodHound/master/LICENSE)

## Introduction

Blocks the user from keep using the App after a period of time based on build time. Mainly to have control preview versions handed out using e.g.: hockey or fabric.

![Screenshot](https://raw.githubusercontent.com/kibotu/TimeBomb/master/screenshot.png)

## How to install

    compile 'com.github.kibotu:TimeBomb:-SNAPSHOT'

## How to build

    graldew clean build
    
### CI 
    
    gradlew clean assembleRelease test javadoc
    
#### Build Requirements

- JDK7, JDK8
- Android Build Tools 24.0.3
- Android SDK 24 

## How to use

1. Add to build date to [defaultConfig](https://github.com/kibotu/TimeBomb/blob/master/app/build.gradle#L15) 

        buildConfigField "String", "BUILD_DATE", "\"" + new Date().getTime() + "\""

2. Invoke check [at app start](https://github.com/kibotu/TimeBomb/blob/master/app/src/main/java/net/kibotu/timebomb/app/MainActivity.java#L17)
   
        TimeBomb.bombAfterDays(this, BuildConfig.BUILD_DATE, 14);

(Optional) Adapt Message in string.xml 

    <string name="time_bomb_message">This Version is no longer Supported. Please update.</string>

## Contributors

[Jan Rabe](jan.rabe@kibotu.net)

###License
<pre>
Copyright 2016 Jan Rabe

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
</pre>