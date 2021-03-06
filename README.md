# Mocha

This is a fork of the excelent jasmine-sublime snippets and syntax package (https://github.com/NicoSantangelo/sublime-jasmine) with some (if not all) the snippets 

## Snippets

Below is a list of all snippets currently -supported- in on this package and the triggers of each one. The **⇥** means the `TAB` key.

### Specs
- `describe`: desc⇥
- `xdescribe`: xdesc⇥
- `it`: it⇥
- `xit`: xit⇥
- `afterEach`: ae⇥
- `beforeEach`: be⇥
- `after`: aft⇥
- `before`: bef⇥
- `expect().not.to.equal`: ne⇥
- 
### Expectations
- `expect`: exp⇥
- `expect().to.be`: tb⇥
- `expect().to.equal`: te⇥
- `expect().to.eql`: tde⇥ (to deep equal)
- `expect().to.match`: tm⇥ 
- `expect().to.be.true`: tbt⇥
- `expect().to.have.length`: thl⇥
- `expect().to.be.false`: tbf⇥
- `expect().to.be.defined`: tbu⇥
- `expect().not.to.be.defined`: nu⇥

- `expect().to.be.defined`: tbd⇥
- `expect().to.be.above`: tbgt⇥
- `expect().to.be.below`: tblt⇥
- `expect().to.be.null`: tbn⇥
- `expect().to.have.string`: tc⇥
- `expect().to.match`: tm⇥
- `expect().to.throw`: tt⇥
- `expect().to.throw(Error)`: tte⇥
- `expect().not.to.match`: nm⇥
- `expect().not.to.be`: nb⇥
- `expect().not.to.be.defined`: nd⇥
- `expect().not.toBeGreaterThan`: ngt⇥
- `expect().not.to.be.null`: nn⇥
- `expect().not.to.have.string`: nc⇥
- `expect().not.to.throw`: nt⇥


## Commands

### Switch between code and spec

This command will open the spec or source file that has the same path of the active view file.
If you're looking at a source file and the package can't find any specs, it'll display a list of possible directories to create a new one.

To run this command, you can use `ctrl+.`/`super+.` or `ctrl+shift+.`/`super+shift+.`, this last one will open a split view. Also you can select `Jasmine: Switch between code and spec` from the command palette.

### Create spec file

This command is exactly the same as running `Jasmine: Switch between code and spec` and not finding specs.

It doesn't have a key binding, but you can use `jasmine_create_spec` as a command name, like this:

`{ "keys": ["KEYS"], "command": "jasmine_create_spec", "args": { "split_view": false } }`

### (legacy) Switch between code and spec

Runs the command from [@gja](https://github.com/gja) package, found in [run_jasmine.py](https://github.com/gja/sublime-text-2-jasmine/blob/master/run_jasmine.py).

If you want to setup a keybinding for it, you can use:

`{ "keys": ["KEYS"], "command": "legacy_jasmine_switch" }`

### Toggle quotes

This command will change the snippets from the current active quotes to it's counterpart.

For example, it will transform this:

````
describe("Name of the group", function() {
    
});
````

to this

````
describe('Name of the group', function() {
    
});
````

If you want to setup a keybinding for it, you can use:

`{ "keys": ["KEYS"], "command": "jasmine_toggle_quotes" }`

**Important!**

After each toggle you may need to restart Sublime to the changes to take effect.

### Command Settings

There are two possible settings:
```javascript
{
    // Ignore directories when searching for files (source and specs)
    "ignored_directories": [".git", "vendor", "tmp", "node_modules"],

    // The parent folder name for the spec files
    "jasmine_path": "spec",

    // Extension used when creating a new spec file. 
    "spec_file_extension": ".spec.js"
}
```

**Remember** that this settings only apply to the new command (they won't affect `(legacy) Switch between code and spec`).

## Syntax

With this package, the editor will recognize `.spec.js` files as having Jasmine syntax. It will highlight `(x)describe` and `(x)it`.

Take into account that any other packages that are using `javascript` as a syntax may not work with `jasmine`, you can always turn it back off by opening a `.spec.js` file and selecting "View > Syntax > Open all with current extension as... > Javascript".

## Installation

### PackageControl

If you have [PackageControl](http://wbond.net/sublime_packages/package_control) installed, you can use it to install the package.

Just type `cmd-shift-p`/`ctrl-shift-p` to bring up the command pallete and pick `Package Control: Install Package` from the dropdown, search and select the package there and you're all set.

### Manual

You can clone the repo in your `/Packages` (*Preferences -> Browse Packages...*) folder and start using/hacking it.
    
    cd ~/path/to/Packages
    git clone https://github.com/NicoSantangelo/sublime-jasmine.git Jasmine
