# Distribution Area & Critical Value Tool

Single-file, embeddable web app to compute **areas (probabilities)** and **critical values (inverse CDF / quantiles)** for:

- **Normal** \(N(\mu,\sigma)\)
- **Gamma** \(\text{Gamma}(\alpha,\theta)\) (shape \(\alpha\), **scale** \(\theta\))
- **Chi-square** \(\chi^2(\nu)\) (df \(\nu\))
- **Exponential** \(\text{Exp}(\lambda)\) (**rate** \(\lambda\))

## What it does

### Area / Probability mode
Compute:

- \(P(X < x)\)
- \(P(X > x)\)
- \(P(a < X < b)\)

### Inverse / Critical Value mode
Solve for critical values:

- Given \(p\), find \(x\) such that \(P(X < x)=p\)  (lower-tail quantile)
- Given \(p\), find \(x\) such that \(P(X > x)=p\)  (upper-tail critical value)
- Given \(p\), find a **central equal-tail interval** \([L,U]\) such that  
  \(P(L < X < U)=p\) and each tail is \((1-p)/2\)

The inverse calculations use **automatic bracketing + bisection** (robust and stable for instructional use).

## Files

Recommended filename:

- `distribution_area_critical_tool.html`

(You can rename it, but keep the `.html` extension.)

## Run locally

1. Download or clone the repository.
2. Open the `.html` file in a browser.

No build step and no external libraries.

## Deploy on GitHub Pages (recommended for Canvas)

1. Push the repository to GitHub.
2. In your repo: **Settings → Pages**
3. Under **Build and deployment**, choose:
   - **Source:** Deploy from a branch  
   - **Branch:** `main` (or `master`) and `/root`
4. Save. GitHub will publish a URL like:

```
https://YOUR_USERNAME.github.io/YOUR_REPO/
```

## Embed in Canvas

Use an iframe that points to your published HTML file:

```html
<iframe
  src="https://YOUR_USERNAME.github.io/YOUR_REPO/distribution_area_critical_tool.html"
  width="100%"
  height="820"
  style="border:0;"
></iframe>
```

## Parameter conventions

- **Normal:** mean \(\mu\), standard deviation \(\sigma\)
- **Gamma:** shape \(\alpha\), **scale** \(\theta\) *(not rate)*
- **Chi-square:** df \(\nu\) (implemented as Gamma with \(\alpha=\nu/2\), \(\theta=2\))
- **Exponential:** **rate** \(\lambda\) (mean \(1/\lambda\))

## Notes / limitations

- Gamma / Chi-square / Exponential are supported on \(x \ge 0\) (CDF is 0 for \(x<0\)).
- Normal CDF uses an error-function approximation; accuracy is appropriate for typical classroom work.
- For extreme parameter values, sanity-check results (as with any numeric tool).

## Suggested citation (optional)

If students need to cite the tool:

> Distribution Area & Critical Value Tool. (Year). GitHub repository: <repo URL>

## License

Add a license that matches your intended use (MIT is a common choice for broad reuse).
---

# MIT License

Copyright (c) 2026 Angie Schirck

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
