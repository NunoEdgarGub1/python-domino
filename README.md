# python-domino

Python bindings for the Domino Data Lab API. Permits interaction with a Domino server from Python
using the API.

## Overview

### Setting up the connection

You can set up the connection by creating new instance of `Domino`. The parameters are:

* project: A project identifier (in the form of ownerusername/projectname)
* api_ky: (Optional) An API key to authenticate with. If not provided the library will expect to find one
  in the DOMINO_USER_API_KEY environment variable.
* host: (Optional) A host URL. If not provided the library will expect to find one in the DOMINO_API_HOST
  environment variable.

### Domino#runs_list

List the runs on the selected project.

### Domino#runs_start

Start a new run on the selected project. The parameters are:

* command: The command to run as an array of strings where members of the array represent arguments
  of the command. E.g. `["main.py", "hi mom"]`
* isDirect: (Optional) Whether or not this command should be passed directly to a shell.
* commitId: (Optional) The commitId to launch from. If not provided, will launch from latest commit.
* title: (Optional) A title for the run.
* tier: (Optional) The hardware tier to use for the run. Will use project default tier if not provided.
* publishApiEndpoint: (Optional) Whether or not to publish an API endpoint from the resulting output.

### Domino#files_list

List the files in a folder in the Domino project. The parameters are:

* commitId: The commitId to list files from.
* path: (Defaults to "/") The path to list from.

### Domino#blobs_get

Retrieve a file from the Domino server by blob key. The parameters are:

* key: The key of the file to fetch from the blob server.

## License

This library is made available under the Apache 2.0 License. This is an open-source project of
[Domino Data Lab](https://www.dominodatalab.com).
