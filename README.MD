# How to clone this properly

    git clone --recursive git@github.com:solven-eu/cleanthat-showcases.git

source : https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules

# How to test some Cleanthat mutator

See https://github.com/solven-eu/cleanthat/tree/master/maven#cleanthatapply

For instance:

    mvn io.github.solven-eu.cleanthat:cleanthat-maven-plugin:apply -Dcleanthat.mutators=SafeAndConsensual -Dcleanthat.mutators=SafeButNotConsensual -Dcleanthat.includeDraft=true

Then check the results with:

    git diff --submodule=diff

Then reset the sub-modules with:

    git reset --hard --recurse-submodules

## While developping a new mutator:

First in cleanthat repository:

    mvn install -pl : :maven -am
    
Then in this repository:

    mvn io.github.solven-eu.cleanthat:cleanthat-maven-plugin:2.12-SNAPSHOT:apply -Dcleanthat.mutators=SafeButControversialMutators -Dcleanthat.includeDraft=true

# How has this been built

https://github.com/trending/java

```
git submodule add git@github.com:seata/seata.git seata
git submodule add git@github.com:TheoKanning/openai-java.git openai-java
git submodule add git@github.com:spring-projects/spring-boot.git spring-boot
[...]
```