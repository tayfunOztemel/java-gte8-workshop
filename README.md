# java-gte8-workshop

## Setup

### Installing JDK 11 Manually
`brew update`<br/>
`brew tap homebrew/cask-versions`<br/>
One of:<br/>
`brew cask install java`<br/>
`brew cask reinstall java`<br/>

To reinstall JDK 8 if gets overridden<br/>
`brew cask install java8`<br/>

### Install with SDKMAN! (Optional)
If you have multiple JDKs installed and need to witch between them<br/>
`curl -s "https://get.sdkman.io" | bash`

Installing JDK<br/>
`sdk install java 11`

Adding already installed versions<br/>
`sdk install java 11 /Library/Java/JavaVirtualMachines/jdk-11.jdk/Contents/Home/`

Setting global/local version<br/>
`sdk default java 11`
`sdk use java 11`

## Compiling and Running Modules

`javac -d target/mods/provider --module-path provider $(find provider -name "*.java")`<br/>
`javac -d target/mods/consumer --module-path target/mods/provider:consumer $(find consumer -name "*.java")`<br/>
`jlink --module-path target/mods/ --add-modules consumer --output myJre --launcher consumer=consumer/consumer.Consumer`<br/>
`./myJre/bin/consumer`<br/>
