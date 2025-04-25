# Manim Animation Project

This project demonstrates how to create animations using [Manim](https://docs.manim.community/), a powerful mathematical animation engine.

## 🎬 Creating an Animation Video Locally

To render a scene:

1. Define your animation in a Python file (e.g., `test.py`).  
   For example:
   ```python
   class SquareToCircle(Scene):
       def construct(self):
           square = Square()
           circle = Circle()
           self.play(Transform(square, circle))
   ```

2. Run the following command in your terminal (after setting up the project environment):
   ```bash
   manim -ql test.py SquareToCircle
   ```
   - `test.py` is the filename.
   - `SquareToCircle` is the name of the scene class.
   - `-ql` stands for "quick low quality" — good for fast previews.

3. The rendered video will be saved in the `media/videos` directory (this folder is `.gitignore`d).

---

## ⚙️ Project Setup


### 📥 Install and Upgrade `pip`

Before setting up the environment, make sure you have the latest version of `pip`:

```bash
python3 -m ensurepip --upgrade
python3 -m pip install --upgrade pip
```

This ensures that your package installer is up to date and avoids common compatibility issues.

---

Use [`uv`](https://github.com/astral-sh/uv) for managing the Python environment and dependencies. Here’s how to get started:

### 1. Install `uv`
```bash
pip install uv
```

> 🛠️ Tip: Use `which uv` to verify the `uv` binary location (e.g., `/Users/ishubansal/.local/bin/uv`)

### 2. Create a Virtual Environment
```bash
uv venv
```

### 3. Activate the Virtual Environment
```bash
source .venv/bin/activate
```

### 4. Sync Dependencies
```bash
uv sync
```
This will install all dependencies listed in the `pyproject.toml` or `uv.lock`.

### 5. 📦 Adding New Dependencies (During Development)

When developing and you need to install a new package, **always use `uv`** to ensure consistency across environments:

```bash
uv add <package_name>
```

This will:

- Install the package in your virtual environment.
- Automatically update the lock files (e.g., `uv.lock`, `pyproject.toml`) so your changes are tracked.
- Ensure that other collaborators can sync the same environment by simply running:

```bash
uv sync
```

> ✅ **Tip:** Avoid using `pip install` directly — using `uv add` keeps your dependencies clean and reproducible.

---

## 📁 Folder Structure (Partial)

```
.
├── test.py               # Example scene
├── .gitignore            # git ignore file
├── media/                # Rendered videos (gitignored)
├── .venv/                # Virtual environment
├── pyproject.toml        # Project dependencies (if using Poetry or uv-compatible format)
└── README.md             # You're here!
```

---

## 🧪 Next Steps

- Try modifying the animation or adding new scenes.
- Explore Manim's [documentation](https://docs.manim.community/en/stable/index.html) for more features.
- Add tests or CI if this grows into a larger project.
