import os
from weasyprint import HTML, CSS

# 1. Define the Markdown / Technical content for the Readme
readme_html = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>README - Construction Website Template</title>
    <style>
        @page {
            size: A4;
            margin: 18mm 15mm 18mm 15mm;
            background-color: #fdfbf7;
            @bottom-right {
                content: "Page " counter(page) " of " counter(pages);
                font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
                font-size: 8pt;
                color: #7f8c8d;
            }
            @bottom-left {
                content: "Construction Website Repository Readme";
                font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
                font-size: 8pt;
                color: #7f8c8d;
            }
        }

        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            color: #2c3e50;
            line-height: 1.5;
            font-size: 10.5pt;
            margin: 0;
            padding: 0;
            background-color: #fdfbf7;
        }

        /* Banner Header */
        .header-banner {
            background-color: #2c3e50;
            color: #ffffff;
            margin: -18mm -15mm 20px -15mm;
            padding: 25px 15mm 20px 15mm;
            border-bottom: 5px solid #e67e22;
        }

        .header-banner h1 {
            font-size: 22pt;
            margin: 0 0 8px 0;
            color: #ffffff;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .header-banner p {
            font-size: 11pt;
            margin: 0;
            color: #bdc3c7;
        }

        .badge {
            display: inline-block;
            background-color: #e67e22;
            color: #ffffff;
            padding: 3px 8px;
            font-size: 8.5pt;
            font-weight: bold;
            border-radius: 3px;
            text-transform: uppercase;
            margin-top: 10px;
        }

        /* Section Headings */
        h2 {
            font-size: 14pt;
            color: #2c3e50;
            border-left: 4px solid #e67e22;
            padding-left: 10px;
            margin-top: 22px;
            margin-bottom: 12px;
            page-break-after: avoid;
        }

        h3 {
            font-size: 11.5pt;
            color: #d35400;
            margin-top: 16px;
            margin-bottom: 8px;
            page-break-after: avoid;
        }

        p {
            margin-top: 0;
            margin-bottom: 10px;
            text-align: justify;
        }

        /* Lists */
        ul {
            margin-top: 0;
            margin-bottom: 12px;
            padding-left: 20px;
        }

        li {
            margin-bottom: 4px;
        }

        /* Code & Preformatted Blocks */
        pre {
            background-color: #282c34;
            color: #abb2bf;
            padding: 12px 15px;
            border-radius: 5px;
            font-family: 'Courier New', Courier, monospace;
            font-size: 9pt;
            line-height: 1.4;
            overflow-x: auto;
            margin-top: 5px;
            margin-bottom: 15px;
            page-break-inside: avoid;
        }

        code {
            font-family: 'Courier New', Courier, monospace;
            background-color: #eaeded;
            color: #c0392b;
            padding: 2px 5px;
            border-radius: 3px;
            font-size: 9.5pt;
        }

        pre code {
            background-color: transparent;
            color: inherit;
            padding: 0;
        }

        /* Table Styling */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
            margin-bottom: 15px;
            font-size: 9.5pt;
            page-break-inside: avoid;
        }

        th, td {
            padding: 8px 10px;
            text-align: left;
            border-bottom: 1px solid #e2e8f0;
        }

        th {
            background-color: #34495e;
            color: #ffffff;
            font-weight: 600;
        }

        tr:nth-child(even) {
            background-color: #f2f4f4;
        }

        /* Callout Box */
        .callout {
            background-color: #fef5e7;
            border-left: 4px solid #f39c12;
            padding: 12px 15px;
            margin: 15px 0;
            border-radius: 0 4px 4px 0;
        }

        .callout p {
            margin: 0;
            color: #7e5109;
        }

        /* Directory Structure visual */
        .file-tree {
            background-color: #ffffff;
            border: 1px solid #d6dbdf;
            border-radius: 5px;
            padding: 12px 15px;
            font-family: 'Courier New', Courier, monospace;
            font-size: 9pt;
            color: #2c3e50;
            margin-bottom: 15px;
        }

        .file-tree div {
            white-space: pre;
            line-height: 1.3;
        }
    </style>
</head>
<body>

    <div class="header-banner">
        <h1>Construction Website Template</h1>
        <p>A responsive, modern web template designed for construction companies, engineering firms, and contractors.</p>
        <span class="badge">Open Source Repository</span>
    </div>

    <h2>📌 Overview</h2>
    <p>
        The <strong>Construction Website Template</strong> is a robust, lightweight frontend asset bundle customized specifically for the construction and architecture domain. It features modular CSS libraries, essential UI/UX animations, responsive slider tools, popup viewers, and iconography suites ready to build high-performance business websites.
    </p>

    <h2>📁 Repository Structure</h2>
    <p>The repository organizes frontend design components, CSS assets, interactive plugins, and iconography into structured subdirectories:</p>

    <div class="file-tree">
<div>construction_website/</div>
<div>├── css/</div>
<div>│   ├── bootstrap-grid.css           # Bootstrap v4 Flexbox Grid system</div>
<div>│   ├── bootstrap-grid.min.css       # Minified Bootstrap Grid system</div>
<div>│   ├── bootstrap-reboot.css         # Reset stylesheet (Normalize alternative)</div>
<div>│   ├── bootstrap-reboot.min.css     # Minified Reset stylesheet</div>
<div>│   ├── bootstrap.css                # Core Bootstrap v4 Framework styling</div>
<div>│   ├── bootstrap.min.css            # Production-ready Bootstrap Core CSS</div>
<div>│   ├── jquery.fancybox.min.css      # Fancybox lightboxes & overlays stylesheet</div>
<div>│   ├── magnific-popup.css           # Lightbox & responsive modal styling</div>
<div>│   ├── mystyle.css                  # Custom theme overrides & custom project styles</div>
<div>│   ├── owl.carousel.min.css         # Touch-enabled owl slider stylesheet</div>
<div>│   ├── owl.theme.default.css        # Owl carousel default navigation skin</div>
<div>│   └── swiper.min.css               # Modern mobile touch slider styles</div>
<div>└── font-awesome/</div>
<div>    ├── css/                         # FontAwesome main stylesheets & sourcemaps</div>
<div>    ├── fonts/                       # Webfont files (.eot, .svg, .ttf, .woff, .woff2)</div>
<div>    ├── bower.json                   # Package configuration for Bower</div>
<div>    ├── component.json               # Package configuration for Component</div>
<div>    └── composer.json                # PHP Composer configuration file</div>
    </div>

    <h2>⚙️ Included Libraries & Dependencies</h2>
    <table>
        <thead>
            <tr>
                <th>Library / Plugin</th>
                <th>Description / Purpose</th>
                <th>Key Asset Files</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>Bootstrap v4 Grid & Base</strong></td>
                <td>Provides responsive mobile-first layouts, flexbox grids, and CSS reset rules.</td>
                <td><code>bootstrap.min.css</code>, <code>bootstrap-grid.css</code></td>
            </tr>
            <tr>
                <td><strong>Font Awesome 4.7</strong></td>
                <td>Scalable vector icons and visual symbols tailored for Web UI components.</td>
                <td><code>font-awesome.min.css</code>, Font binaries</td>
            </tr>
            <tr>
                <td><strong>Swiper & Owl Carousel</strong></td>
                <td>Touch-friendly slideshows, portfolio galleries, and testimonial sliders.</td>
                <td><code>swiper.min.css</code>, <code>owl.carousel.min.css</code></td>
            </tr>
            <tr>
                <td><strong>Magnific Popup & Fancybox</strong></td>
                <td>Fast, responsive lightbox scripts for showcasing project photos and videos.</td>
                <td><code>magnific-popup.css</code>, <code>jquery.fancybox.min.css</code></td>
            </tr>
            <tr>
                <td><strong>Custom Styles</strong></td>
                <td>Project-specific color palettes, custom typography, hero banners, and footers.</td>
                <td><code>mystyle.css</code></td>
            </tr>
        </tbody>
    </table>

    <h2>🚀 Quick Start & Integration</h2>
    <p>To use this asset pack in your HTML project, include the required CSS files inside your document's <code>&lt;head&gt;</code> block:</p>

    <pre><code>&lt;!-- Core Reset & Grid --&gt;
&lt;link rel="stylesheet" href="construction_website/css/bootstrap.min.css"&gt;

&lt;!-- Plugins & Icons --&gt;
&lt;link rel="stylesheet" href="construction_website/font-awesome/css/font-awesome.min.css"&gt;
&lt;link rel="stylesheet" href="construction_website/css/owl.carousel.min.css"&gt;
&lt;link rel="stylesheet" href="construction_website/css/magnific-popup.css"&gt;

&lt;!-- Custom Theme Styling --&gt;
&lt;link rel="stylesheet" href="construction_website/css/mystyle.css"&gt;</code></pre>

    <div class="callout">
        <p><strong>Note:</strong> Ensure that the relative paths to the <code>font-awesome/fonts/</code> directory remain intact relative to the CSS file location to prevent font loading errors.</p>
    </div>

    <h2>🛠️ Customization & Development</h2>
    <ul>
        <li><strong>Custom Styling:</strong> Modify or extend <code>css/mystyle.css</code> to adjust the theme accent colors, font choices, or layout margins.</li>
        <li><strong>Web Fonts:</strong> Standard FontAwesome 4.7 fonts are pre-compiled and placed inside <code>font-awesome/fonts/</code>.</li>
        <li><strong>Source Maps:</strong> Sourcemap files (<code>.map</code>) are provided alongside key minified stylesheets to simplify browser debugging during development.</li>
    </ul>

    <h2>📄 License & Contributing</h2>
    <p>
        Contributions and pull requests are welcome. Feel free to open an issue or submit improvements to project templates, component stylesheets, or script integrations.
    </p>

</body>
</html>
"""

# Write HTML file
html_file_path = "README.html"
pdf_file_path = "README.pdf"

with open(html_file_path, "w", encoding="utf-8") as f:
    f.write(readme_html)

# Convert HTML to PDF using WeasyPrint
HTML(html_file_path).write_pdf(pdf_file_path)

print(f"Successfully generated {pdf_file_path}")
