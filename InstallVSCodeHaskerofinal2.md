# Installation of VS Code with Haskero Extension for a Immersive Haskell Experience - Windows 10

![MattMMarkdownEmblem](https://github.com/Matthew-Mosior/Software-Setup-Guides/blob/master/githubmarkdownemblem.png)

# Introduction
___

This installation guide will give you a step-by-step walkthrough on installing a rich, fast, and friendly code editor for Haskell development, and many other programming languages if you so choose!

> OS: Windows 10

> Estimated Time to Completion: 45 minutes

# Background 
___

To provide some insight on the tools you'll be installing and working with:

- [Haskell](https://www.haskell.org) - A functional programming language.
- [Haskell Platform](https://www.haskell.org/downloads#platform) - A fully functional all-in-one installer that provides the necessary components to program in Haskell.
- [VS Code](https://code.visualstudio.com/) - A code editor from Microsoft with many useful extensions (programs that can be downloaded and used within the editor itself).
- [Haskero](https://marketplace.visualstudio.com/items?itemName=Vans.haskero) - A VS Code extension that utilizes stack and intero to guide the user through the wonderful world of Haskell.
    - [Intero](https://github.com/commercialhaskell/intero) - A backend program that will allow Haskero to operate to its fullest extent.
- [Windows Powershell](https://support.microsoft.com/en-us/help/968929/windows-management-framework-windows-powershell-2-0--winrm-2-0--and-bi) - The command-line terminal you will use to work with all Haskell development, comes standard in Windows 10 machines.

# Walkthrough
___

> Before you start, make sure to backup your pc.  

1. Download the Haskell Platform.
    -  Click this [link](https://www.haskell.org/platform/windows.html) to download the Haskell Platform.  You will see two choices under step 1:
        - Download Core (64 bit)
        - Download Full (64 bit) : ~ 2 Gb download size
    - The real difference between these two is how many built in Haskell libraries you would like.  If you see yourself using or experimenting with many additional already-build libraries, go ahead and click Download Full (64 bit), otherwise click Download Core (64 bit).
    - Regardless of download choice, click the "run" option that will pop-up in your window.  This will run the installer executable.
    - The installer will then pop up on your screen after minimizing your browser window.
    - Follow the instructions within the installer and do not change the install locations for any of the components, use the default locations.
    - The installer will install the Glasgow Haskell Compiler (GHC), stack tool, cabal build system, 35 core and commonly implemented packages.  You will get extra libraries if you downloaded the Full platform. 
2. Download Intero
    - Click this [link](https://github.com/commercialhaskell/intero) to go to the Intero Github page (Credit: [commercialhaskell](https://github.com/commercialhaskell)).
    - On the Intero Github page, click the "Releases" tab within the main toolbar near the top of the page.
    - Within the "Releases" tab, click on the most recent release listed near the top of the screen (should be in the following format: a.bc.def where a,b,c,d,e and f are integers)
    - Click the "save" option that will pop-up in your window.  This will save the Intero files to your pc.
3. Download VS Code, Haskero and Start a Hello world Haskell Project.
    - Click this [link](https://code.visualstudio.com/) to go to VS Code homepage.  
        - On the homepage click the green button in the middle that says "Download for Windows Stable Build".
    - Click the "run" option that will pop-up in your window.  This will run the installer executable.
    - The installer will then pop-up on your screen after minimizing your browser window.
    - Follow the instructions within the installer and do not change the install locations for any of the components, use the default locations.
        - Within the installer, a setup screen will have four options with checkboxes next to them, with the last already checked off.  The last checkbox places VS Code in your pc's registry, this is important. The first three are optional, but can be useful with quickly opening outside files into VS Code and giving it setup icon within the start-up menu. 
    - After VS Code is successfully installed, open VS Code a Welcome tab will greet you.
    - On the right side of the Welcome tab, click the box the says "Tools and Languages".
    - After clicking "Tools and languages", the toolbar of the left side of the screen will have opened up with a search bar at the top.  
    - Type "Haskero" into the search bar.
    - Under the choice named "Haskero", click the button on the choice that says "Install".
    - After a short time, this "Install" button will say "Reload", click it.
        - The will install and load the Haskero extension.
    - Click File -> Preferences -> Settings.
        - A "settings.json" file will appear in the main toolbar (tab should say "User Settings").
    - Within "settings.json", find the "Haskero Configurations" drop-down menu.
        - Within the drop-down menu, look for the "haskero.intero.stackpath" setting. 
        - It should have "stack" as its value.  This is value we will use, keep it.
    - Click the very top folder symbol on the top of the toolbar at left side of the screen.
    - Click the open folder button within the toolbar.
    - This will open the pc's file explorer.
    - Create a new folder named "Haskell" or select an exisiting folder.  This is based on how you want your Haskell stack projects organized.
    - Click the "Terminal" tab on the top left of the toolbar at the bottom left of the screen.
    - This is a Powershell terminal, you will use this to initiate all Haskell commands.
        - You should be within the directory containing the folder you just created or chose.  If not, please Set-Location or cd to the location of the folder.
    - **The next steps are important!!**
        - Your terminal should look like this:  
            ```PS SomeDrive:\Path\To\Your\Folder>```
        - Now we call the "stack new" command to create a new stack project.  We'll call it helloworld.
        - Go ahead and type in the location of your stack.exe.  This is the stack toolchain executable that was installed within Haskell Platform.
            - If you don't know its location (you probably won't since you used the default settings when installing Haskell Platform) go ahead and type stack.exe within the search bar in your file explorer window.  Make sure you do this once you are inside your OS drive (this is typically were programs reside, so its probably the C: drive).  
        ```PS SomeDrive:\Path\To\Your\Folder> SomeDrive:\Path\To\stack.exe stack new helloworld new-template```
            - This command will create a new stack project named "helloworld" within the folder you opened in VS Code.  
                 - You should see something like this:  

> Downloading template "new-template" to create project "helloworld" in helloworld/ ...
>Using the following authorship configuration:
>author-email: example@example.com
>author-name: Example Author Name
>Copy these to /home/matt/.stack/config.yaml and edit to use different values.
>Writing default config file to: /home/matt/helloworld/stack.yaml
>Basing on cabal files:
>/home/matt/helloworld/helloworld.cabal
>Downloaded lts-3.2 build plan.
>Caching build plan
>Fetched package index.
>Populated index cache.
>Checking against build plan lts-3.2
>Selected resolver: lts-3.2
>Wrote project config to: /home/matt/helloworld/stack.yaml
- The next step is to create a sandboxed GHC complier within the helloworld project you just created. (Don't worry, your not reinstalling it, its just making a instance of it to use within the immediate stack project).  
        ```PS SomeDrive:\Path\To\Your\Folder\helloworld> stack setup```
                - You should see something like this:
> Downloaded ghc-7.10.2.
> Installed GHC.
> stack will use a sandboxed GHC it installed
> For more information on paths, see 'stack path' and 'stack exec env'
> To use this GHC and packages outside of a project, consider using:
> stack ghc, stack ghci, stack runghc, or stack exec
- Now its time to use the command "stack build".   
```PS SomeDrive:\Path\To\Your\Folder\helloworld> stack build```
   - This will build your helloworld project and create a local helloworld-exe.  
   - You should see something like this:
> helloworld-0.1.0.0: configure
> Configuring helloworld-0.1.0.0...
> helloworld-0.1.0.0: build
> Preprocessing library helloworld-0.1.0.0...
> [1 of 1] Compiling Lib              ( src/Lib.hs, >.stack-work/dist/x86_64-linux/Cabal-1.22.4.0/build/Lib.o )
> In-place registering helloworld-0.1.0.0...
> Preprocessing executable 'helloworld-exe' for helloworld-0.1.0.0...
> [1 of 1] Compiling Main             ( app/Main.hs, >.stack-work/dist/x86_64-linux/Cabal-1.22.4.0/build/helloworld-exe/helloworld-exe-tmp/Main.o )
> Linking .stack-work/dist/x86_64-linux/Cabal-1.22.4.0/build/helloworld-exe/helloworld-exe ...
> helloworld-0.1.0.0: install
> Installing library in
> /home/matt/helloworld/.stack-work/install/x86_64-linux/lts-3.2/7.10.2/lib/x86_64-linux-ghc-7> .10.2/helloworld-0.1.0.0-6urpPe0MO7OHasGCFSyIAT
> Installing executable(s) in
> /home/matt/helloworld/.stack-work/install/x86_64-linux/lts-3.2/7.10.2/bin
> Registering helloworld-0.1.0.0...
- It's finally time to run your executable!  
```PS SomeDrive:\Path\To\Your\Folder\helloworld> stack exec helloworld-exe```
    - This will output the string "someFunc", which will make sense once you take a look at your Main.hs file.
    - You should see something like this:
> matt@d30er5643dfS:~/helloworld$ stack exec helloworld-exe
> someFunc
- One last thing to show you...
    - Click on the "Output" tab within the toolbar on the bottom of VS Code.  
        - This should display the following:  
> Initializing Haskero...
> Spawning process 'stack' with command 'stack ghci --with-ghc intero   >"--ghci-options=-ignore-dot-ghci -Wall" --no-build --no-load'
>Haskero initialization done.
- This means Haskero is working as intended.

#### Congratulations! You've now successfully installed the proper components to create, build, and execute a new stack project using the Haskero extension within VS Code.  Enjoy!

> For more clarification on any of the instructions once working within powershell, please follow this [link](https://docs.haskellstack.org/en/stable/GUIDE/)

# Credits

> **Haskell Stack Documentation:** [Stack Contributors](https://docs.haskellstack.org/en/stable/README/)

> **Haskero:** [Julien Vannesson](https://gitlab.com/vannnns/haskero) 

> **Intero:** [Commercialhaskell](https://github.com/commercialhaskell) Contributors: [chrisdone](https://github.com/chrisdone), [purcell](https://github.com/purcell) et al.

#### Documentation created by [Matthew Mosior](https://github.com/Matthew-Mosior), October 2017.



