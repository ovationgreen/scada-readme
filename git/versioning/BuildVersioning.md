# Versioning of Ovation Green SCADA
Actual Ovation Green SCADA version is defined in file **PC** repository > **bin** > **VersionInfo.ini**

Product version is configured in section *[FileVersion]* by the following properties:
- **Major** - major version, the first number: **6**.0.2
- **Minor** - minor version, the middle number: 6.**0**.2
- **Release** - release version, the last number: 6.0.**2**

The installation file contains also build number which is added automatically. It can be found in properties of installation file: 6.0.2.**3254**

## Types of builds for Ovation Green SCADA
Type of each build is defined in file **PC** repository > **bin** > **VersionInfo.ini**

*Build type* is defined by property **Release** located in section *[ProductVersion]*:
- **0**: Internal version. This is version which is built before branch is ready for validation. Final product version contains version with build number at the end. For example: **6.0.3.3254**, **OvationGreenSCADA-Setup_6.0.3.3254.exe**
- **3**: Prelim version. This is version which is provided for validation. Final product version contains version with ending *Prelim* at the end. For example: **6.0.3 Prelim**, **OvationGreenSCADA-Setup_6.0.3_Prelim.exe**
- **4**: Release version. This is validated version which is officially delivered to customers. Final product version contains version only. For example: **6.0.3**, **OvationGreenSCADA-Setup_6.0.3.exe**
- **6**: Hotfix. This is hotfix to previously released version. Final product version contains version with ending words *Hotfix 2*. For example: **6.0.3 Hotfix3**, **OvationGreenSCADA-Setup_6.0.3_Hotfix3.exe**. In case of Hotfix build type the number of hotfix is specified by property **Build**. For other build types this property is ignored.

> [!IMPORTANT]
> **Internal version** cannot be provided to customers.

> [!NOTE]
> For each branch there are built automatically the following binaries:
> - **OvationGreenSCADA-Setup_6.0.3.exe** - full SCADA installation package.
> - **OvationGreenSCADA-Patch_6.0.3.exe** - SCADA update/patch package. This one could be installed **ONLY** over previous full installation package.
> - **OvationGreenSCADA-DeskPatch_6.0.3.exe** - SCADA update/patch package containing Desk with all dependencies. This one could be installed **ONLY** over previous full installation package.

On customer side there could be installed only installation packages from SharePoint: 
- [Ovation Green SCADA](https://emerson.sharepoint.com/:f:/r/sites/OvationGreenSCADA/Ovation%20Green%20SCADA%20binaries/Ovation%20Green%20SCADA?csf=1&web=1&e=O8LvWY)


> [!IMPORTANT]
> Oficially procedure of installation looks like following:
> - Install last release package: **OvationGreenSCADA-Setup_6.0.0**
> - Install last **Release Update** (**OvationGreenSCADA-Setup_6.0.2**) or **Hotfix** (**OvationGreenSCADA-Setup_6.0.2_Hotfix2**) over previous release package

