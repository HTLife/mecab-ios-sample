# MeCab Sample App for iOS
Sample Swift project for [MeCab](https://github.com/taku910/mecab), a Japanese tokenizer/morphological analyzer. Updated for iOS 12.x and Swift 5.

<img src="https://user-images.githubusercontent.com/1572318/55723208-68daf700-5a43-11e9-80bf-c97f831655e8.PNG" width="200px">

Use the following command to clone and get the mecab-ios submodule as well:

```
git clone --recurse-submodules https://github.com/landonepps/mecab-ios-sample
```

## Setting up your own project

Tutorial video
https://www.youtube.com/watch?v=oprLupr228A&feature=youtu.be

1. Create a new Xcode Swift project and make it a git repository (or let Xcode do it for you).

2. Add `mecab-ios` as a submodule by executing the following command in your project's repository:

```
git submodule add https://github.com/landonepps/mecab-ios-sample
cd mecab-ios-sample
git submodule update --init --recursive
```

3. Select `Add Files to "ProjectName"...` from the Xcode menu and choose `mecab.xcodeproj` in the `mecab-ios` folder created by adding the submodule. This will import the project and all the necessary files.

4. Drag `mecabrc` from the top directory of this repository into your project. Make sure to select `Copy items if needed`.

5. Open the `mecab-ios` folder in your project's folder and drag the `ipadic` folder into your project. (The files are already in your project's directory. so it doesn't matter if you have `Copy items if needed` selected or not.)

6. Click on your project file, go to the target's `General` tab, and add `mecab.framework` in the `Embedded Binaries` section near the bottom.

7.  Make sure to `import mecab` wherever you need to use it.

8.  You can now call the MeCab library's functions directly from Swift – e.g.

```swift
let mecab = mecab_new2("-d \(Bundle.main.resourcePath!)")
```

9.  Dealing with MeCab directly is not ideal, so feel free to use the Swift wrappers that I made for this sample project: `Tokenizer.swift` and `Token.swift`.

10. Clean and build.

These instrucations are based on the ones from https://github.com/lxmmxl56/iPhone-libmecab

Special thanks to [Joseph Toronto on Stack Overflow](http://stackoverflow.com/a/37891729/3295398) for coming up with the original steps.
