# คู่มือการใช้งาน Spec Kit ฉบับใช้งานจริง (v2) 🇹🇭

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Language: Thai](https://img.shields.io/badge/Language-%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2%E0%B9%84%E0%B8%97%E0%B8%A2-blue.svg)](#)
[![Spec Kit](https://img.shields.io/badge/GitHub-Spec--Kit-blueviolet.svg)](https://github.com/github/spec-kit)
[![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-brightgreen.svg)](https://www.python.org/)
[![Read Online Guide](https://img.shields.io/badge/Docs-Read%20Online-orange.svg)](https://chanchai9666.github.io/speckit-manual/)

> **Unofficial Community Guide & Interactive Manual**  
> คู่มือภาษาไทยเพื่อการศึกษาและใช้งานจริง เรียบเรียงและสังเคราะห์ขึ้นจากโครงการโอเพนซอร์ส [github/spec-kit](https://github.com/github/spec-kit) ภายใต้สัญญาอนุญาต MIT License

---

## 🌐 เข้าชมคู่มือฉบับเต็มออนไลน์ (Online Guide)

👉 **[คลิกที่นี่เพื่อเปิดอ่านคู่มือ (https://chanchai9666.github.io/speckit-manual/)](https://chanchai9666.github.io/speckit-manual/)**

หน้าเว็บออกแบบให้รองรับทั้ง Desktop, Tablet และ Mobile เต็มรูปแบบ มีทั้ง Dark Mode / Light Mode, สารบัญนำทางแบบ Slide-in Drawer, ปุ่มคัดลอกคำสั่ง และช่องค้นหา Interactive Cheat Sheet แบบเรียลไทม์

---

## 📖 สรุปเนื้อหาในคู่มือ (Table of Contents)

คู่มือนี้แบ่งเนื้อหาออกเป็น 5 เฟส ครอบคลุมการทำงานตั้งแต่เริ่มต้นจนถึงระดับผู้เชี่ยวชาญ:

### 1. เริ่มต้น & ปูพื้นฐาน (Getting Started)
- สรุปภาพรวมและแนวคิด **Spec-Driven Development (SDD)** — เปลี่ยน Specification ให้เป็นพิมพ์เขียวที่ตรวจสอบได้
- ข้อกำหนดของระบบและการติดตั้งผ่าน `uv` หรือ `pipx`
- ความแตกต่างระหว่าง **CLI Commands (Terminal)** กับ **Agent Commands (Chat / Skill)**
- Quick Start: เริ่มต้นโปรเจคใหม่ใน 4 ขั้นตอน

### 2. วงจรการทำงานหลัก & การสั่งงาน (Core SDD & Prompting)
- ลำดับขั้นตอนมาตรฐาน: `constitution` → `specify` → `clarify` → `plan` → `checklist` → `tasks` → `analyze` → `implement` → `converge`
- เจาะลึกคำสั่ง Agent แต่ละขั้นตอน พร้อมตัวอย่างการสั่งงาน
- เคล็ดลับการเขียน Prompt เปรียบเทียบสิ่งที่ควรทำ (Do) และควรเลี่ยง (Don't)
- แนวทางปฏิบัติที่ดี (Best Practices)

### 3. สถานการณ์ใช้งานจริง & ตัวอย่าง (Real-world Scenarios)
- **Greenfield (0-to-1):** สร้างระบบใหม่จากศูนย์
- **Brownfield:** นำมาประยุกต์ใช้กับโปรเจคเดิมที่มีโค้ดอยู่แล้ว
- รูปแบบการดูแลรักษาสเปก: Flow-Forward, Living Spec, Flow-Back
- **Bug Fixing Extension:** วินิจฉัย (`assess`), แก้ไข (`fix`), และทดสอบยืนยันผล (`test` -> `verified`)
- **Idea Assessment Extension:** ประเมินความคุ้มค่าก่อนลงทุนลงแรง (`intake` → `research` → `define` → `shape` → `decide`)
- รวม 6 กรณีศึกษาพร้อมชุดคำสั่งที่นำไปปรับใช้ได้ทันที

### 4. การตั้งค่า & จัดการขั้นสูง (Configuration & Advanced)
- รวมคำสั่ง CLI ที่ใช้บ่อย และพารามิเตอร์สำคัญของ `specify init`
- การเชื่อมต่อและสลับ AI Agent: GitHub Copilot, Claude Code, Opencode, Codex, Qwen, Antigravity ฯลฯ
- การใช้งาน Extensions, Presets, Workflows และ Bundles
- Git Extension & Branching Automation
- แผนที่โครงสร้างโฟลเดอร์ `.specify/`
- ตัวแปรสภาพแวดล้อม (Environment Variables) และแนวทางการอัปเกรดอย่างปลอดภัย

### 5. อ้างอิง & แก้ปัญหา (Reference & Quick Lookup)
- การแก้ปัญหาที่พบบ่อย (Troubleshooting)
- **Interactive Cheat Sheet:** ค้นหาแนวทางและชุดคำสั่งตามสถานการณ์แบบทันที

---

## ⚡ เริ่มต้นอย่างรวดเร็ว (Quick Reference)

```bash
# 1. ติดตั้ง CLI ด้วย uv
uv tool install specify-cli

# 2. เริ่มต้นโปรเจคใหม่ (เช่น ใช้งานร่วมกับ GitHub Copilot)
specify init my-project --integration copilot
cd my-project
```

จากนั้นสั่งงานผ่านหน้าแชทของ AI Coding Agent:
```text
/speckit-constitution   # กำหนดมาตรฐานโปรเจค
/speckit-specify        # ระบุฟีเจอร์ที่ต้องการ (What & Why)
/speckit-plan           # วางแผนเทคนิคและสถาปัตยกรรม (How & Tech Stack)
/speckit-tasks          # แตกงานย่อยและจัดลำดับ
/speckit-implement      # ลงมือเขียนโค้ดตามแผน
/speckit-converge       # ตรวจสอบความครบถ้วนสมบูรณ์
```

---

## ⚖️ สัญญาอนุญาตและข้อชี้แจง (License & Disclaimer)

- **MIT License**: เผยแพร่ภายใต้สัญญาอนุญาตแบบโอเพนซอร์ส MIT License เช่นเดียวกับโครงการต้นฉบับ [github/spec-kit](https://github.com/github/spec-kit)
- **Community Disclaimer**: คู่มือฉบับภาษาไทยนี้จัดทำขึ้นโดยชุมชนเพื่อวัตถุประสงค์ในการศึกษาและการถ่ายทอดความรู้ (Unofficial Community Guide) มิได้มีความเกี่ยวข้อง ได้รับการสนับสนุน หรือได้รับการรับรองอย่างเป็นทางการจาก GitHub, Inc. หรือ Microsoft Corporation แต่อย่างใด
- เครื่องหมายการค้า GitHub®, GitHub Copilot® และ Octocat เป็นเครื่องหมายการค้าของ GitHub, Inc. / Microsoft Corporation
