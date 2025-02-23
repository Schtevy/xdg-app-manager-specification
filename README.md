# XDG App Manager Specification

## Abstract
The XDG App Manager is a user-space application management system designed to install, update, and uninstall applications in compliance with the [XDG Base Directory Specification](https://specifications.freedesktop.org/basedir-spec/latest/). Unlike traditional package managers, which manage system-wide dependencies, libraries, and runtimes, the XDG App Manager focuses solely on user-space applications, ensuring a lightweight, dependency-free installation process.

## Design Principles
- XDG Compliance: Applications are installed into $HOME/.local/ subdirectories.
- No Global Dependencies: Applications must be self-contained within the user's home directory.
- Simple Installation & Uninstallation: Applications are extracted and managed through convention-based file structures.
- Versioning Support: Multiple versions of an application can coexist, with a symlink determining the active version.
- Minimalism: No system-wide registries or databases; everything is file-based.
- Security First: Applications must be signed using Sigstore (Cosign), allowing verification before installation.

## Scope
This specification defines:
- Application packaging format: How an application should be structured for distribution.
- Installation process: How applications are installed in user-space directories following XDG conventions.
- Update mechanism: How new versions of applications replace old ones.
- Uninstallation process: How applications and their associated files are cleanly removed.
- Symlink management: How multiple versions are handled and how the active version is determined.
- Core functions: API and CLI specifications for application management.
- Security & Verification: How application authenticity is verified using Sigstore.

