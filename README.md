# easy-share

A public drop box for documents and patch files, so they can be viewed or downloaded from any machine.

## Add files

From a local clone (on any machine where `gh auth login` has been run once):

```bash
cp ~/somewhere/fix.patch .
git add -A && git commit -m "Add fix.patch" && git push
```

## Get files on another machine

- **Browse:** https://github.com/GuruSrikanth10/easy-share
- **Download one file** (no git needed):

  ```bash
  curl -LO https://raw.githubusercontent.com/GuruSrikanth10/easy-share/main/fix.patch
  ```

  In Windows PowerShell, type `curl.exe` instead of `curl`.
- **Apply a patch straight from the repo:**

  ```bash
  curl -sL https://raw.githubusercontent.com/GuruSrikanth10/easy-share/main/fix.patch | git apply
  ```

  For `git format-patch` output, use `git am` instead of `git apply` to keep the commit message.
- **Get everything:** `git clone https://github.com/GuruSrikanth10/easy-share.git` (then `git pull` for updates), or download the [ZIP](https://github.com/GuruSrikanth10/easy-share/archive/refs/heads/main.zip).

## Notes

- Raw download links can lag a just-pushed change by up to ~5 minutes (GitHub caching).
- GitHub rejects files over 100 MB.
- `.gitattributes` keeps `*.patch` and `*.diff` files byte-for-byte, so they apply cleanly on Windows too.
