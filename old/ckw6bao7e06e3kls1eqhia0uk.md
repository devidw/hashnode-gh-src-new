## How to combine all text files of a folder into a single file using Bash on Windows

You have a directory structure of a folder containing a handful of text files? And you want to merge all these files in that specific folder into a single text file, which then contains the content of all the text files?

Thanks to shell scripting, we do not have to do that manually. 

Here is what we are going to use to automate this job: 

1. On Windows, there is that command called `type`, which we can use in the Command Prompt to get the content of a given text file.
   Here is what the [docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/type) say on `type`:

> In the Windows Command shell, type is a built in command which displays the contents of a text file. Use the type command to view a text file without modifying it.

2. In order to get the contents of all text files in a folder, we will make use of the asterix operator (`*`).
3. And to save the merged contents into a new text file, we will use the `>` redirection operator.

Here is the full command:

```bash
type *.txt > combined.txt
```

* In the command above, we only selected files with an extension of `.txt`, when you are working with different content types → that's the place to specify it.
* Here `combined.txt` is the location the output of the `type` command will be saved to.

## Automated opening (optional)

Most likely, you want to open the merged file after creation. Using the [`start`](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/start) command, we can tell the Command Prompt to do that for us as well.

```bash
type *.txt > combined.txt && start combined.txt
```

Here we used the `&&` syntax to run both commands at once. Chaining these commands using `&&` instead of `&` we make sure that the chained command only gets executed, when the previous command was successfully.