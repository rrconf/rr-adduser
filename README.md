# require adduser

```
[export ADDUSER_NAME=<string>]
[export ADDUSER_UID=<number>]
[export ADDUSER_UIDFORCE=<number>]
[export ADDUSER_GID=<number>]
[export ADDUSER_GIDFORCE=<number>]
[export ADDUSER_GROUP=<string>]
[export ADDUSER_HOME=<string>]
[export ADDUSER_GECOS=<string>]
[export ADDUSER_SHELL=<string>]
require adduser [username]
```

Ensure that a named user exists in the system. Either the environment variable `ADDUSER_NAME` or an argument `username` must be provided, argument has preference over environment variable.

The user is created with disabled password, existing user password is not changed.

If `ADDUSER_UID` is set, the creation of the user uses given UID. If the user already exists, and also `ADDUSER_UIDFORCE` is provided, the module fails if the user exists with a different UID.

If `ADDUSER_GID` is set, the creation of the user uses given GID. If the user already exists, and also `ADDUSER_GIDFORCE` is provided, the module fails if the user exists with a different GID.

If `ADDUSER_GROUP` is provided, the user is added to this group as the primary group. If the group does not exist, it will be created.

The `ADDUSER_HOME`, `ADDUSER_GECOS` and `ADDUSER_SHELL` allow to specify details for the user being created. They default to `/home/$ADDUSER_NAME`, `$ADDUSER_NAME` and `/bin/bash`.
