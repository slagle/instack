instack
=======

Execute diskimage-builder[1] elements on the current system.  This enables a
current running system to have an element applied in the same way that
diskimage-builder applies the element to an image build.

[1] https://github.com/stackforge/diskimage-builder

An undercloud based installer that uses instack is at:
https://github.com/slagle/instack-undercloud

Use the command line arguments for fine grained control over which elements to
apply, or drive instack via a declarative style json file (see
https://github.com/slagle/instack-undercloud/blob/master/json-files/fedora-20-undercloud.json
for an example).

<pre><code>
usage: instack [-h] [-e [ELEMENT [ELEMENT ...]]]
               [-p ELEMENT_PATH [ELEMENT_PATH ...]] [-k [HOOK [HOOK ...]]]
               [-b [BLACKLIST [BLACKLIST ...]]]
               [-x [EXCLUDE_ELEMENT [EXCLUDE_ELEMENT ...]]] [-j JSON_FILE]
               [-d] [-i] [--dry-run] [--no-cleanup]

Execute diskimage-builder elements on the current system.

optional arguments:
  -h, --help            show this help message and exit
  -e [ELEMENT [ELEMENT ...]], --element [ELEMENT [ELEMENT ...]]
                        element(s) to execute
  -p ELEMENT_PATH [ELEMENT_PATH ...], --element-path ELEMENT_PATH [ELEMENT_PATH ...]
                        element path(s) to search for elements (ELEMENTS_PATH
                        environment variable will take precedence if defined)
  -k [HOOK [HOOK ...]], --hook [HOOK [HOOK ...]]
                        hook(s) to execute for each element
  -b [BLACKLIST [BLACKLIST ...]], --blacklist [BLACKLIST [BLACKLIST ...]]
                        script names, that if found, will be blacklisted and
                        not run
  -x [EXCLUDE_ELEMENT [EXCLUDE_ELEMENT ...]], --exclude-element [EXCLUDE_ELEMENT [EXCLUDE_ELEMENT ...]]
                        element names that will be excluded from running even
                        if they are listed as dependencies
  -j JSON_FILE, --json-file JSON_FILE
                        read runtime configuration from json file
  -d, --debug           Debugging output
  -i, --interactive     If set, prompt to continue running after a failed
                        script.
  --dry-run             Dry run only, don't actually modify system, prints out
                        what would have been run.
  --no-cleanup          Do not cleanup tmp directories
</code></pre>

