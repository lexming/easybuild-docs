# Enhancements in EasyBuild v5.0

*(for a full overview of changes in EasyBuild v5.0, see [here](overview-of-changes.md))*

Various significant enhancements are included in EasyBuild v5.0, including:

* [`run_shell_cmd` function][run_shell_cmd]
* [Granular exit codes][granular_exit_codes]

---

## `run_shell_cmd` function { : #run_shell_cmd }

See dedicated page on the new [`run_shell_cmd` function](run_shell_cmd.md).

## Granular exit codes { : #granular_exit_codes }

EasyBuild v5 now uses a range of ~50 exit codes instead of just 0 for normal
termination and 1 for unexpected termination. Each non-zero exit code
correlates to the specific type of error or failure that caused the
termination of the program. For instance, a missing easyconfig or a failed
checksum check. The full list of exit codes is defined in the class
[easybuild.tools.build_log.EasyBuildExit](https://github.com/easybuilders/easybuild-framework/blob/main/easybuild/tools/build_log.py#L74).

EasyBuild will always return its own exit codes on termination. Other exit
codes from external processes executed through `run_shell_cmd` or HTTP response
status codes are reported in the corresponding logs.
