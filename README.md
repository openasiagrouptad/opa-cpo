# Journey to ONE · Session 01: Stop to Glue

Interactive e-learning course built from `CPO_SS1.pptx` (Openasia brand). Single self-contained `index.html`: all images and fonts are embedded, with no external requests.

## Structure (17 pages, ~30 min)

| Module | Pages | Required activities |
|---|---|---|
| 00 Khởi động | Chào mừng · Hành trình hôm nay | Explore the 3 stops on the journey map |
| 01 Compact Team | Ba quả bóng · Team của bạn là quả bóng nào? | Flip 3 cards · self-reflection poll · quiz |
| 02 Pit Stop | F1 · Pit Stop trong doanh nghiệp · Chu trình Tops & Flops · Thực hành · Kiểm tra | Pit-crew ordering game · Pit Stop / không phải sorting · explore the cycle · write own Tops/Flops/Actions (downloadable) · 3 quiz questions |
| 03 Team Glue | Goal · Frame · Trust · Tình huống · Know your team | Open all 3 tabs · match 6 scenarios · guess then reveal team data |
| 04 Team Glue Activation | One-page · 6 tuần 3S · Kiểm tra | Open both templates + quiz · open all 6 weeks · match 6 activities |
| 05 Tổng kết | Năng lượng lan truyền · Hoàn thành | Personal commitment |

**Gating:** the *Tiếp theo* button and later menu items stay locked until every activity on the current page is done. Quizzes give instant feedback and unlimited retries; no score is recorded. Progress is saved in the learner's browser (`localStorage`).

## Host on GitHub Pages

1. Repo **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**.
2. The course is then at `https://openasiagrouptad.github.io/opa-cpo/`.

## Embed in an LMS / website

```html
<iframe id="course" src="https://openasiagrouptad.github.io/opa-cpo/"
        title="Journey to ONE – Session 01" style="width:100%;height:100vh;border:0"
        allowfullscreen loading="lazy"></iframe>
<script>
  // Optional: auto-resize to the course height and listen for completion
  addEventListener('message', function (e) {
    var f = document.getElementById('course');
    if (!e.data || e.source !== f.contentWindow) return;
    if (e.data.type === 'course:height') f.style.height = e.data.height + 'px';
    if (e.data.type === 'course:complete') { /* e.g. mark complete in your LMS */ }
  });
</script>
```

`embed-example.html` in this repo is a working test page for the snippet above.
