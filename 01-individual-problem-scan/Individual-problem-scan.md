# 01 — Individual Problem Scan

## Scan rộng

| #  | Lăng kính          | Problem quan sát được                                                               | Ai đang đau?       | Dấu hiệu thật                |
| -- | ------------------ | ----------------------------------------------------------------------------------- | ------------------ | ---------------------------- |
| 1  | Lặp lại            | Sinh viên phải đọc nhiều source (Discord, PDF, GitHub) để biết chính xác cần nộp gì | Sinh viên học tech | Hỏi lại nhiều trước deadline |
| 2  | Lặp lại            | Team member mới setup Git/GitHub workflow rất lâu                                   | Member mới         | Onboarding 30-60 phút        |
| 3  | Tốn thời gian      | Viết weekly update từ GitHub + Discord + task board                                 | Team lead          | 45-60 phút/tuần              |
| 4  | Tốn thời gian      | Search decision cũ trong Discord thread rất khó                                     | Team project       | 10-15 phút/lần tìm           |
| 5  | AI có thể tốt hơn  | Requirement/task bị rải rác nhiều nơi                                               | Sinh viên/team     | Miss format submit           |
| 6  | AI có thể tốt hơn  | Review PRD dài trước khi comment mất nhiều thời gian                                | PM reviewer        | 30-45 phút/document          |
| 7  | Pain từ người khác | Designer phải hỏi lại vì spec từ PM chưa rõ                                         | Designer, PM       | 2-3 lần hỏi/spec             |
| 8  | Pain từ người khác | Meeting xong không ai nhớ action items                                              | Team member        | Task bị quên                 |
| 9  | Tốn thời gian      | Tìm function/file liên quan trong codebase lớn                                      | Developer          | Search lâu                   |
| 10 | Lặp lại            | Viết meeting notes sau mỗi buổi họp                                                 | PM/team lead       | 20-30 phút/buổi              |

---

# Top 3 Problems

| Rank | Problem                           | Vì sao chọn                          | Điều còn chưa chắc                           |
| ---- | --------------------------------- | ------------------------------------ | -------------------------------------------- |
| 1    | Multi-source assignment confusion | Pain thật, workflow rõ, dễ đo metric | AI extract requirement có đủ chính xác không |
| 2    | Weekly report generation          | Có before/after rõ, AI fit tốt       | Data source có đồng nhất không               |
| 3    | Discord decision search           | Team nào cũng gặp                    | Search quality khó đo                        |

---

# Problem Card #1 — Multi-source Assignment Confusion

## Problem

Sinh viên phải đọc nhiều nguồn rời rạc (Discord, Notion, PDF, GitHub) để biết chính xác cần làm gì trước deadline.

---

## Actor

* Sinh viên học tech/project-based course
* Team member mới tham gia project/lab
* Người chưa quen workflow của lớp/team

---

## Thời điểm / bối cảnh

* Trước deadline lab/project
* Khi assignment bị update qua Discord thread
* Khi requirement nằm ở nhiều source khác nhau

---

## Current Workflow

```text
CURRENT STATE — ~45 phút

[Đọc PDF lab]
→ [Đọc Discord thread]
→ [Check pinned messages]
→ [Mở GitHub repo]
→ [Hỏi bạn bè/TA]
→ [Tự tổng hợp requirement]  <-- bottleneck
→ [Bắt đầu làm bài]

Pain:
- Requirement nằm rải rác
- Dễ miss update mới
- Không biết source nào là final
```

---

## Bottleneck

### Bước nghẽn nhất

Tự tổng hợp requirement từ nhiều nguồn khác nhau.

### Pain cụ thể

* Requirement không nằm cùng một nơi
* Discord thường có update mới nhưng khó tìm lại
* Sinh viên phải tự verify requirement
* Dễ submit sai format hoặc thiếu file

---

## Impact

* Sinh viên mất nhiều thời gian chỉ để hiểu cần làm gì
* Hỏi lặp lại nhiều trong Discord trước deadline
* TA/mentor phải trả lời cùng một dạng câu hỏi
* Member mới khó onboarding vào workflow lớp/project
* Một số bài submit thiếu requirement hoặc sai format

---

## Success Metric

| Metric                | Current      | Expected     |
| --------------------- | ------------ | ------------ |
| Time hiểu assignment  | ~45 phút     | dưới 10 phút |
| Số lần hỏi lại        | 5 lần/team   | dưới 1 lần   |
| Miss requirement      | Thỉnh thoảng | hiếm         |
| Onboarding member mới | 30+ phút     | dưới 10 phút |

---

## Future Workflow

```text
FUTURE STATE — ~8 phút

[Upload PDF + Discord + GitHub]
→ [Extract requirements]
→ [Merge duplicated info]
→ [Generate checklist + summary]
→ [Student review]
→ [Start assignment]

Human boundary:
- Student verify final requirement trước submit

Fallback:
- AI unsure → show source reference
```

---

## Non-AI Alternative

* Gom toàn bộ requirement vào một source duy nhất
* Standardized assignment template
* Mentor update requirement rõ hơn
* FAQ cố định cho từng lab

---

## AI Hypothesis

AI có thể:

* đọc nhiều nguồn cùng lúc,
* extract requirement,
* detect duplicated/conflicting info,
* generate checklist dễ hiểu,
* highlight update quan trọng.

---

## Boundary

AI không tự quyết định requirement cuối cùng hoặc override instruction từ mentor/TA.

Sinh viên vẫn phải:

* review checklist,
* verify submission format,
* kiểm tra requirement quan trọng.

---

## Quick Gut

* [ ] No AI
* [ ] Rule
* [x] Workflow
* [ ] Agent
* [ ] Chưa biết

---

## Vì sao tôi chọn bài này

* Pain thật và dễ gặp
* Workflow rõ
* Có bottleneck cụ thể
* Impact đo được
* AI fit tự nhiên nhưng chưa cần Agent

---

## Điều còn chưa chắc

* AI extract requirement có đủ chính xác không
* Requirement conflict giữa nhiều source xử lý thế nào
* Discord context có đủ clean để summarize không

````

:::writing{variant="document" id="39417"}


# Problem Card #2 — Weekly Report Generation

## Problem

PM/team lead mất nhiều thời gian tổng hợp progress từ Jira, Slack và GitHub để viết weekly report.

---

## Actor

- PM
- Team lead
- Engineering manager

---

## Current Workflow

```text
CURRENT STATE — ~60 phút

[Export Jira progress]
→ [Đọc Slack update]
→ [Check GitHub commits/PR]
→ [Manual summary]
→ [Viết narrative] <-- bottleneck
→ [Send report]

Pain:
- Data nằm nhiều source
- Narrative viết thủ công
- Dễ miss blocker/update
````

---

## Bottleneck

### Bước nghẽn nhất

Viết narrative tổng hợp từ nhiều nguồn khác nhau.

### Pain cụ thể

* Progress update không đồng nhất format
* Phải tự nối context giữa task/chat/code
* Viết report mất nhiều thời gian mỗi tuần

---

## Impact

* PM/team lead mất 45-60 phút mỗi tuần
* Report quality không đồng đều
* Dễ miss blocker hoặc dependency
* Team thiếu visibility về tiến độ

---

## Success Metric

| Metric                 | Current      | Expected     |
| ---------------------- | ------------ | ------------ |
| Time viết report       | ~60 phút     | dưới 10 phút |
| Missing blocker/update | Thỉnh thoảng | hiếm         |
| Manual summary steps   | 4-5 bước     | 1-2 bước     |

---

## Future Workflow

```text
FUTURE STATE — ~10 phút

[Pull Jira + Slack + GitHub]
→ [AI summarize progress]
→ [AI draft narrative]
→ [PM review/edit]
→ [Send report]

Human boundary:
- PM review final narrative

Fallback:
- AI draft tệ → PM rewrite section đó
```

---

## Non-AI Alternative

* Standardized update template
* Team update progress theo format cố định
* Weekly checklist/report structure

---

## AI Hypothesis

AI có thể:

* summarize progress,
* group updates,
* detect blocker,
* generate readable narrative.

---

## Quick Gut

* [ ] Rule
* [x] Workflow
* [ ] Agent

````

:::writing{variant="document" id="51742"}

# Problem Card #3 — Discord Decision Search

## Problem 

Team member khó tìm lại decision cũ trong Discord/thread dài khi tiếp tục công việc.

---

## Actor

- Developer
- PM
- Designer
- Team member mới

---

## Current Workflow

```text
CURRENT STATE — ~15 phút/lần tìm

[Nhớ keyword mơ hồ]
→ [Search Discord]
→ [Mở nhiều thread]
→ [Đọc lại context]
→ [Hỏi lại team]
→ [Tìm được decision]

Pain:
- Search Discord kém
- Context bị phân mảnh
- Decision không centralized
````

---

## Bottleneck

### Bước nghẽn nhất

Search và reconstruct context từ thread cũ.

### Pain cụ thể

* Không nhớ đúng keyword
* Decision nằm giữa nhiều thread
* Team phải trả lời lại cùng context

---

## Impact

* Mất 10-15 phút mỗi lần tìm
* Team bị interrupt bởi câu hỏi lặp lại
* Decision dễ bị hiểu sai
* Member mới khó hiểu historical context

---

## Success Metric

| Metric               | Current    | Expected     |
| -------------------- | ---------- | ------------ |
| Time search decision | 10-15 phút | dưới 2 phút  |
| Số lần hỏi lại       | nhiều      | giảm đáng kể |
| Context missing      | thường gặp | hiếm         |

---

## Future Workflow

```text
FUTURE STATE — ~2 phút

[Input vague question]
→ [Search semantic context]
→ [Find related thread]
→ [Summarize decision]
→ [Show source reference]

Human boundary:
- User verify final context

Fallback:
- Không chắc → show raw thread
```

---

## Non-AI Alternative

* Better documentation
* Decision log riêng
* Structured meeting notes

---

## AI Hypothesis

AI có thể:

* semantic search,
* summarize thread,
* reconstruct context,
* link related discussion.

---

## Quick Gut

* [ ] Rule
* [x] Workflow
* [ ] Agent

```
```

