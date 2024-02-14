# Instructions

The following guide should allow users to connect to the DGX-1 by running `ssh dgx` in the terminal.

Note: These instructions are only applicable to CS staff and students.

## Getting set up

1. To start, you'll need to get a user account on the DGX-1.

- Email cs-support@st-andrews.ac.uk. **Attach your SSH public key** and request that a user account be created. 
- Once an account is created you can SSH into the DGX-1. For connecting outside of the university network, utilise the cs-jump service.

2. On your main machine, assuming linux or macOS (possibly different for windows), you can edit the **~/.ssh/config** file to _bookmark_ the DGX-1. See an example of this below:

```bash
Host cs-jump
    HostName jump.cs.st-andrews.ac.uk
    User <st-andrews username>
    Port 22
    IdentityFile ~/.ssh/id_rsa
    IdentitiesOnly yes

Host dgx
    HostName nv-dgx-1.st-andrews.ac.uk
    User <st-andrews username>
    Port 22
    IdentitiesOnly yes
    ProxyJump cs-jump
```

3. Now you can access the DGX-1 by typing `ssh dgx` in your terminal.

Note that the above can also be used similarly to access an office/lab machine remotely.

---

# Best practices of using the DGX-1

In terms of best practice, using Docker or an alternative to Docker is essential. Ideally containers should not be running endlessly. Experimenmts should be designed such that you spin up the container to run the experiment and then automatically shut it down after the results have been extracted. Furthermore, you should avoid running containers in an _interactive_ manner where possible.

## Disclaimer

This guide is provided for informational purposes only. While every effort has been made to ensure accuracy and completeness, the instructions and advice contained within this document are provided without warranty of any kind. The University of St Andrews, the authors, and contributors shall not be held liable for any direct or indirect damages or issues arising from the use of this guide. Users should follow these instructions at their own risk and are encouraged to verify the steps and adapt them as necessary for their specific needs and environments. Please read https://wiki.cs.st-andrews.ac.uk/ for more information. IT Services recommendation is to use the key agent rather than explicitly specifying a key. This is covered on the wiki:
https://wiki.cs.st-andrews.ac.uk/index.php?title=Using_SSH#Using_the_SSH_agent
