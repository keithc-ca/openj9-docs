<!--
* Copyright (c) 2017, 2025 IBM Corp. and others
*
* This program and the accompanying materials are made
* available under the terms of the Eclipse Public License 2.0
* which accompanies this distribution and is available at
* https://www.eclipse.org/legal/epl-2.0/ or the Apache
* License, Version 2.0 which accompanies this distribution and
* is available at https://www.apache.org/licenses/LICENSE-2.0.
*
* This Source Code may also be made available under the
* following Secondary Licenses when the conditions for such
* availability set forth in the Eclipse Public License, v. 2.0
* are satisfied: GNU General Public License, version 2 with
* the GNU Classpath Exception [1] and GNU General Public
* License, version 2 with the OpenJDK Assembly Exception [2].
*
* [1] https://www.gnu.org/software/classpath/license.html
* [2] https://openjdk.org/legal/assembly-exception.html
*
* SPDX-License-Identifier: EPL-2.0 OR Apache-2.0 OR GPL-2.0-only WITH Classpath-exception-2.0 OR GPL-2.0-only WITH OpenJDK-assembly-exception-1.0
-->


# What's new in version 0.19.0

 The following new features and notable changes since version 0.18.0 are included in this release:

- [New binaries and changes to supported environments](#binaries-and-supported-environments)
- [Option to print code cache usage to `stderr` at VM shutdown](#option-to-print-code-cache-usage-to-stderr-at-vm-shutdown)
- [![Start of content that applies to Java 8](cr/java8.png) `StringBuffer` and `StringBuilder` above 1 G grow to the maximum size](#stringbuffer-and-stringbuilder-above-1-g-grow-to-the-maximum-size)
- [![Start of content that applies to Java 14+](cr/java14plus.png) jpackage packaging tool platform support](#jpackage-packaging-tool-platform-support)
- [![Start of content that applies to Java 14+](cr/java14plus.png) Extended messages for `NullPointerException` not yet implemented](#extended-messages-for-nullpointerexception-not-yet-implemented)
- [Compiler changes for Linux](#compiler-changes-for-linux)
- ![Start of content that applies only to Java 14plus](cr/java14plus.png) [New JDK 14 features](#new-jdk-14-features)

## Features and changes

### Binaries and supported environments

Eclipse OpenJ9&trade; release 0.19.0 supports OpenJDK 14, which is available from the AdoptOpenJDK community at the following link:

- [OpenJDK version 14](https://adoptopenjdk.net/archive.html?variant=openjdk14&jvmVariant=openj9)

OpenJDK 14 with Eclipse OpenJ9 is not a long term support (LTS) release.

The latest builds of OpenJDK with OpenJ9 for Java 8 and 11 at the AdoptOpenJDK community are for Eclipse OpenJ9 release 0.18.0. Features mentioned in these release notes are not available in these builds. Although it might be possible to build an OpenJDK 8 or OpenJDK 11 with OpenJ9 0.19.0, testing at the project is not complete and therefore support for any of these features is not available.

To learn more about support for OpenJ9 releases, including OpenJDK levels and platform support, see [Supported environments](openj9_support.md).

### Option to print code cache usage to `stderr` at VM shutdown

A new command line option [-XX:+PrintCodeCache](xxprintcodecache.md) allows you to print the code cache memory usage to `stderr` when the VM shuts down.

### ![Start of content that applies to Java 8](cr/java8.png) `StringBuffer` and `StringBuilder` above 1 G grow to the maximum size

A 1 G `char[]` or larger `StringBuffer` and `StringBuilder` now immediately grows to the maximum possible size for <i>all</i> current versions of Java, including Java 8. For Java 8 only, you can revert to the previous behavior of growing only as much as necessary to accommodate the `String` being added, by using the option, [`-Djava.lang.stringBuffer.growAggressively=false`](djavalangstringbuffergrowaggressively.md).

### ![Start of content that applies to Java 14+](cr/java14plus.png) jpackage packaging tool platform support

The `jpackage` utility is described in JEP 343 as a tool that "packages a Java application into a platform-specific package that includes all of the necessary dependencies." Full details of the tool are available at [JEP 343: Packaging Tool](https://openjdk.org/jeps/343). Be aware that `jpackage` is supported on only the following OpenJ9 platforms: Linux&reg;, macOS&reg;, and Windows&trade;. It is _not_ supported on AIX&reg; or z/OS&reg; platforms.

### ![Start of content that applies to Java 14+](cr/java14plus.png) Extended messages for `NullPointerException` not yet implemented

[JEP 358: Helpful NullPointerExceptions](https://openjdk.org/jeps/358) provides extended messages when a `NullPointerException` is generated by the Java 14 VM and you have enabled the feature. However, be aware that this is _not_ implemented in OpenJ9 at this time.


### Compiler changes for Linux

Linux x86 64-bit, Linux on POWER&reg; LE 64-bit, and Linux on IBM Z&reg; 64-bit have all moved to the gcc 7.5 compiler. See [Supported environments](openj9_support.md).

### ![Start of content that applies to Java 14 plus](cr/java14plus.png) New JDK 14 features

The following features are supported by OpenJ9:

- [JEP 343](https://openjdk.org/jeps/343): Packaging Tool (Incubator)<br>:fontawesome-solid-triangle-exclamation:{: .warn aria-hidden="true"} **Restrictions:** `jpackage` is supported on only the following OpenJ9 platforms: Linux&reg;, macOS&reg;, and Windows&trade;. It is _not_ supported on AIX&reg; or z/OS&reg; platforms.
- [JEP 352](https://openjdk.org/jeps/352): Non-Volatile Mapped Byte Buffers
- [JEP 358](https://openjdk.org/jeps/358): Helpful NullPointerExceptions
- [JEP 359](https://openjdk.org/jeps/359): Records (Preview)

The following features are implemented in OpenJDK and available in any builds of OpenJDK 14 with OpenJ9:

- [JEP 305](https://openjdk.org/jeps/305): Pattern Matching for instanceof (Preview) 
- [JEP 361](https://openjdk.org/jeps/361): Switch Expressions (Standard)
- [JEP 367](https://openjdk.org/jeps/367): Remove the Pack200 Tools and API
- [JEP 368](https://openjdk.org/jeps/368): Text Blocks (Second Preview)

You can find the full list of features for JDK 14 at the [OpenJDK project](https://openjdk.org/projects/jdk/14/). Any remaining features that are listed do not apply to OpenJ9.

## Full release information

To see a complete list of changes between Eclipse OpenJ9 version 0.18.0 and version 0.19.0 releases, see the [Release notes](https://github.com/eclipse-openj9/openj9/blob/master/doc/release-notes/0.19/0.19.md).

<!-- ==== END OF TOPIC ==== version0.19.md ==== -->
