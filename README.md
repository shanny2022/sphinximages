## 🐳 Docker Images for Sphinx

### 📦 Images
| Image | Description | Registries |
|--------|--------------|-------------|
| **`sphinx`** | Main Sphinx image | [Docker Hub](https://hub.docker.com/r/sphinxdoc/sphinx) · [GitHub Container Registry](https://github.com/sphinx-doc/sphinx/pkgs/container/sphinx) |
| **`sphinx-latexpdf`** | Image for LaTeX (for PDF output) | [Docker Hub](https://hub.docker.com/r/sphinxdoc/sphinx-latexpdf) · [GitHub Container Registry](https://github.com/sphinx-doc/sphinx/pkgs/container/sphinx-latexpdf) |

> **Note:**  
> The `sphinx-latexpdf` container includes **TeXLive**, making it quite large (over **2 GiB**).

---

### ⚙️ Usage

**Create a new Sphinx project:**
```bash
docker run -it --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-quickstart

Build HTML documentation:
docker run --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-build -M html . _build

Build EPUB documentation:
docker run --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-build -M epub . _build

💡 Tips
To install additional dependencies, use sphinxdoc/sphinx as a base
# Dockerfile
FROM sphinxdoc/sphinx
WORKDIR /docs
ADD requirements.txt /docs
RUN python3 -m pip install -r requirements.txt

🧪 Sphinx CI Docker Image
The Docker image used for testing Sphinx in CI pipelines is defined in the ci directory of this repository.

---

5. Scroll down and click **“Commit changes”** to save.  

---

### ✅ Result
Once saved, your GitHub README will automatically format it with headers, code blocks, tables, and colored syntax highlighting — exactly like professional open-source repos.  

Would you like me to show you what it will *look like visually* once rendered on GitHub (a preview mockup)?

