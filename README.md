# calabashCrossPlatform

This is a brand new calabashCrossPlatform demo

## What is calabash
[calabash offical site](http://calaba.sh/)

[calabash for ios guide](https://github.com/calabash/calabash-ios)

[calabash for android guide](https://github.com/calabash/calabash-andorid)

## How can it really cross platform?
see demo[here](https://developer.xamarin.com/guides/testcloud/calabash/xplat-best-practices/)

## Requirement
1. MacOS 10.10 or 10.11 or something like unix
2. Xcode 6 or 7
3. iOS Devices >= 7.1
4. iOS Simulators >= 8.0
5. Android SDK

## Installation
1. install Ruby [This way](https://www.ruby-lang.org/en/documentation/installation/)
2. install calabash-android [This way](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md)
3. install calabash-ios

using:
`bundle`

## build your App
1. Android build move your app to this folder
2. IOS build [see this](https://github.com/calabash/calabash-ios#step-1-link-calabashframework)
3. set APP path
`export APP=/where/you/place/your/ios/app`
to add enviroment parameters for ios APP
4. modify config/cucumber.yum set APP_BUNDLE_PATH the same ass APP enviroment parameters

## What's the files means

.

├── Gemfile						#The gem file for requirement

├── config						#config file

│   ├── cucumber.yml					#for cross platform to load different ruby file

├── features						#saving test case and implement

│   ├── android						#androind implement and support package

│   │   ├── pages					#android implement for pages of app

│   │   │   ├── xx.rb					#class and API for a page

│   │   └── support					#android support packages

│   │       ├── app_installation_hooks.rb

│   │       ├── app_life_cycle_hooks.rb

│   │       ├── env.rb

│   │       └── hooks.rb

│   ├── ios						#ios implement and support package

│   │   ├── pages					#ios implement for pages of app

│   │   │   ├── xxx.rb					#class and API for a page

│   │   └── support					#support packages

│   │       ├── 01_launch.rb

│   │       ├── 02_pre_stop_hooks.rb

│   │       └── env.rb

│   ├── login.feature					#test featueres

│   └── step_definitions				#define steps API for both android and ios

│       ├── calabash_steps.rb				#load original steps

│       └── my_first_steps.rb				#self define step

└── test_servers					#saving the apk rebuild by calabash


## How to run
1. ios:

`bundle exec cucumber -p ios`

2. android

`calabash-android run xxx.apk -p android`


