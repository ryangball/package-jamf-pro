# Create Jamf Pro Patch PKGs
Easily package Jamf Pro applications individually to be used with Jamf Pro's Patch Management.

## Explanation
Patch Management within Jamf Pro requires individual applications when patching the Jamf Pro tools (Jamf Admin, Jamf Remote, Jamf Imaging, Composer, Recon). Creating these indivudual packages can be tedious and sometimes they require special permissions.

This script will take whatever version of Jamf Pro tools installed on a Mac and package them up individually and reveal the packages in Finder.
<p align="center">
<img alt="Preview of built PKGs" src="images/packaged_preview.png">
</p>

## Features
- Creates individual packages for each Jamf Pro component app (Jamf Admin.app, Jamf Imaging.app, Jamf Remote.app, Composer.app, and Recon.app)
- When one of the resulting packages is installed, the corresponding Casper Suite app will be removed
- Disable the automatic relocation of the Jamf apps to the `/Applications/Casper\ Suite` directory
- Once all Casper Suite apps are removed the `/Applications/Casper\ Suite` directory is removed
- Fix permissions issues get when packaging with Composer.app (icons for Jamf apps don't display properly)
- Allows for specifying whether or not non-admins can execute the applications

## Usage
```bash
git clone https://github.com/ryangball/create-jamf-pro-patch-pkgs.git
cd create-jamf-pro-patch-pkgs
sudo ./create_jamf_pro_patch_pkgs.sh
```

## Restrict Non-Admins from Executing
If you want only admins to read/execute the resulting installed application you can change `allowNonAdminToReadOrExecute="true"` to `allowNonAdminToReadOrExecute="false"`.
