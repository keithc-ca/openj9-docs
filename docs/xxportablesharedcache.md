<!--
* Copyright (c) 2020, 2020 IBM Corp. and others
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
* [2] http://openjdk.java.net/legal/assembly-exception.html
*
* SPDX-License-Identifier: EPL-2.0 OR Apache-2.0 OR GPL-2.0 WITH
* Classpath-exception-2.0 OR LicenseRef-GPL-2.0 WITH Assembly-exception
-->

# -XX:\[+|-\]PortableSharedCache

This option enables AOT compiled code to be generated based on a chosen set of processor features (features present in the Intel&reg; Sandy Bridge microarchitecture) that maximizes its portability across machines. It is currently supported only on x86. The feature is turned on by default in Docker containers but can be disabled with `-XX:-PortableSharedCache`. To enable the portable shared cache feature outside Docker containers, `-XX:+PortableSharedCache` needs to be specified for the initial Java Virtual Machine instance (when the creation of the Shared Class Cache happens) as well as for every subsequent instance that makes use of the same Shared Class Cache.

This option is especially useful for applications deployed on the cloud in the form of Docker containers, as it allows the Shared Class Cache to be portable across processors with different microarchitectures and across VMs with different heap sizes.

## Syntax

        -XX:[+|-]PortableSharedCache

| Setting                            | Effect  | Default                                                                            |
|------------------------------------|---------|:----------------------------------------------------------------------------------:|
| `-XX:+PortableSharedCache`         | Enable  |                                                                                    |
| `-XX:-PortableSharedCache`         | Disable | <i class="fa fa-check" aria-hidden="true"></i><span class="sr-only">yes</span>     |

<!-- ==== END OF TOPIC ==== xxportablesharedcache.md ==== -->