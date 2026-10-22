# AGENTS.md

## Project type

Static HTML/CSS course exercises (《高级网页设计》). No build step, no package manager, no tests, no linter. Files are opened directly in a browser.

## Entry point

`index.html` — course index page linking to all exercise files.

## Structure

- Numbered exercise files (`1.html` … `12-1.html`) — each is a self-contained page
- `css.css` — shared stylesheet referenced by exercise pages
- `img/` — image assets shared by exercise pages (`1.jpg` … `4.jpg`)
- `四级项目/` — 四级项目「网页元素设计」交付目录，可独立打包提交：
  - `9-1 户外自然生态科普.html` — 项目主页面（引用 `./img/*.png`）
  - `img/` — 主页面引用的 7 张图片
  - `report_ref1~3.png` / `report_my1~3.png` / `report_test.png` — 报告用原型、实现、测试截图
  - `高级网页设计I  网页元素设计 项目报告.doc` — 报告模板
  - `高级网页设计I 实验指导书 网页元素设计.docx` — 实验指导书

## Conventions

- All pages use `lang="zh-CN"` and UTF-8
- Some filenames contain Chinese characters — handle encoding carefully on Windows
- No framework or preprocessor; plain HTML + CSS only

## Naming Rules

- All CSS class names, id names, and JS variables **must** start with `Fu_` (e.g., `Fu_container`, `Fu_title`, `Fu_count`)

## Index Linking Rule

- After creating any new HTML exercise file, **add a card link** to `index.html` in the `.grid` section (use the existing card markup pattern with URL-encoded href for filenames containing spaces or Chinese characters)

## Prompt Logging

- Before executing any user request, **append** the prompt to `Fu_prompt.md` (do not overwrite)
- Each log entry must include:
  - Timestamp in `yyyy-mm-dd-hh-mm` format
  - Model used
  - Full prompt content
