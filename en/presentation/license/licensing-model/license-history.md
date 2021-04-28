---
title: License history
description: 'Before and after the licence change: October 27th, 2017'
---

# License history

## Old License

Up to commit [3247e3f2](https://gitlab.com/recalbox/recalbox/commit/3247e3f2d3dc60a926673d54b3dff3604e640763), Recalbox used to be a derivative work of [Buildroot](https://buildroot.org/).

> This directory contains the source code that compiles recalboxOS for different cards.
>
> Recalbox is an opensource project. We hope you will contribute and help us improve this OS.
>
> But if you are working on a fork, out of respect for our work, we ask that you do not integrate our work in progress located on branches other than that of the main branch.
>
> Please wait for a merge on the main branch.
>
> Please use  **Issues**  in the corresponding projects to report a bug or request a feature.

So inherited from Buildroot and was covered by its license: [GNU General Public License v2.0 or later](https://spdx.org/licenses/GPL-2.0-or-later.html) \(SPDX identifier : `GPL-2.0-or-later`\).



### As required by the license, Recalbox was

* Distributing the full source code of the derivative work, including the full toolchain :

> Complete source code means all the source code for all modules it contains, plus any associated interface definition files, plus the scripts used to control compilation and installation of the executable.
>
> _source:_ [_GNU General Public License v2.0 or later_](https://spdx.org/licenses/GPL-2.0-or-later.html)​

* Distributing [a copy of the license itself](https://gitlab.com/recalbox/recalbox/blob/3247e3f2d3dc60a926673d54b3dff3604e640763/COPYING) with the source code.



### Also, as [suggested by the Buildroot developers](https://buildroot.org/downloads/manual/manual.html#legal-info-buildroot), Recalbox was also:

* Distributing the full source code of Buildroot itself.

## Current license <a id="current-license"></a>

Starting from commit [ed05dff8](https://gitlab.com/recalbox/recalbox/commit/ed05dff8) \(which is the immediate child of commit [3247e3f2](https://gitlab.com/recalbox/recalbox/commit/3247e3f2d3dc60a926673d54b3dff3604e640763) mentioned above\), we introduced a new [custom license](https://gitlab.com/recalbox/recalbox/blob/master/LICENSE.md), which states :

> Redistribution and use of the RECALBOX code or any derivative works are permitted provided that the following conditions are met :
>
> * Redistributions may not be sold without authorization, nor may they be used in a commercial product or activity.
> * Redistributions that are modified from the original source must include the complete source code, including the source code for all components used by a binary built from the modified sources.
> * Redistributions must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
>
> THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES \(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION\) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT \(INCLUDING NEGLIGENCE OR OTHERWISE\) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

**Information :** While not a legal requirement framed by the license, we kindly ask anyone who would like to create derivative works, modified versions or "forks" of Recalbox not to use any code that did not hit the `master`branch yet :

> If you are working on a fork, by respect for our work, we ask you not to integrate our work in progress located on branches other than master. Thank you for waiting for a merge on master branch. _source :_ [_our README file_](https://gitlab.com/recalbox/recalbox/blob/master/README.md)_​_

