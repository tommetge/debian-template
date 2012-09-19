Debian Packaging Template
=========================

There are a million of these scattered around the net. There's nothing
special about this one. Still, feel free to put it to good use. Keep
in mind: this is designed for debhelper >= 8.

Usage
=====

Clone this repo somewhere on your machine and copy the `debian` directory
into the root of your project. Don't submodule it - you'll need a unique
debian directory for each of your projects.

Once you have a copy, you need to edit the following files:

    debian/changelog
    debian/control
    debian/rules

In most cases, you won't need to do much more than change the project name
in each of these files, especially if you're using Python's DistUtils to
manage the actual installation process.

Project Naming
--------------

Naming is important - and it must be consistent across all of the
packaging files in the `debian` folder. You will see "project-name" used
in both `debian/control` and `debian/changelog`; you will need to change
it in both locations, wherever it is used. There is some in-line
documentation to help you.

Services
--------

If your project provides a service, an init script template is available
as `debian/project.init`. If you rename it, make sure that you change the
references in `debian/rules`.

Post-install Configuration
--------------------------

If you need to do any kind of post-install configuration, use the
`debian/project.postinst` file. You will need to rename this to match the
name of the project, as defined in `debian/control`.