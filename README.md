The application demonstrates an issue with dependency resolution when a dependency is published to maven,
using the maven-publish plugin, with multiple publications.

**Please note, this is not an issue with composite projects.**

To demo:

   - from *libb* directory run `gradle publishToMavenLocal`
   - from *liba* directory run `gradle publishToMavenLocal`
   - from *app* directory run `gradle dependencies`

Result:

   - all configurations fail to show transitive dependencies of `org.example:liba:0.1-SNAPSHOT`

To fix:

   - in *liba/build.gradle* comment out `publication` `someDocs`