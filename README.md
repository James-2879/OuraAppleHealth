# OuraAppleHealth
## V1 (deprecated)

Apple Shortcuts for exporting Oura data to Apple Health using the _V1 API_.

> [!IMPORTANT]
> These shorcuts use the soon-to-be deprecated V1 Oura API; see the _main_ branch for up-to-date V2 shortcuts. V1 also does not include blood oxygen.

## Table of contents
1. [Introduction](#introduction)
    1. [Set-up](#set-up) 
2. [Notes](#notes)
    1. [Lowest Resting Heart Rate](#rhr)
    2. [Body Temperature](#temp)
3. [Contributing](#contributing)

## Introduction <a name="introduction"></a>
These shortcuts aim to export four data types from Oura to Health (click the links below to download each shortcut).
- [Average Heart Rate Variability](https://www.icloud.com/shortcuts/d6378e0918094124b2bfc0cd2e818aec)
- [Lowest Resting Heart Rate](https://www.icloud.com/shortcuts/f2d51df1c47041958923c53329ec5c13)
- [Body Temperature](https://www.icloud.com/shortcuts/84eb63dad918427884cf74dd81cf5801)

> [!IMPORTANT]
> These shortcuts are **not** a way to get around the Oura Subscription, they need to be able to access the Oura API, which is only possible **with** a subscription. Note that for *Generation 2* users this should not be a requirement, only for *Generation 3* users.

### Set-up <a name="set-up"></a>
This is quick and simple.
1. Download the desired shortcuts as linked in the introduction
2. Generate an Oura _Personal Access Token_ (API key) [here](https://cloud.ouraring.com/personal-access-tokens)
3. Add your key to the top of each shortcut (open up the shortcut in the app and there is a 'Text' block where the key should be pasted)
4. Set up an _Automation_ in the Shortcuts App to run these shortcuts automatically every day

Done!

> [!TIP]
> These shortcuts can only run once you have opened the app in the morning to sync your sleep data. Therefore it is recommended to set the automation to run at a time when you know you will have opened the Oura app, or the scripts will fail to run. It is suggested to set the time for sometime in the afternoon, unless you tend to sync your data as soon as you get up. The data is written as if it was added at 6 am every morning, because this is generally the midpoint of my sleep, you may want to change this to be earlier or later. At some point I may alter it so that the shortcut calculates the midpoint of the sleep period and then writes it to that time.

> [!NOTE]
> These shortcuts are designed for iPhone, and will not run on MacOS as there is no native Apple Health API available.

## Notes <a name="notes"></a>

### Lowest Resting Heart Rate <a name="rhr"></a>

This pulls the single **lowest** heart rate captured over the night, and logs it as _Resting Heart Rate_ in Apple Health. This is different to the _Heart Rate_ metric, which Oura automatically syncs to Health.

### Body Temperature <a name="temp"></a>

There is no _Skin Temperature_ metric in Apple Health, which is what Oura measures. Instead, this shortcuts adds 37 celsius to the temperature change recorded in Oura, and logs it to the _Body temperature_ metric. This evidently isn't that scientific, but this allows you to identify trends easily in the Health app, particularly as negative temperature values are not allowed for obvious reasons. The value can be changed from 37 to an alternative number in the shortcut if that is more preferable.

> [!NOTE]
> Oura _should_ store temperature data in celsius, not fahrenheit, so 37C should automatically translate to 98.6F if you use non-metric units in Health/Oura. Please let me know if this is not the case.

## Contributing <a name="contributing"></a>

If you would like to contribute to the shortcuts, please fork this repo and create a _Pull request_ which will be reviewed.

Alternatively, if you have an issue or suggestion, please create an _Issue_ for this repo.
