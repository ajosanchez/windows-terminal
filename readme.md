# Windows Terminal Config
Keep all your terminals in one place
___

1. [Download](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) and install the Windows Terminal 

2. Select the dropdown icon near the first tab to edit the settings.json file. This file includes the terminals you want access to and how they should open:

For example, my Miniconda3 terminal is configured as follows:
```
{
	"guid": "{c6eaf9f4-32a7-5fdc-b5cf-066e8a4b9999}",
	"hidden": false,
	"name": "Miniconda",
	"icon": "C:\\Users\\alex.s\\Documents\\anaconda-logo.ico",
	"startingDirectory": "C:\\Users\\alex.s",
	"commandline": "powershell.exe -ExecutionPolicy ByPass -NoExit -Command & 'C:\\Users\\alex.s\\Miniconda3\\shell\\condabin\\conda-hook.ps1' ; conda activate 'C:\\Users\\alex.s\\Miniconda3'"
}
```

And here's my git bash configuration:
```
{
    "guid": "{c6eaf9f4-32a7-5fdc-b5cf-066e8a4b9139}",
    "hidden": false,
    "name": "Git Bash",
    "icon": "%PROGRAMFILES%\\git\\mingw64\\share\\git\\git-for-windows.ico",
    "commandline": "\"%PROGRAMFILES%\\git\\bin\\bash.exe\" --login -i -l",
    "startingDirectory": "C:\\Users\\alex.s"
}
```

At the very top you'll notice a default config. Put the guid of the terminal you want to open by default. For mine, I use Miniconda3.

The trickiest part is getting the "commandline" setting just right so it opens exactly as that terminal would. To find the command, search for the terminal in the Windows search box at the bottom left of your screen. Once you see the icon of the terminal in the results, right-click on it and select "open file folder." With the folder now open, find the icon/shortcut for the terminal you want and right-click -> properties. The command you need is in the target box so copy and paste it under "commandline". However, this command doesn't always work perfectly so you may need to twaek it. Reference the examples above or do some googling to find just the right way to specify the command.

I also like to have the appropriate icon which instead of a default. For Miniconda3 I downloaded the Anaconda logo and used a service online to convert the image to a .ico file. Voila!
