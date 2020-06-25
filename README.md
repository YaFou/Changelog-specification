# Changelog specification

## Specification

### Summary
1. Key words
2. File name
3. Keep a changelog specification
4. Changelog title
5. Changelog header
6. Releases
7. Releases order
8. Releases links
9. Releases dates
10. Changes from the previous release
11. Sections
12. Sementic Versionning specification
13. Entry format
14. Added entries
15. Changed entries
16. Deprecated entries
17. Removed entries
18. Fixed entries
19. Security entries
20. Upgrade entries

---

1. The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **RECOMMENDED**,  **MAY**, and **OPTIONAL** in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).

2. The changelog file **SHOULD** be named `CHANGELOG` with an **OPTIONAL** extension. It's **RECOMMANDED** to use the Markdown syntax (`CHANGELOG.md`).

3. The changelog **MUST** follow [the "Keep a changelog" 1.0.0 specification](https://keepachangelog.com/en/1.0.0/).

4. The begining of the file **SHOULD** have a title `Changelog`
   ```markdown
   # Changelog
   ```

5. The header of the file **MUST** have a reference of this specification to provide the information of the following.
   ```markdown
   # Changelog
   This changelog follows [the "Changelog specification"](https://github.com/YaFou/Changelog-specification).
   ```

6. Each release **MUST** be informed in the changelog.
   ```markdown
   # Changelog
   ...

   ## 1.1.1
   ...

   ## 1.1.0
   ...

   ## 1.0.0
   ...
   ```

7. The releases **MUST** be sorted in order of released. The latest release **MUST** be in the top of the file after the header.

8. The release version **MAY** have a link to the release page.
   ```markdown
   ## [1.0.0](https://github.com/:owner/:repo/releases/tag/:version)
   ```

9. Each release **MUST** have a release date written in its section. This date **MUST** follow the [ISO standard](https://www.iso.org/iso-8601-date-and-time-format.html).
   ```markdown
   ## 1.0.0
   > 2020-06-25
   ```

10. Each release **MUST** log all changes since the previous release.

11. Each release **MUST** have no more than there six sections:
    - `Added`: new features;
    - `Changed`: comportement change, new arguments in a function...;
    - `Deprecated`: features which is not recommended to use;
    - `Removed`: removed features;
    - `Fixed`: fixed bugs;
    - `Security`: fixed security vulnerabilities;
    - and `Upgrade`: guide to upgrade the application or the library to this version. It includes how to solve depreciations.
    ```markdown
    ## 1.0.0

    ### Added
    ...

    ### Changed
    ...

    ### Deprecated
    ...

    ### Removed
    ...

    ### Fixed
    ...

    ### Security
    ...

    ### Upgrade
    ...
    ```

12. Release version **MUST** follow [the "Sementic Versionning" 2.0.0 specification](https://semver.org/spec/v2.0.0.html).

13. Each change entry **MUST** have the same format. It's **RECOMMANDED** to use the following format: `- <Change>.`.  
    The entry **MAY** have a scope to show a specific scope of the library or the application by example; if you want to use a scope, it's **RECOMMANDED** to use the following format: `- <Scope> - <Change>.` (or in Markdown format: `- **<Scope>** - <Change>.`). The changelog **SHOULD** have scope on each entry if there at least one entry with a scope.
    ```markdown
    ## 1.0.0

    ### Added
    - Thing 1
    - **Scope** - Thing 2.

    ### Changed
    - **Scope** - Thing 3.
    ```

14. Entries in the `Added` section **MUST** be used for new features (new classes, functions). It's **RECOMMMANDED** to use the following format: `<Feature name>`.
    These entries **SHOULD** have a explanation: `<Feature name>: <Explanation>`.
    ```markdown
    ### Added
    - Feature 1: Choose the good features
    - Feature 2: Write a good changelog
    ```

15. Entries in the `Changed` section **MUST** be used for changes (change of the arguments in a function, function behavior change). It's recommanded to use the following format: `<Feature name>: <Change>`.
    ```markdown
    ### Changed
    - `Function 1` function definition: from `function(arg1)` to `function(arg2)`.
    - `Function 2` function name: from `oldFunction()` to `newFunction`.
    ```

16. Entries in the `Deprecated` section **MUST** be used for features which are not recommanded to use. It's **RECOMMANDED** to use the following format: `<Feature name>: <Depreciation explanation>`. If the depreciation includes a solution, it's **RECOMMANDED** to use this format: `<Feature name>: <Depreciation explanation>; <Solution>`.
    ```markdown
    ### Deprecated
    - `oldFunction` function: Will be removed; use `newFunction` instead.
    - first argument of `function` function: Will not have a default value.
    ```

17. Entries in the `Removed` section **MUST** be used for removed features. It's **RECOMMANDED** to use the following format: `<Feature name>`. These entries **SHOULD** provide also a explanation, it's **RECOMMANDED** to use `<Feature name>: <Explanation>`.
    ```markdown
    ### Removed
    - Feature 1
    - Feature 2: Unused
    ```

18. Entries in the `Fixed` section **MUST** be used for fixed bugs. It's **RECOMMANDED** to use the following format: `<Bug explanation>`.
    ```markdown
    ### Fixed
    - Feature 1 did not return value.
    - Feature 2 did not work on ARM architecture.
    ```

19. Entries in the `Security` section **MUST** be used for fixed vulnerabilities. The vulnerability **SHOULD** have a CVE identifier. It's **RECOMMMANDED** to use the following format: `<CVE identifier>: <Explanation>`.
    ```markdown
    ### Security
    - CVE-0000-0000: User could execute a script.

20. Entries in the `Upgrade` section **MUST** be used to provide a guide to migrate from the previous release to the following release. It's **RECOMMANDED** to use the same format than the entries in the `Deprecated` section.
    If the change is a breaking change, it's **RECOMMANDED** to use the following format: `BREAKING CHANGE - <Feature name>: <Depreciation explanation>; <Solution>` (or in Markdown format: `**BREAKING CHANGE** - <Feature name>: <Depreciation explanation>; <Solution>`).
    ```markdown
    ### Upgrade
    - `oldFunction` function: Will be removed; use `newFunction` instead.
    - **BREAKING CHANGE** - first argument of `function` function: Not have default value.
