Rebuilding artifacts from (Maven) Central Repository
====================================================

[![Reproducible Builds](https://reproducible-builds.org/images/logos/rb.svg) an independently-verifiable path from source to binary code](https://reproducible-builds.org/)

As part of [Reproducible Builds efforts for the JVM](https://reproducible-builds.org/docs/jvm/), this "**Reproducible Central**" project is an attempt at:
1. writing [`.buildspec`rebuild instructions](BUILDSPEC.md) for the artifacts available in the [Central Repository](https://search.maven.org/),
equivalent to the packaging instructions that are maintained by every Linux distribution
(for example Debian's [debian/rules](https://www.debian.org/doc/debian-policy/ch-source#s-debianrules) or ArchLinux's PKGBUILD), whatever the build tool used (Central Repository is not used by Maven only)
2. show the level of reproducibility obtained using previous instructions: how many output files from the rebuild are strictly equal to reference in Central Repository, how many output files are not yet reproducible and should be improved before the next release?

## What Can I Do?

<details><summary><b>Rebuild Yourself To Check Results</b></summary>

 - <details><summary><b>Prerequisites</b></summary>
    
    * [Docker](https://www.docker.com)
    
    * `dos2unix` - DOS to MAC/UNIX text file format converter. 
      
      Can be installed via [homebrew](https://brew.sh) on MAC via: `brew install dos2unix`.
   </details>

You can rebuild a project release by running:
```
./rebuild.sh content/<path/to/...>/<project>-<version>.buildspec
```
`rebuild.sh` script will use the build specification file (= [`.buildspec` file](BUILDSPEC.md)) to choose a Docker image to rebuild the project and check output against Central Repository reference binaries.

</details>

<details><summary><b>Contribute A New `.buildspec`</b></summary>

If you know a project released to Central Repository that is expected to provide Reproducible Builds, please tell us by opening an issue with details.

You can also choose one from our [list of projects waiting for a `.buildspec`](https://github.com/jvm-repo-rebuild/reproducible-central/labels/buildspec): follow our [instructions to write a new `.buildspec`)](BUILDSPEC.md#writing-a-new-buildspec) that you can contribute back with a PR.

</details>

<details><summary><b>Improve Reproducibility Score Of A Project Release</b></summary>

If a rebuild published here is not fully reproducible (it has some :warning:), there is an issue: please help to improve the situation.

You'll need to rebuild the release yourself (see previous instructions), then use [diffoscope](https://diffoscope.org/) to easily explore precise difference
between reference file from Central Repository and effective rebuild file, then debug up to the root cause of this unwanted difference:
- rebuilder bug: if the improvement has to happen at [buildspec](BUILDSPEC.md) or [rebuild script](rebuild.sh) level, don't hesitate to open an issue or a PR here,
- upstream project reproducibility issue :beetle:: please contact the upstream project and help them improve the reproducibility for their next release, creating an issue in their issue tracker and adding it to Reproducible Central buildspec as `issue` parameter that will link to it with a :beetle:.

</details>

<details><summary><b>Add Reproducible Builds Badge to a Project With Reproducible Releases</b></summary>

If a project has listed here at least one release with proven reproducibility success, it can add a badge like ![Reproducible Builds](https://img.shields.io/badge/Reproducible_Builds-ok-success?labelColor=1e5b96) pointing to its entries here:

```
[![Reproducible Builds](https://img.shields.io/badge/Reproducible_Builds-ok-success?labelColor=1e5b96)](https://github.com/jvm-repo-rebuild/reproducible-central#...groupId...:...artifactId...)
```

Notice the anchor in the link.

</details>

## Rebuild Results

Nightly Rebuild: [![CircleCI](https://circleci.com/gh/jvm-repo-rebuild/reproducible-central/tree/master.svg?style=shield)](https://circleci.com/gh/jvm-repo-rebuild/reproducible-central/tree/master)

<!-- BEGIN GENERATED INTRO -->
rebuilding **760 releases** of **242 projects**:
- **583** releases were found successfully **fully reproducible** (100% reproducible artifacts :heavy_check_mark:),
- 177 had issues (some unreproducible artifacts :warning:):

<!-- END GENERATED INTRO -->

<!-- BEGIN GENERATED RESULTS TABLE -->
| [Central Repository](https://search.maven.org/) groupId:artifactId(s) | versions | [result](https://reproducible-builds.org/docs/jvm/): reproducible? |
| -------------------------------- | --------- | -------- |
| [biz.aQute.bnd:bnd-plugin-parent](content/content/biz/aQute/bnd/plugins/README.md) | 5 | 5 :heavy_check_mark: / 0 :warning: |
| [ch.qos.logback:logback-parent](content/content/ch/qos/logback/README.md) | 3 | 1 :heavy_check_mark: / 2 :warning: |
| [ch.qos.reload4j:reload4j](content/content/ch/qos/reload4j/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [com.adobe.acs:acs-aem-commons](content/content/com/adobe/acs/aem-commons/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [com.github.adangel.liquibase.ext:liquibase-percona](content/content/com/github/adangel/liquibase/ext/liquibase-percona/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [com.github.ldapchai:ldapchai](content/content/com/github/ldapchai/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [com.github.package-url:packageurl-java](content/content/com/github/package-url/packageurl-java/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [com.github.veithen.maven:java-format-maven-plugin](content/content/com/github/veithen/maven/java-format-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [com.github.veithen:parent](content/content/com/github/veithen/parent/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [com.io7m.jade:com.io7m.jade](content/content/com/io7m/jade/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [com.ongres.stringprep:parent](content/content/com/ongres/stringprep/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [com.scalapenos:stamina_2.11](content/content/com/scalapenos/stamina/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [com.taobao.arthas:arthas-all](content/content/com/taobao/arthas/README.md) | 13 | 0 :heavy_check_mark: / 13 :warning: |
| [fr.vidal.oss:atom-jaxb](content/content/fr/vidal/oss/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [io.dropwizard:dropwizard-project](content/content/io/dropwizard/core/README.md) | 26 | 23 :heavy_check_mark: / 3 :warning: |
| [io.dropwizard.metrics:metrics-parent](content/content/io/dropwizard/metrics/README.md) | 25 | 11 :heavy_check_mark: / 14 :warning: |
| [io.dropwizard.metrics5:metrics-parent](content/content/io/dropwizard/metrics5/README.md) | 6 | 1 :heavy_check_mark: / 5 :warning: |
| [io.fabric8:docker-maven-plugin](content/content/io/fabric8/docker-maven-plugin/README.md) | 8 | 6 :heavy_check_mark: / 2 :warning: |
| [io.fabric8:kubernetes-client-project](content/content/io/fabric8/kubernetes-client/README.md) | 7 | 0 :heavy_check_mark: / 7 :warning: |
| [io.github.albertus82:jface-utils](content/content/io/github/albertus82/jface-utils/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [io.github.albertus82:unexepack](content/content/io/github/albertus82/unexepack/README.md) | 3 | 0 :heavy_check_mark: / 3 :warning: |
| [io.github.derkrischan:jpdftest](content/content/io/github/derkrischan/jpdftest/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [io.liftwizard:liftwizard](content/content/io/liftwizard/README.md) | 22 | 22 :heavy_check_mark: / 0 :warning: |
| [io.micronaut.build:micronaut-maven-plugin](content/content/io/micronaut/build/micronaut-maven-plugin/README.md) | 19 | 19 :heavy_check_mark: / 0 :warning: |
| [io.wcm:io.wcm.caconfig.editor.parent](content/content/io/wcm/caconfig/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [io.wcm:io.wcm.handler.richtext](content/content/io/wcm/handler/README.md) | 7 | 1 :heavy_check_mark: / 6 :warning: |
| [io.wcm.maven.plugins:nodejs-maven-plugin](content/content/io/wcm/maven/plugins/nodejs-maven-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [io.wcm.tooling.commons:io.wcm.tooling.commons.content-package-builder](content/content/io/wcm/tooling/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [io.wcm:io.wcm.wcm.ui.clientlibs](content/content/io/wcm/wcm/README.md) | 8 | 6 :heavy_check_mark: / 2 :warning: |
| [net.nicoulaj.maven.plugins:checksum-maven-plugin](content/content/net/nicoulaj/maven/plugins/checksum-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [net.sourceforge.pmd:pmd](content/content/net/sourceforge/pmd/README.md) | 20 | 19 :heavy_check_mark: / 1 :warning: |
| [nl.hsac:hsac-fitnesse-fixtures](content/content/nl/hsac/hsac-fitnesse-fixtures/README.md) | 24 | 13 :heavy_check_mark: / 11 :warning: |
| [org.apache.accumulo:accumulo](content/content/org/apache/accumulo/README.md) | 3 | 0 :heavy_check_mark: / 3 :warning: |
| [org.apache.activemq:activemq-parent](content/content/org/apache/activemq/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.any23:apache-any23](content/content/org/apache/any23/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache:apache](content/content/org/apache/apache/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| [org.apache.aries.cdi:org.apache.aries.cdi](content/content/org/apache/aries/cdi/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.camel:camel](content/content/org/apache/camel/camel/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.cxf.fediz:fediz](content/content/org/apache/cxf/fediz/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.drill:drill-root](content/content/org/apache/drill/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.dubbo:dubbo](content/content/org/apache/dubbo/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [org.apache.felix:org.apache.felix.feature](content/content/org/apache/felix/features/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.felix:org.apache.felix.http.parent](content/content/org/apache/felix/http/parent/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.felix:maven-bundle-plugin](content/content/org/apache/felix/maven-bundle-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.felix:felix-parent](content/content/org/apache/felix/pom/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.httpcomponents:httpcomponents-parent](content/content/org/apache/httpcomponents/parent/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.jackrabbit:filevault-package-maven-plugin](content/content/org/apache/jackrabbit/filevault-package-maven-plugin/README.md) | 4 | 4 :heavy_check_mark: / 0 :warning: |
| [org.apache.jackrabbit.vault:jackrabbit-filevault](content/content/org/apache/jackrabbit/filevault/README.md) | 7 | 0 :heavy_check_mark: / 7 :warning: |
| [org.apache.jena:jena](content/content/org/apache/jena/jena/README.md) | 8 | 0 :heavy_check_mark: / 8 :warning: |
| [org.apache.jspwiki:jspwiki-builder](content/content/org/apache/jspwiki/README.md) | 5 | 0 :heavy_check_mark: / 5 :warning: |
| [org.apache.karaf:decanter](content/content/org/apache/karaf/decanter/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.karaf:karaf](content/content/org/apache/karaf/karaf/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.logging:logging-parent](content/content/org/apache/logging/parent/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.archetype:maven-archetype](content/content/org/apache/maven/archetype/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.doxia:doxia-sitetools](content/content/org/apache/maven/doxia/doxia-sitetools/README.md) | 5 | 5 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.doxia:doxia](content/content/org/apache/maven/doxia/doxia/README.md) | 5 | 5 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.indexer:maven-indexer](content/content/org/apache/maven/indexer/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.jxr:jxr](content/content/org/apache/maven/jxr/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven:maven](content/content/org/apache/maven/maven/README.md) | 6 | 3 :heavy_check_mark: / 3 :warning: |
| [org.apache.maven:maven-parent](content/content/org/apache/maven/parent/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.maven.plugin-tools:maven-plugin-tools](content/content/org/apache/maven/plugin-tools/maven-plugin-tools/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-antrun-plugin](content/content/org/apache/maven/plugins/maven-antrun-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-artifact-plugin](content/content/org/apache/maven/plugins/maven-artifact-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-assembly-plugin](content/content/org/apache/maven/plugins/maven-assembly-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-checkstyle-plugin](content/content/org/apache/maven/plugins/maven-checkstyle-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-compiler-plugin](content/content/org/apache/maven/plugins/maven-compiler-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-dependency-plugin](content/content/org/apache/maven/plugins/maven-dependency-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-deploy-plugin](content/content/org/apache/maven/plugins/maven-deploy-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-ear-plugin](content/content/org/apache/maven/plugins/maven-ear-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-ejb-plugin](content/content/org/apache/maven/plugins/maven-ejb-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.enforcer:enforcer](content/content/org/apache/maven/plugins/maven-enforcer-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-gpg-plugin](content/content/org/apache/maven/plugins/maven-gpg-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.plugins:maven-invoker-plugin](content/content/org/apache/maven/plugins/maven-invoker-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-jar-plugin](content/content/org/apache/maven/plugins/maven-jar-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-javadoc-plugin](content/content/org/apache/maven/plugins/maven-javadoc-plugin/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| [org.apache.maven.plugins:maven-jlink-plugin](content/content/org/apache/maven/plugins/maven-jlink-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-pdf-plugin](content/content/org/apache/maven/plugins/maven-pdf-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-pmd-plugin](content/content/org/apache/maven/plugins/maven-pmd-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-project-info-reports-plugin](content/content/org/apache/maven/plugins/maven-project-info-reports-plugin/README.md) | 5 | 4 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.plugins:maven-release-plugin](content/content/org/apache/maven/plugins/maven-release-plugin/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-resources-plugin](content/content/org/apache/maven/plugins/maven-resources-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.plugins:maven-scm-publish-plugin](content/content/org/apache/maven/plugins/maven-scm-publish-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-scripting-plugin](content/content/org/apache/maven/plugins/maven-scripting-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-shade-plugin](content/content/org/apache/maven/plugins/maven-shade-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-site-plugin](content/content/org/apache/maven/plugins/maven-site-plugin/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| [org.apache.maven.plugins:maven-source-plugin](content/content/org/apache/maven/plugins/maven-source-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.plugins:maven-war-plugin](content/content/org/apache/maven/plugins/maven-war-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.plugins:maven-wrapper-plugin](content/content/org/apache/maven/plugins/maven-wrapper-plugin/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.reporting:maven-reporting-api](content/content/org/apache/maven/reporting/maven-reporting-api/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.reporting:maven-reporting-exec](content/content/org/apache/maven/reporting/maven-reporting-exec/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.reporting:maven-reporting-impl](content/content/org/apache/maven/reporting/maven-reporting-impl/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.resolver:maven-resolver-ant-tasks](content/content/org/apache/maven/resolver/maven-resolver-ant-tasks/README.md) | 4 | 4 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.resolver:maven-resolver](content/content/org/apache/maven/resolver/maven-resolver/README.md) | 8 | 7 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.scm:maven-scm](content/content/org/apache/maven/scm/README.md) | 4 | 4 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven:maven-archiver](content/content/org/apache/maven/shared/maven-archiver/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-artifact-transfer](content/content/org/apache/maven/shared/maven-artifact-transfer/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.shared:maven-common-artifact-filters](content/content/org/apache/maven/shared/maven-common-artifact-filters/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-dependency-analyzer](content/content/org/apache/maven/shared/maven-dependency-analyzer/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-dependency-tree](content/content/org/apache/maven/shared/maven-dependency-tree/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-filtering](content/content/org/apache/maven/shared/maven-filtering/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.shared:maven-invoker](content/content/org/apache/maven/shared/maven-invoker/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-script-interpreter](content/content/org/apache/maven/shared/maven-script-interpreter/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-shared-resources](content/content/org/apache/maven/shared/maven-shared-resources/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-shared-utils](content/content/org/apache/maven/shared/maven-shared-utils/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.shared:maven-verifier](content/content/org/apache/maven/shared/maven-verifier/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.skins:maven-fluido-skin](content/content/org/apache/maven/skins/fluido/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.surefire:surefire](content/content/org/apache/maven/surefire/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.maven.wagon:wagon](content/content/org/apache/maven/wagon/wagon/README.md) | 6 | 6 :heavy_check_mark: / 0 :warning: |
| [org.apache.maven.wrapper:maven-wrapper-parent](content/content/org/apache/maven/wrapper/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.ftpserver:ftpserver-parent](content/content/org/apache/mina/ftpserver/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.mina:mina-parent](content/content/org/apache/mina/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.plc4x.plugins:plc4x-code-generaton](content/content/org/apache/plc4x/plc4x-code-generation/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.plc4x:plc4x-parent](content/content/org/apache/plc4x/plc4x/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.royale.compiler:compiler](content/content/org/apache/royale/compiler/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.shiro:shiro-root](content/content/org/apache/shiro/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:htl-maven-plugin](content/content/org/apache/sling/htl-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:jspc-maven-plugin](content/content/org/apache/sling/jspc-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.adapter](content/content/org/apache/sling/org.apache.sling.adapter/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.api](content/content/org/apache/sling/org.apache.sling.api/README.md) | 4 | 4 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.auth.core](content/content/org/apache/sling/org.apache.sling.auth.core/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.bundleresource.impl](content/content/org/apache/sling/org.apache.sling.bundleresource.impl/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.caconfig.api](content/content/org/apache/sling/org.apache.sling.caconfig.api/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.caconfig.impl](content/content/org/apache/sling/org.apache.sling.caconfig.impl/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.caconfig.spi](content/content/org/apache/sling/org.apache.sling.caconfig.spi/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.commons.content.analyzing](content/content/org/apache/sling/org.apache.sling.commons.content.analyzing/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.commons.content.processing](content/content/org/apache/sling/org.apache.sling.commons.content.processing/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.commons.crypto](content/content/org/apache/sling/org.apache.sling.commons.crypto/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.commons.johnzon](content/content/org/apache/sling/org.apache.sling.commons.johnzon/README.md) | 5 | 3 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.commons.log](content/content/org/apache/sling/org.apache.sling.commons.log/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.commons.messaging.mail](content/content/org/apache/sling/org.apache.sling.commons.messaging.mail/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.commons.messaging](content/content/org/apache/sling/org.apache.sling.commons.messaging/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.commons.metrics](content/content/org/apache/sling/org.apache.sling.commons.metrics/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.distribution.journal.kafka](content/content/org/apache/sling/org.apache.sling.distribution.journal.kafka/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.distribution.journal](content/content/org/apache/sling/org.apache.sling.distribution.journal/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.engine](content/content/org/apache/sling/org.apache.sling.engine/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.event](content/content/org/apache/sling/org.apache.sling.event/README.md) | 5 | 0 :heavy_check_mark: / 5 :warning: |
| [org.apache.sling:org.apache.sling.feature.analyser](content/content/org/apache/sling/org.apache.sling.feature.analyser/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.feature.cpconverter](content/content/org/apache/sling/org.apache.sling.feature.cpconverter/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.feature.extension.apiregions](content/content/org/apache/sling/org.apache.sling.feature.extension.apiregions/README.md) | 5 | 5 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.feature.extension.unpack](content/content/org/apache/sling/org.apache.sling.feature.extension.unpack/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.feature.launcher](content/content/org/apache/sling/org.apache.sling.feature.launcher/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.feature](content/content/org/apache/sling/org.apache.sling.feature/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.fsresource](content/content/org/apache/sling/org.apache.sling.fsresource/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.i18n](content/content/org/apache/sling/org.apache.sling.i18n/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.installer.console](content/content/org/apache/sling/org.apache.sling.installer.console/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.installer.core](content/content/org/apache/sling/org.apache.sling.installer.core/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [org.apache.sling:org.apache.sling.installer.factory.configuration](content/content/org/apache/sling/org.apache.sling.installer.factory.configuration/README.md) | 5 | 1 :heavy_check_mark: / 4 :warning: |
| [org.apache.sling:org.apache.sling.installer.factory.packages](content/content/org/apache/sling/org.apache.sling.installer.factory.packages/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.installer.provider.file](content/content/org/apache/sling/org.apache.sling.installer.provider.file/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.installer.provider.jcr](content/content/org/apache/sling/org.apache.sling.installer.provider.jcr/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.javax.activation](content/content/org/apache/sling/org.apache.sling.javax.activation/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.jcr.contentloader](content/content/org/apache/sling/org.apache.sling.jcr.contentloader/README.md) | 3 | 0 :heavy_check_mark: / 3 :warning: |
| [org.apache.sling:org.apache.sling.jcr.jackrabbit.accessmanager](content/content/org/apache/sling/org.apache.sling.jcr.jackrabbit.accessmanager/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.jcr.jackrabbit.usermanager](content/content/org/apache/sling/org.apache.sling.jcr.jackrabbit.usermanager/README.md) | 3 | 0 :heavy_check_mark: / 3 :warning: |
| [org.apache.sling:org.apache.sling.jcr.maintenance](content/content/org/apache/sling/org.apache.sling.jcr.maintenance/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.jcr.packageinit](content/content/org/apache/sling/org.apache.sling.jcr.packageinit/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.jcr.resource](content/content/org/apache/sling/org.apache.sling.jcr.resource/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.jcr.resourcesecurity](content/content/org/apache/sling/org.apache.sling.jcr.resourcesecurity/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.launchpad.test-services](content/content/org/apache/sling/org.apache.sling.launchpad.test-services/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.models.api](content/content/org/apache/sling/org.apache.sling.models.api/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.models.caconfig](content/content/org/apache/sling/org.apache.sling.models.caconfig/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.models.impl](content/content/org/apache/sling/org.apache.sling.models.impl/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.models.jacksonexporter](content/content/org/apache/sling/org.apache.sling.models.jacksonexporter/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.models.validation-impl](content/content/org/apache/sling/org.apache.sling.models.validation-impl/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.pipes](content/content/org/apache/sling/org.apache.sling.pipes/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.repoinit.parser](content/content/org/apache/sling/org.apache.sling.repoinit.parser/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.resourceaccesssecurity](content/content/org/apache/sling/org.apache.sling.resourceaccesssecurity/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.resourcemerger](content/content/org/apache/sling/org.apache.sling.resourcemerger/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.resourceresolver](content/content/org/apache/sling/org.apache.sling.resourceresolver/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.rewriter](content/content/org/apache/sling/org.apache.sling.rewriter/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.scripting.core](content/content/org/apache/sling/org.apache.sling.scripting.core/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.scripting.sightly.repl](content/content/org/apache/sling/org.apache.sling.scripting.sightly.repl/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.scripting.sightly.testing-content](content/content/org/apache/sling/org.apache.sling.scripting.sightly.testing-content/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.scripting.sightly](content/content/org/apache/sling/org.apache.sling.scripting.sightly/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.scripting.spi](content/content/org/apache/sling/org.apache.sling.scripting.spi/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.security](content/content/org/apache/sling/org.apache.sling.security/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.servlets.annotations](content/content/org/apache/sling/org.apache.sling.servlets.annotations/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.servlets.post](content/content/org/apache/sling/org.apache.sling.servlets.post/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.sling:org.apache.sling.servlets.resolver](content/content/org/apache/sling/org.apache.sling.servlets.resolver/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [org.apache.sling:org.apache.sling.settings](content/content/org/apache/sling/org.apache.sling.settings/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.sitemap](content/content/org/apache/sling/org.apache.sling.sitemap/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.starter.content](content/content/org/apache/sling/org.apache.sling.starter.content/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.starter](content/content/org/apache/sling/org.apache.sling.starter/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.tenant](content/content/org/apache/sling/org.apache.sling.tenant/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.testing.caconfig-mock-plugin](content/content/org/apache/sling/org.apache.sling.testing.caconfig-mock-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.testing.clients](content/content/org/apache/sling/org.apache.sling.testing.clients/README.md) | 4 | 4 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.testing.jcr-mock](content/content/org/apache/sling/org.apache.sling.testing.jcr-mock/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:org.apache.sling.testing.resourceresolver-mock](content/content/org/apache/sling/org.apache.sling.testing.resourceresolver-mock/README.md) | 4 | 3 :heavy_check_mark: / 1 :warning: |
| [org.apache.sling:org.apache.sling.testing.sling-mock-oak](content/content/org/apache/sling/org.apache.sling.testing.sling-mock-oak/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.apache.sling:scriptingbundle-maven-plugin](content/content/org/apache/sling/scriptingbundle-maven-plugin/README.md) | 3 | 0 :heavy_check_mark: / 3 :warning: |
| [org.apache.sling:slingfeature-maven-plugin](content/content/org/apache/sling/slingfeature-maven-plugin/README.md) | 5 | 2 :heavy_check_mark: / 3 :warning: |
| [org.apache.sshd:sshd](content/content/org/apache/sshd/README.md) | 2 | 0 :heavy_check_mark: / 2 :warning: |
| [org.apache.struts:struts2-parent](content/content/org/apache/struts/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.tika:tika](content/content/org/apache/tika/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| [org.apache.wayang:wayang](content/content/org/apache/wayang/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.apache.wss4j:wss4j](content/content/org/apache/wss4j/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.modello:modello](content/content/org/codehaus/modello/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:animal-sniffer-parent](content/content/org/codehaus/mojo/animal-sniffer/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:aspectj-maven-plugin](content/content/org/codehaus/mojo/aspectj-maven-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.mojo:extra-enforcer-rules](content/content/org/codehaus/mojo/extra-enforcer-rules/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:flatten-maven-plugin](content/content/org/codehaus/mojo/flatten-maven-plugin/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.mojo:mojo-parent](content/content/org/codehaus/mojo/mojo-parent/README.md) | 5 | 5 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:properties-maven-plugin](content/content/org/codehaus/mojo/properties-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:taglist-maven-plugin](content/content/org/codehaus/mojo/taglist-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:versions-maven-plugin](content/content/org/codehaus/mojo/versions-maven-plugin/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.mojo:wagon-maven-plugin](content/content/org/codehaus/mojo/wagon-maven-plugin/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.plexus:plexus-archiver](content/content/org/codehaus/plexus/plexus-archiver/README.md) | 6 | 5 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.plexus:plexus-cipher](content/content/org/codehaus/plexus/plexus-cipher/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.plexus:plexus-compiler](content/content/org/codehaus/plexus/plexus-compiler/README.md) | 7 | 5 :heavy_check_mark: / 2 :warning: |
| [org.codehaus.plexus:plexus-components](content/content/org/codehaus/plexus/plexus-components/README.md) | 4 | 3 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.plexus:plexus-interactivity](content/content/org/codehaus/plexus/plexus-interactivity/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.plexus:plexus-languages](content/content/org/codehaus/plexus/plexus-languages/README.md) | 5 | 0 :heavy_check_mark: / 5 :warning: |
| [org.codehaus.plexus:plexus](content/content/org/codehaus/plexus/plexus-pom/README.md) | 6 | 5 :heavy_check_mark: / 1 :warning: |
| [org.codehaus.plexus:plexus-utils](content/content/org/codehaus/plexus/plexus-utils/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.codehaus.plexus:plexus-velocity](content/content/org/codehaus/plexus/plexus-velocity/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.complate:complate-core](content/content/org/complate/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.cyclonedx:cyclonedx-core-java](content/content/org/cyclonedx/cyclonedx-core-java/README.md) | 20 | 20 :heavy_check_mark: / 0 :warning: |
| [org.cyclonedx:cyclonedx-maven-plugin](content/content/org/cyclonedx/cyclonedx-maven-plugin/README.md) | 8 | 8 :heavy_check_mark: / 0 :warning: |
| [org.eclipse.jkube:jkube](content/content/org/eclipse/jkube/README.md) | 9 | 9 :heavy_check_mark: / 0 :warning: |
| [org.eclipse.transformer:org.eclipse.transformer.parent](content/content/org/eclipse/transformer/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.fusesource.jansi:jansi](content/content/org/fusesource/jansi/jansi/README.md) | 8 | 5 :heavy_check_mark: / 3 :warning: |
| [org.jline:jline-parent](content/content/org/jline/jline/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.jrivard.xmlchai:xmlchai](content/content/org/jrivard/xmlchai/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.liquibase.ext:liquibase-percona](content/content/org/liquibase/ext/liquibase-percona/README.md) | 16 | 15 :heavy_check_mark: / 1 :warning: |
| [org.mybatis.dynamic-sql:mybatis-dynamic-sql](content/content/org/mybatis/dynamic-sql/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.mybatis:mybatis-guice](content/content/org/mybatis/guice/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.mybatis:mybatis-parent](content/content/org/mybatis/parent/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.nlpub:watset](content/content/org/nlpub/watset/README.md) | 12 | 11 :heavy_check_mark: / 1 :warning: |
| [org.openapitools.openapidiff:openapi-diff-parent](content/content/org/openapitools/openapidiff/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.osgi:org.osgi.test.parent](content/content/org/osgi/test/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| [org.owasp.antisamy:antisamy](content/content/org/owasp/antisamy/README.md) | 6 | 6 :heavy_check_mark: / 0 :warning: |
| [org.quickperf:quick-perf](content/content/org/quickperf/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [org.simplify4u:pgp-keys-map](content/content/org/simplify4u/pgp-keys-map/README.md) | 12 | 12 :heavy_check_mark: / 0 :warning: |
| [org.simplify4u.plugins:pgpverify-maven-plugin](content/content/org/simplify4u/plugins/pgpverify-maven-plugin/README.md) | 7 | 7 :heavy_check_mark: / 0 :warning: |
| [org.simplify4u.plugins:sign-maven-plugin](content/content/org/simplify4u/plugins/sign-maven-plugin/README.md) | 7 | 5 :heavy_check_mark: / 2 :warning: |
| [org.simplify4u:slf4j-mock](content/content/org/simplify4u/slf4j-mock/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.slf4j:slf4j-parent](content/content/org/slf4j/README.md) | 1 | 0 :heavy_check_mark: / 1 :warning: |
| [org.sonatype.nexus.archetypes:nexus-format-archetype](content/content/org/sonatype/nexus/archetypes/nexus-format-archetype/README.md) | 1 | 1 :heavy_check_mark: / 0 :warning: |
| [org.tomitribe.transformer:org.eclipse.transformer.parent](content/content/org/tomitribe/transformer/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.webjars:flexmonster](content/content/org/webjars/flexmonster/README.md) | 2 | 2 :heavy_check_mark: / 0 :warning: |
| [org.webjars:swagger-ui](content/content/org/webjars/swagger-ui/README.md) | 3 | 3 :heavy_check_mark: / 0 :warning: |
| [world.convex:convex](content/content/world/convex/README.md) | 4 | 0 :heavy_check_mark: / 4 :warning: |
| **Count: 242** | **760** | **583** :heavy_check_mark: **177** :warning: |
<!-- END GENERATED RESULTS TABLE -->

## Understanding What Is Behind

see [history](HISTORY.md)

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#
