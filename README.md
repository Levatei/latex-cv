# CV — LaTeX Template

> A clean, customized LaTeX CV built on the [AltaCV](https://github.com/liantze/AltaCV) template by LianTze Lim.
> Supports English and Russian, versioning watermarks, and custom company icons.

---

## 📁 Repository Structure

| Path | Description |
|---|---|
| `images/` | Icons and images used in the CV |
| `pdf/` | Compiled PDF output files |
| `build.sh` | Automated build script |
| `CMakeLists.txt` | CMake configuration |
| `custom-altacv.cls` | Customized AltaCV class file |
| `cv-en.tex` | Main source file — English version |
| `cv-ru.tex` | Main source file — Russian version |
| `preamble.tex` | Global settings: colors, fonts, icons |

---

## 🔨 How to Build

### Option 1 — Build Script (recommended)

**Prerequisites:** `texlive`, `LuaTeX`, `CMake ≥ 3.12`, `bash`

```bash
# View usage
./build.sh

# Build English version (no bibliography)
bash build.sh cv-en

# Build Russian version (no bibliography)
bash build.sh cv-ru ru 0

# Build English version with bibliography
bash build.sh cv-en en 1
```

The compiled PDF will appear in the `pdf/` directory. Intermediate files are cleaned up automatically.

---

### Option 2 — Overleaf (I use this one.)

1. Go to [overleaf.com](https://www.overleaf.com) and create a new project.
2. Upload all files from this repository.
3. Open `cv-en.tex` or `cv-ru.tex`.
4. Click **Recompile** → **Download PDF**.

---

### Option 3 — TeXstudio

1. Install [TeXstudio](https://www.texstudio.org).
2. Clone this repository:
   ```bash
   git clone https://github.com/temikfart/temikfart.git
   ```
3. Open `cv-en.tex` in TeXstudio and press **F5** to compile.

---

## ✏️ How to Edit

Open `cv-en.tex` (or `cv-ru.tex`) and replace the personal data with your own. The file is organized into standard sections: personal info, education, experience, and skills.

---

## ✨ Custom Features

### CV Version Watermark

The `\cvversion` command adds a watermark with the current CV version:

```latex
% Version format: v.YYYY.MM.DD-<language>-<type>
\cvversion{v.2024.01.15-en-full}
```

To hide the watermark, comment out the `draftwatermark` package in `preamble.tex`.

---

### Colored Job Entry

Use `\cvjob` instead of `\cvevent` to display a clickable, colored link to the company:

```latex
\cvjob{Assistant Engineer \cvtag{C++}}
      {\huawei Huawei -- System Engineering Lab}
      {Summer Internship 2022}
      {Huawei RRI}
      {https://career.huawei.ru/rri/en/}
```

---

### Custom Company Icons

Add your own icon by placing a `.png` or `.pdf` file in the `images/` folder and defining a command in `preamble.tex`:

```latex
\newcommand*\huawei{
  \raisebox{-0.15\totalheight}
    {\includegraphics[width=15pt]{images/huawei}}
  \hspace{.5ex}
}
```

Adjust `-0.15` to control vertical alignment, `width` for size, and `.5ex` for spacing.

---

### Font Awesome Icons

Icons are available via the [Font Awesome](https://fontawesome.com) package. Use them anywhere in your CV for a polished look.

---

## 📄 License

Free to use and modify under the [LaTeX Project Public License (LPPL)](https://www.latex-project.org/lppl/).
Please credit the original template author **LianTze Lim** if you share or redistribute your version.

---

## 🙏 Credits

- Original template: [AltaCV by LianTze Lim](https://github.com/liantze/AltaCV)
