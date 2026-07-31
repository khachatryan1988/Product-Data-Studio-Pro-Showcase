# Where to copy the architecture files

## Private repository

Copy:

```text
PRIVATE_ARCHITECTURE.md
```

to:

```text
D:\python codes\myProjects\Product-Data-Studio-Pro\ARCHITECTURE.md
```

Then:

```powershell
git add ARCHITECTURE.md
git commit -m "Add project architecture documentation"
git push
```

## Public repository

Copy:

```text
PUBLIC_ARCHITECTURE.md
```

to:

```text
D:\python codes\myProjects\Product-Data-Studio-Pro-Showcase\ARCHITECTURE.md
```

Add this line to the public README, for example after the feature section:

```markdown
## Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for a high-level product architecture overview.
```

Then:

```powershell
git add ARCHITECTURE.md README.md
git commit -m "Add public architecture overview"
git push
```
