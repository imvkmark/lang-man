# man - appledoc(9)

Usage: appledoc [OPTIONS] <paths to source dirs or files>

PATHS
  -o, --output <path>                     Output path
  -t, --templates <path>                  Template files path
      --docset-install-path <path>        DocSet installation path
  -s, --include <path>                    Include static doc(s) at path
  -i, --ignore <path>                     Ignore given path
  -x, --exclude-output <path>             Exclude given path from output
      --index-desc <path>                 File including main index description

PROJECT INFO
  -p, --project-name <string>             Project name
  -v, --project-version <string>          Project version
  -c, --project-company <string>          Project company
      --company-id <string>               Company UTI (i.e. reverse DNS name)

OUTPUT GENERATION
  -h, --create-html                       [b] Create HTML
  -d, --create-docset                     [b] Create documentation set
  -n, --install-docset                    [b] Install documentation set to Xcode
  -u, --publish-docset                    [b] Prepare DocSet for publishing
      --html-anchors <string>             [*] The html anchor format to use in DocSet HTML.
      --clean-output                      [b] Remove contents of output path before starting !!CAUTION!!

OPTIONS
      --keep-intermediate-files           [b] Keep intermediate files in output path
      --keep-undocumented-objects         [b] Keep undocumented objects
      --keep-undocumented-members         [b] Keep undocumented members
      --search-undocumented-doc           [b] Search undocumented members documentation
      --repeat-first-par                  [b] Repeat first paragraph in member documentation
      --preprocess-headerdoc              [b] Preprocess header doc comments - 10.7 only!
      --print-information-block-titles    [b] Print title of information blocks. "Note:", "Warning:", etc.
      --use-single-star                   [b] Use single star for bold marker
      --merge-categories                  [b] Merge categories to classes
      --merge-category-comment            [b] Merge category comment to class
      --keep-merged-sections              [b] Keep merged categories sections
      --prefix-merged-sections            [b] Prefix merged sections with category name
      --explicit-crossref                 [b] Shortcut for explicit default cross ref template
      --use-code-order                    [b] Order sections by the order specified in the input files
      --crossref-format <string>          Cross reference template regex
      --exit-threshold <number>           Exit code threshold below which 0 is returned

WARNINGS
      --warn-missing-output-path          [b] Warn if output path is not given
      --warn-missing-company-id           [b] Warn if company ID is not given
      --warn-undocumented-object          [b] Warn on undocumented object
      --warn-undocumented-member          [b] Warn on undocumented member
      --warn-empty-description            [b] Warn on empty description block
      --warn-unknown-directive            [b] Warn on unknown directive or format
      --warn-invalid-crossref             [b] Warn on invalid cross reference
      --warn-missing-arg                  [b] Warn on missing method argument documentation

DOCUMENTATION SET INFO
      --docset-bundle-id <string>         [*] DocSet bundle identifier
      --docset-bundle-name <string>       [*] DocSet bundle name
      --docset-desc <string>              [*] DocSet description
      --docset-copyright <string>         [*] DocSet copyright message
      --docset-feed-name <string>         [*] DocSet feed name
      --docset-feed-url <string>          [*] DocSet feed URL
      --docset-feed-formats <values>      DocSet feed formats. Separated by a comma [atom,xml]
      --docset-package-url <string>       [*] DocSet package (.xar) URL
      --docset-fallback-url <string>      [*] DocSet fallback URL
      --docset-publisher-id <string>      [*] DocSet publisher identifier
      --docset-publisher-name <string>    [*] DocSet publisher name
      --docset-min-xcode-version <string> [*] DocSet min. Xcode version
      --docset-platform-family <string>   [*] DocSet platform familiy
      --docset-cert-issuer <string>       [*] DocSet certificate issuer
      --docset-cert-signer <string>       [*] DocSet certificate signer
      --docset-bundle-filename <string>   [*] DocSet bundle filename
      --docset-atom-filename <string>     [*] DocSet atom feed filename
      --docset-xml-filename <string>      [*] DocSet xml feed filename
      --docset-package-filename <string>  [*] DocSet package (.xar,.tgz) filename. Leave off the extension. This will be added depending on the generated package.

MISCELLANEOUS
      --logformat <number>                Log format [0-3]
      --verbose <value>                   Log verbosity level [0-6,xcode]
      --version                           Display version and exit
      --help                              Display this help and exit

==================================================================
[b] boolean parameter, uses no value, use --no- prefix to negate.

[*] indicates parameters accepting placeholder strings:
- %PROJECT replaced with --project-name
- %PROJECTID replaced with normalized --project-name
- %VERSION replaced with --project-version
- %VERSIONID replaced with normalized --project-version
- %COMPANY replaced with --project-company
- %COMPANYID replaced with --company-id
- %YEAR replaced with current year (format yyyy)
- %UPDATEDATE replaced with current date (format yyyy-MM-dd)
- %DOCSETBUNDLEFILENAME replaced with --docset-bundle-filename
- %DOCSETATOMFILENAME replaced with --docset-atom-filename
- %DOCSETPACKAGEFILENAME replaced with --docset-package-filename

Find more help and tips online:
- http://appledoc.gentlebytes.com/
- http://tomaz.github.com/appledoc/

appledoc uses the following open source components, fully or partially:

- DDCli by Dave Dribin
- CocoaLumberjack by Robbie Hanson
- ParseKit by Todd Ditchendorf
- RegexKitLite by John Engelhart
- GRMustache by Gwendal Roué
- Discount by David Parsons
- Timing functions from Apple examples

We'd like to thank all authors for their contribution!