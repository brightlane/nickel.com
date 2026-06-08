# UniConverter Affiliate Site — build.py v1

A complete, production-ready affiliate marketing website for [Wondershare UniConverter](https://videoconverter.wondershare.com), built for GitHub Pages at:

**`https://brightlane.github.io/videoconverter/`**

---

## Quick Start

```bash
python3 build.py
```

Outputs 51 files into `videoconverter-site/` next to `build.py`. Zero dependencies — pure Python 3 stdlib only.

---

## Deployment

Your repo needs exactly three files:

```
videoconverter/               ← your GitHub repo name
├── build.py
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

**One-time GitHub setup:**
1. Go to `Settings → Pages → Source` → set to **GitHub Actions**
2. Push to `main` — workflow builds and deploys automatically in ~30 seconds

---

## Config (top of build.py)

```python
BASE      = Path(__file__).parent / "videoconverter-site"                        # Output folder
SITE_ROOT = "/videoconverter"                                                     # Must match repo name exactly
SITE_URL  = "https://brightlane.github.io/videoconverter"                        # Full canonical URL
AFF       = "https://www.linkconnector.com/ta.php?lc=007949048607004532&atid=videoconverterwebs"
YEAR      = date.today().year                                                     # Auto-updates on every build
```

⚠️ `SITE_ROOT` must exactly match your GitHub repo name or all internal links will 404.

---

## All 23 Pages

| Page | URL | Target Keywords | Schema |
|---|---|---|---|
| Homepage | `/` | best video converter, UniConverter download | SoftwareApp + Breadcrumb |
| Features | `/features/` | UniConverter features, GPU converter | SoftwareApp + Breadcrumb |
| Formats | `/formats/` | 1000+ formats, MP4 MKV AVI converter | SoftwareApp + Breadcrumb |
| How It Works | `/how-it-works/` | how to convert video, batch converter | SoftwareApp + HowTo |
| Pricing | `/pricing/` | UniConverter price, annual vs lifetime | SoftwareApp + FAQPage |
| Review | `/review/` | UniConverter review, is it worth it | SoftwareApp + Review |
| FAQ | `/faq/` | UniConverter free, Mac, 4K, DVD | SoftwareApp + FAQPage |
| Download | `/download/` | download UniConverter Windows Mac | SoftwareApp + Breadcrumb |
| Blog | `/blog/` | video conversion guides | SoftwareApp + Breadcrumb |
| Convert to MP4 | `/convert-mp4/` | convert MKV AVI MOV to MP4 | SoftwareApp + Article |
| Compress Video | `/compress-video/` | compress video, reduce file size | SoftwareApp + Article |
| MKV to MP4 | `/convert-mkv-mp4/` | MKV to MP4 converter | SoftwareApp + Article |
| MOV to MP4 | `/convert-mov-mp4/` | MOV to MP4, iPhone video converter | SoftwareApp + Article |
| DVD Burner | `/dvd-burner/` | burn video to DVD, DVD creator | SoftwareApp + Article |
| Alternatives | `/alternatives/` | best video converter alternatives | SoftwareApp + Breadcrumb |
| vs HandBrake | `/vs-handbrake/` | UniConverter vs HandBrake | SoftwareApp + Breadcrumb |
| vs VLC | `/vs-vlc/` | UniConverter vs VLC | SoftwareApp + Breadcrumb |
| vs Any Video Converter | `/vs-any-video-converter/` | video converter comparison | SoftwareApp + Breadcrumb |
| Global | `/global/` | video converter worldwide, 200+ countries | SoftwareApp + Breadcrumb |
| SEO Guide | `/guide/` | 60+ keyword tags + 4 keyword prose paragraphs | SoftwareApp + Breadcrumb |
| Privacy | `/privacy/` | — | — |
| Disclaimer | `/disclaimer/` | — | — |
| 404 | `/404.html` | — | — |

---

## 1000+ Keywords — 6 Layers

| Layer | Detail |
|---|---|
| `<meta name="keywords">` | 174 keyword phrases on every page covering every search angle |
| `<title>` + `<meta description>` | Unique per page, keyword-rich, under character limits |
| JSON-LD schema | SoftwareApplication + BreadcrumbList on every page. FAQPage on /faq/ and /pricing/. Review schema on /review/. HowTo schema on /how-it-works/. Article OG type on all guide pages |
| Format pills | 40+ format names rendered as visible chips on homepage and formats page |
| SEO prose | Keyword-rich paragraphs on /guide/ with natural density |
| SEO tag cloud | 60+ clickable keyword tags on /guide/ |

---

## SEO Files

| File | Purpose |
|---|---|
| `sitemap.xml` | 21 URLs with `lastmod`, priority and changefreq — submit to Google & Bing |
| `robots.txt` | Allows all crawlers, points to sitemap |
| `llms.txt` | Structured product summary for AI crawlers (Perplexity, ChatGPT, etc.) |
| `feed.xml` | RSS feed with 5 blog articles |
| `assets/favicon.svg` | Orange/dark branded SVG favicon |
| `.nojekyll` | Prevents GitHub Pages from running Jekyll |

**After deploying, submit sitemap:**
```
https://brightlane.github.io/videoconverter/sitemap.xml
```
→ Google Search Console → Add property → Submit sitemap
→ Bing Webmaster Tools → Import from Google

---

## Affiliate Link

Every CTA button uses:
```
https://www.linkconnector.com/ta.php?lc=007949048607004532&atid=videoconverterwebs
```

All affiliate links include `rel="noopener sponsored"` per Google's guidelines.
To update, change the `AFF` variable at the top of `build.py`.

---

## Product Facts (for content updates)

| Fact | Value |
|---|---|
| Product | Wondershare UniConverter (originally Video Converter Ultimate) |
| Current version | UniConverter 17 |
| Publisher | Wondershare Software Ltd (est. 2003, publicly listed) |
| Users | 15M+ worldwide |
| Formats | 1000+ video, audio and image formats |
| Max resolution | 8K, HDR, HDR10, Dolby Vision |
| Speed | Up to 90× real-time via GPU |
| GPU support | NVIDIA NVENC/CUDA, AMD VCE, Intel Quick Sync |
| Mac support | macOS 10.12+ including Apple Silicon M1/M2/M3 |
| Windows support | Windows 7, 8, 10, 11 (32 and 64-bit) |
| Pricing | Free trial · $39.99/yr Annual · $79.99 Perpetual · Commercial from $337.46 |
| Discounts | Up to 30% off available |
| Key features | Conversion, compression, editing, DVD/Blu-ray burning, screen recording, video downloading, AI Super Resolution, AI Frame Interpolation, AI Stabilization, AI Noise Reduction, watermark removal, batch processing |

---

## Design System

Dark tech aesthetic — orange/dark theme.

| Variable | Value | Usage |
|---|---|---|
| `--acc` | `#ff6b35` | Primary orange — CTAs, headings, links |
| `--acc2` | `#ff3d6b` | Pink/red — gradient accents |
| `--acc3` | `#ffbe0b` | Gold — highlights, code chips |
| `--blue` | `#2563eb` | Blue — secondary accents |
| `--cyan` | `#06b6d4` | Cyan — highlights |
| `--green` | `#10b981` | Green — checkmarks, success |
| `--bg` | `#050810` | Deep dark background |
| `--txt` | `#f0f4ff` | Primary text |
| `--muted` | `#8892a4` | Body / secondary text |

Fonts: **Syne** (headings) + **Space Grotesk** (body) + **JetBrains Mono** (code/format chips).

---

## File Structure After Build

```
videoconverter-site/
├── .nojekyll
├── index.html
├── 404.html
├── sitemap.xml
├── robots.txt
├── llms.txt
├── feed.xml
├── assets/
│   └── favicon.svg
├── features/index.html
├── formats/index.html
├── how-it-works/index.html
├── pricing/index.html
├── review/index.html
├── faq/index.html
├── download/index.html
├── blog/index.html
├── convert-mp4/index.html
├── compress-video/index.html
├── convert-mkv-mp4/index.html
├── convert-mov-mp4/index.html
├── dvd-burner/index.html
├── alternatives/index.html
├── vs-handbrake/index.html
├── vs-vlc/index.html
├── vs-any-video-converter/index.html
├── global/index.html
├── guide/index.html
├── privacy/index.html
└── disclaimer/index.html
```

---

## Tech Stack

| Layer | Choice |
|---|---|
| Generator | Python 3 stdlib only — zero dependencies |
| HTML/CSS/JS | Vanilla — no frameworks, instant load |
| Fonts | Google Fonts CDN (Syne + Space Grotesk + JetBrains Mono) |
| Hosting | GitHub Pages — free, HTTPS, global CDN |
| CI/CD | GitHub Actions — auto-deploy on every `git push` to `main` |

---

## License

Independent affiliate guide. UniConverter is a product of Wondershare Software Ltd.
This site is not affiliated with or endorsed by Wondershare.
