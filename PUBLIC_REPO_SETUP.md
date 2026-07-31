# Update the public GitHub repository

Repository:

```text
Product-Data-Studio-Pro-Showcase
```

Visibility:

```text
Public
```

## Safe contents

This public repository may contain:

- README and public documentation
- Screenshots
- Privacy information
- System requirements
- Public changelog
- Gumroad product link

It must not contain:

- `app.py`
- `core/`
- `tests/`
- `installer/`
- `.exe`
- Gumroad customer ZIP
- full source code

## Push the 2.2.0 update

```powershell
cd "D:\python codes\myProjects\Product-Data-Studio-Pro-Showcase"

git status
git add .
git commit -m "Update showcase for version 2.2.0"
git push
```

After Gumroad is published, add the final product URL to:

```text
README.md
GUMROAD_URL.txt
GitHub repository Website field
```
