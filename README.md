# Form Field Advanced Display Add-On Package

## Description

<u>This solution depends on package "[Property Advanced Validation](???)" (PAV)</u>

Purpose:

* Field on forms of an ItemType may need to be disabled or enabled for defined "Stages” only.
* Field on forms of an ItemType may need to be shown or hidden for defined "Stages” only.

* 2 generic "Client Methods" (ffr_FormField_ApplyRenderRules, ffr_FormField_ApplyRenderRules_p) are provided to read the rules of the ItemType specific configurations to execute the rendering rules during "onLoad” of the Form.
* Form Field Rendering rules must be set to status "Active" (life cycle) to take effect.

Features used from PEV:

* "Stages" are defined as one or more possible "Life Cycle States" of an item.

Similar to and improved functionality from community project "[Life Cycle Based Props and Fields](<https://github.com/ArasLabs/lc-based-props-and-fields>)"


## History

| Version    | Comments                                                     |
| ---------- | ------------------------------------------------------------ |
| [v1.0.0]() | Initial version. (replaces community project "[Life Cycle Based Props and Fields](<https://github.com/ArasLabs/lc-based-props-and-fields>)"); |

### Supported Aras Versions

| Project    | Aras      |
| ---------- | --------- |
| [v1.0.0]() | 11.0 SP15 |

## Installation

### Installation Components

* Aras Import Package Tool
* Downloaded Package

- No code tree changes


### Pre-requisites

* Aras Innovator Install (Supported Service Packs listed above)

### Dependencies

* Property Advanced Validation (PAV) package

### Aras Install Steps

##### Important: **Always back up your code tree and database before applying an import package or code tree patch!**

- [ ] Use the package import utility in your CD image to import the packages in this module. 

- [ ] Log on as **root** and use options <u>Merge</u> and <u>Thorough</u> for all steps

  - [ ] Import the `imports.mf` file from the Imports folder.

## Usage

<u>Prerequisite: Set up Stage definitions according to the PAV Usage.</u>

1. Log in as <u>admin</u> and expand to **Administration > Configuration**
2. Open **Form Field Rendering Rules**. Create a <u>New Item</u>.
3. Select the existing ItemType you wish to apply the rules to.
4. Select the stage definition created previously.
5. Select an Owner.
6. Add the fields to be controlled.
   1. Select the form to be controlled.
   2. Select the field(s)
   3. Set the stages to validate at (multi-select) or the All Stages flag
   4. For each field select the appropriate combination of the below:
      1. Set <u>visible</u> or <u>hidden</u> and if the rule is applied to an **Identity**
      2. Set <u>enabled</u> or <u>disabled</u> and if the rule is applied to an **Identity**
7. **Save** and **Lock** the record.
8. **Promote** the record to <u>Active</u>. (**If you do not do this, the rules will not be in force!**)
9. For the **ItemType(s)** selected above, go to any **Form(s)** used and set <u>Form Events</u> for the following:
   1. ffr_FormField_ApplyRenderRules_p – OnFormPopulated
   2. ffr_FormField_ApplyRenderRules – OnLoad
10. Save/Unlock/Close the **Form(s)**.
11. Test Validation.
    1. Checks will run when a form is loaded.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Original Aras community project written by Rolf Laudenbach (rlaudenbach@aras.com) at Aras Corp.

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
