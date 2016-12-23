#### gradle basic
#### why gradle
##### compare with existing tools
- Ant is extremlly flexible
- Maven offers rigid standards and promotes convention but a bit overbearing
- gradle sits inbetween
#### features
- gradle intends to be a means of developing organization- and porject-specific build standards. it is a toolkit for developing and extending thoses standards wth a rich, descriptive language.
- XML is the wrong format for a build file
- Groovy relieves much of the frustration develpers have faced in lacking control flow and other constructs in Ant or Maven
- Domain Specific Language

#### grammar
- left shift `<<`
- closure `{...}`
- task configuration
    - run before task execution
    - is to setup variables and context that turns task into a rich object model
    - build configuration code runs every time
- tasks are objects, inherits from `DefaultTask`
- Methods of `DefaultTask`
    - `dependsOn`
    - `doFirst`
    - `doLast`
    - `onlyIf`
- Properties of `DefaultTask`
    - `didWork`
    - `enabled`