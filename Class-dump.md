# Class-dump

Github地址： https://github.com/nygard/class-dump
主页：http://stevenygard.com/projects/class-dump

下载并打开安装包 http://stevenygard.com/download/class-dump-3.5.dmg（版本可能会随时更新）
将class-dump可执行文件放到/usr/bin下或者/usr/local/bin

```ruby
class-dump 3.5 (64 bit)
Usage: class-dump [options] <mach-o-file>

  where options are:
        -a             show instance variable offsets
        -A             show implementation addresses
        --arch <arch>  choose a specific architecture from a universal binary (ppc, ppc64, i386, x86_64)
        -C <regex>     only display classes matching regular expression
        -f <str>       find string in method name
        -H             generate header files in current directory, or directory specified with -o
        -I             sort classes, categories, and protocols by inheritance (overrides -s)
        -o <dir>       output directory used for -H
        -r             recursively expand frameworks and fixed VM shared libraries
        -s             sort classes and categories by name
        -S             sort methods by name
        -t             suppress header in output, for testing
        --list-arches  list the arches in the file, then exit
        --sdk-ios      specify iOS SDK version (will look in /Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS<version>.sdk
        --sdk-mac      specify Mac OS X version (will look in /Developer/SDKs/MacOSX<version>.sdk
        --sdk-root     specify the full SDK root path (or use --sdk-ios/--sdk-mac for a shortcut)
```

## 例子
class-dump AppKit:
```ruby
class-dump /System/Library/Frameworks/AppKit.framework
```
class-dump UIKit:
```ruby
class-dump /Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS4.3.sdk/System/Library/Frameworks/UIKit.framework
```
class-dump UIKit and all the frameworks it uses:
```ruby
class-dump /Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS4.3.sdk/System/Library/Frameworks/UIKit.framework -r --sdk-ios 4.3
```
class-dump UIKit (and all the frameworks it uses) from developer tools that have been installed in /Dev42 instead of /Developer:
```ruby
class-dump /Dev42/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS5.0.sdk/System/Library/Frameworks/UIKit.framework -r --sdk-root /Dev42/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS5.0.sdk
```

使用dumpdecrypted给App砸壳后
```ruby
class-dump --arch armv7 hello.decrypted -H -o ./heads/
```

# class-dump-z
主页：https://code.google.com/p/networkpx/wiki/class_dump_z
使用wiki： https://code.google.com/archive/p/networkpx/wikis/class_dump_z.wiki

将class-dump-z可执行文件放到`/usr/bin`下或者`/usr/local/bin`