## lokalise2 file download

Download files

### Synopsis

Exports project files as a .zip bundle. Generated bundle will be uploaded to an Amazon S3 bucket, which will be stored there for 12 months available to download. As the bundle is generated and uploaded you would get a response with the URL to the file. Requires Download files admin right.

```
lokalise2 file download [flags]
```

### Options

```
      --add-newline-eof                         Enable to add new line at end of file (if supported by format).
      --all-platforms                           Enable to include all platform keys. If disabled, only the keys associated with the platform of the format will be exported.
      --bundle-description string               Description of the created bundle. Applies to ios_sdk or android_sdk OTA SDK bundles.
      --bundle-structure string                 (With --original-filenames=false only.) Bundle structure. Placeholders available in constructuion are %LANG_ISO%, %LANG_NAME%, %FORMAT%, and %PROJECT_NAME%.
      --custom-translation-status-ids strings   Only translations attributed to selected custom statuses will be included. Leave empty for all.
      --dest string                             Destination folder for ZIP file. (default "./")
      --directory-prefix string                 (With --original-filenames=true only.) Directory prefix in the bundle. Placeholder available in construction is %LANG_ISO%.
      --disable-references                      Enable to skip automatic replacement of key reference placeholders (e.g. [%key:hello_world%]) with their corresponding translations.
      --escape-percent                          (With --placeholder-format=printf only.) When enabled, all universal percent placeholders "[%]" will be always exported as "%%".
      --exclude-tags strings                    Exclude keys with the specified tags.
      --export-empty-as string                  How empty translations will be exported. Allowed values are empty (to export empty values), base (to replace with the base language value), or skip (to omit).
      --export-sort string                      Sort keys by specified method. Allowed values are first_added, last_added, last_updated, a_z, or z_a.
      --filter-data strings                     Narrow export data range. Allowed values are translated, untranslated, reviewed, reviewed_only, last_reviewed_only, nonfuzzy, and nonhidden. (Note: "Fuzzy" is now called "Unverified" in the editor.)
      --filter-filenames strings                Only keys attributed to selected files will be included. Leave empty for all.
      --filter-langs strings                    List of languages to export. Omit this parameter for all languages.
      --filter-repositories strings             Pull requests will be created only for listed repositories (organization/repository format). Leave empty array to process all configured integrations by platform only.
      --format string                           File format. Allowed values are the file extension of any of the supported file formats we support (e.g. json, strings, xml) or ios_sdk or android_sdk for respective OTA SDK bundles. (required)
  -h, --help                                    help for download
      --icu-numeric                             (With --plural-format=icu only.) If enabled, plural forms zero, one, and two will be replaced with =0, =1, and =2, respectively.
      --include-comments                        Enable to include key comments and descriptions in exported file (if supported by the format).
      --include-description                     Disable to exclude key descriptions in exported file (if supported by the format). (default true)
      --include-pids strings                    Other projects ID's, which keys should be included with this export.
      --include-tags strings                    Narrow export range to tags specified.
      --indentation string                      Override default indentation with specified spacing (in supported files). Allowed values are default, 1sp, 2sp, 3sp, 4sp, 5sp, 6sp, 7sp, 8sp, or tab.
      --java-properties-encoding string         (Java Properties export only.) Encoding for .properties files. Allowed values are utf-8 and latin-1.
      --java-properties-separator string        (Java Properties export only.) Separator for keys/values in .properties files. Allowed values are = and :.
      --json-only                               Only return the API JSON response.
      --json-unescaped-slashes                  (With --format=json only.) Enable to leave forward slashes unescaped.
      --keep-zip                                Keep or delete ZIP file after being unpacked.
      --language-mapping string                 List of languages to override default iso codes for this export (JSON, see https://lokalise.com/api2docs/curl/#transition-download-files-post).
      --original-filenames                      Enable to use original filenames/formats. If set to false, all keys will be exported to a single file per language. (default true)
      --placeholder-format string               Override the default placeholder format for the file type. Allowed values are printf, ios, icu, net, symfony.
      --plural-format string                    Override the default plural format for the file type. Allowed values are json_string, icu, array, generic, symfony.
      --replace-breaks                          Enable to replace line breaks in exported translations with \n (default true). Use --replace-breaks=false to disable. (default true)
      --triggers strings                        Trigger integration exports (must be enabled in project settings). Allowed values are amazons3, gcs, github, gitlab, bitbucket.
      --unzip-to string                         Unzip to this folder. (default "./")
      --webhook-url string                      Once the export is complete, sends a HTTP POST with the generated bundle URL to the specified URL.
      --yaml-include-root                       (YAML export only). Enable to include language ISO code as root key.
```

### Options inherited from parent commands

```
      --config string       config file (default is ./config.yml)
      --project-id string   Unique project identifier (required).
  -t, --token string        API token. You can create API tokens at https://lokalise.com/profile.
```

### SEE ALSO

* [lokalise2 file](lokalise2_file.md)	 - Upload and download files

###### Auto generated by spf13/cobra on 28-Jul-2020
