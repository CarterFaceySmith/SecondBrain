Determines the rights and limitations on how you can use, modify, and distribute given [[C++ Libraries]]. There are various types of licenses applied to open-source libraries. 

Below is a brief overview of three common licenses:

## MIT License

The MIT License is a permissive license that allows users to do whatever they want with the software code. They only need to include the original copyright, license notice, and a disclaimer of warranty in their copies.

Example: Including the MIT License into your project can be done by simply adding the license file and a notice at the top of your source code files like:

```cpp
/* Copyright (C) [year] [author]
 * SPDX-License-Identifier:    MIT
 */
```

## GNU General Public License (GPL)

The GPL is a copyleft license that grants users the rights to use, study, share, and modify the software code. However, any changes made to the code or any software that uses GPL licensed code must also be distributed under the GPL license.

Example: To include a GPL license in your project, include a `COPYING` file with the full text of the license and place a notice in your source code files like:

```cpp
/* Copyright (C) [year] [author]
 * SPDX-License-Identifier:    GPL-3.0-or-later
 */
```

## Apache License 2.0

The Apache License is a permissive license similar to the MIT license and allows users to do virtually anything with the software code. The primary difference is that it requires that any changes to the code are documented, and it provides specific terms for patent protection.

Example: To include the Apache License in your project, add a `LICENSE` file with the full text of the license. Add a notice to your source code files like:

```cpp
/* Copyright (C) [year] [author]
 * SPDX-License-Identifier:    Apache-2.0
 */
```


See also:
- [[Code Licensing]]