# Useful Commands

## List NPM Packages

```bash
npm list -g --depth 0
```

## List All User Installed Packages \(apt-mark\)

**How does it work:**

1. Get the list of manually installed packages. For aptitude, the additional `sed` strips out remaining whitespace at the end of the line.
2. Get the list of packages installed right after a fresh install.
3. Compare the files, only output the lines in file 1 that are not present in file 2.

```bash
comm -23 <(apt-mark showmanual | sort -u) <(gzip -dc /var/log/installer/initial-status.gz | sed -n 's/^Package: //p' | sort -u)
```

