# Codex 文献下载回退

按篇处理。沿用 medlit 已核验的题名、DOI、PMID、期刊和年份，记录已经尝试的入口。取得并核验 PDF 后停止该篇的全文回退。补充材料仍从出版商的附件入口单独获取。

## 有 DOI 或 arXiv ID

读取 [fetch-paper](upstream/fetch-paper/SKILL.md)。用系统 Python 调用其原始解析器，每次传一个标识符，使用 `--json`。脚本位于 `upstream/fetch-paper/scripts/resolve_oa.py`，从任务工作目录运行，避免向技能目录写缓存。已配置 `UNPAYWALL_EMAIL` 或 `CONTACT_EMAIL` 时用它查询 Unpaywall。缺少地址时继续适用的公开入口，若仅此步骤缺配置且仍需要 Unpaywall，再说明缺项。当前上游解析器即使收到 arXiv ID 也要求联系邮箱。缺配置时，已核验的 arXiv ID 可直接通过 arXiv 官方落地页查看和下载。根据返回的 PDF 或落地页继续 medlit 的下载和核验。接受稿和预印本注明版本。仅有 HTML 时记录可阅读全文，并继续查找 PDF。

## 有 Web of Science 记录或学校能访问 WoS

读取 [wos-download](https://github.com/cookjohn/wos-skills/blob/268b1398e81205010fcc0520f7087675c2de3b5c/skills/wos-download/SKILL.md)。将上游浏览器指令映射为当前已连接的 Codex 浏览器操作。打开已有 WoS 记录，或在可访问的 WoS 界面按 DOI 或完整题名检索，核对记录后使用全文链接进入出版商页面，通过可见的 PDF 控件保存。由用户在同一窗口完成必要的学校登录或人机验证，随后从当前页面继续。复用已打开的出版商页面，避免重复访问相同入口。

## 需要在浏览器继续或接收用户已下载的 PDF

参考 [paper-to-zotero](https://github.com/uxfion/skills/blob/b18090501e75af30e20acfb293c527fe9498da56/paper-to-zotero/SKILL.md) 的下载接收流程。保留该篇待处理记录和已核验的出版商链接。若浏览器需要人工验证，允许用户接手，期间先处理清单中其他可获取的文献。用户完成验证后，继续用页面 PDF 控件下载。用户已经下载时，接收浏览器返回的文件，或查看用户提供的下载目录或文件路径。核对 PDF 可读性与 DOI 或题名，记录原始来源和可访问位置。仅在用户同时要求导入 Zotero 时才使用该技能的导入流程，。本地已有该技能时，按上游说明检查所需的 Zotero 连接和依赖。

每篇汇报实际取得的文件及版本。仍缺全文时说明可访问的链接、遇到的具体障碍及用户需要完成的步骤。
