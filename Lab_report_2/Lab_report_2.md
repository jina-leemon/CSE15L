# [Lab Report 2: Setting Remote Environments](https://jina-leemon.github.io/CSE15L/Lab_report_2/Lab_report_2)

### Code change 1:

![Code change diff 1](https://jina-leemon.github.io/CSE15L/Lab_report_2/code_fix_1_diff.png)

**Code change** <br>
This is the first code change diff.
The link to the test file for the failure-inducing input that promted my group to make the change is here: <br>

[failure input: there is no link (new-file-2.md)](https://github.com/jina-leemon/markdown-parser/blob/main/new-file-2.md)

**The symptom**: java throws index out of bounds error
(not in the commit message history but couldn't edit that so added it in as a comment)

**Description**:<br>
relationship between the bug, the symptom, and the failure-inducing input:<br>

The symptom of the failure was that java threw an index out of bounds error since there was no index of "(", ")", "[", "]" when there are no brackets or paranthesis to begin with. <br>
The input is a file with no () or []. However, the code looks for these indicators and takes the position (index).<br>
The bug is that there is no check that () and [] are absent, and the symptom is that java throws and index out of bounds error.
We resolved this by adding a check when all the indices are -1 (not found)
<br>
<br>

### Code change 2:

![Code change diff 2](https://jina-leemon.github.io/CSE15L/Lab_report_2/code_fix_2_diff.png)

**Code change** <br>
The failure-inducing input is a image file that is recognized as a link. The link to this file can be found here: <br>

[failure input: there is no link](https://github.com/jina-leemon/markdown-parser/blob/main/new-file-3.md)

**The symptom**: <br>
The code returns images as link. The code should throw an error in this case.

**Description**:<br>
relationship between the bug, the symptom, and the failure-inducing input:<br>

The failure-inducing input is a image markdown instead of a link. The bug is that there is no check in the code to see if the link-like text (with [] and ()) is in fact an image (has ! in the beginning). The following symptom is that even images are recognized as a link. In <br>
In order to resolve this we checked that there is a "!" in the beginning and breaks if there is (meaning it is an image).
<br>
<br>

### Code change 3:

![Code change diff 3](https://jina-leemon.github.io/CSE15L/Lab_report_2/code_fix_3_diff.png)

**Code change** <br>
The failure-inducing input is a link description [] with empty address ()
For example, \[website]()
<br>

[failure input: () empty](https://github.com/jina-leemon/markdown-parser/blob/main/new-file-4.md)

**The symptom**: <br>
There is no link in this case but the return is not empty.

**Description**:<br>
relationship between the bug, the symptom, and the failure-inducing input:<br>

The input has a () and a [] but nothing inside the () where the link address is supposed to be.<br>
Accordingly, the symptom is that there is a non-empty output and the bug is that the code cannot detect that the length between the openParan and closeParan is 0.<br>
To fix this we added an if statement checking that the length between the paranthesis is not zero and returning a link if this is true.
<br>
<br>
