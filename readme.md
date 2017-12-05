# Infinite Scroll

So, the flat list is a pretty interesting way of dealing with elements, and as I have checked before, the flatlist in iOS is implemented using a UICollectionView (in Android is implemented with a ListView of sorts), meaning the items will be rendered as you are scrolling.

This is a great way way to maintain the application performance as you bind through a collection of items (assuming the list might be large), meaning the application does not need to render everything pre-emptively if it does not need to do that but then... you will still receive the impact of downloading a large dataset, maintain that in memory of flush it somewhere, etc.

In here, you are presented with an implementation of an infinite data source, making this problem quite interesting... How to you interact with a datasource that is infinite in nature?

If you have done something similar to `Haskell` you might be familiar with the concept of lazy lists and lazy evaluation... This means, let's evaluate strictly the minimum amount of data when is required. This concept is presented by [Spencer Carli in his flat list demo](https://github.com/spencercarli/react-native-flatlist-demo). The application loads and decides you might be accessing the first (maybe a bit more) page and fetches that information, `FlatList` then is configured to request more information as the user hits certain threshold.

This way, you enforce a minimum dataset to be transfer, if the information is close to what the user needs then you will be saving data transfer, time and resources. Win!

This exercise is about listing user information as performant as possible. Fetching a small dataset and expanding it as we browse the data.

## How to run this code?

```sh
# Cloning the repo to 'infinityscroll'
git clone git@github.com:rodrigoelp/reactnative-typescript-exercise-13.git infiniteScroll
# Changing directory
cd infiniteScroll
# Installing dependencies
yarn # if you have not installed yarn, then change it to: npm install
# Compiling the typescript code
./node_modules/.bin/tsc
# Launching the react-native development server
open -a Terminal "`react-native start`"
# Compiling the code for ios and deploying it to the simulator
react-native run-ios # optionally, type: react-native run-android
# Alternatively, you could comment the line above and run the two lines below.
# open -a Terminal "`react-native run-ios`"
# open -a Terminal "`react-native run-android`"
```
