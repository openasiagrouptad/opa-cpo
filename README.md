# Journey to ONE · Session 01: Stop to Glue

Interactive e-learning course built from `CPO_SS1.pptx` (Openasia brand). Single self-contained `index.html`: all images and fonts are embedded. The only external request is the YouTube video on the closing page, which loads when the learner presses play.

## Structure (17 pages, ~30 min)

| Module | Pages | Required activities |
|---|---|---|
| 00 Khởi động | Chào mừng · Hành trình hôm nay | Click the 5 hotspots on the interactive journey map |
| 01 Compact Team | Ba quả bóng · Team của bạn là quả bóng nào? | Flip 3 cards · self-reflection poll · quiz |
| 02 Pit Stop | F1 · Pit Stop trong doanh nghiệp · Chu trình Tops & Flops · Thực hành · Kiểm tra | Pit-crew ordering game · Pit Stop / không phải sorting · drive one lap of the Pit Stop loop (5 stations in order) · write own Tops/Flops/Actions (downloadable as a branded Word file) · 3 quiz questions |
| 03 Team Glue | Goal · Frame · Trust · Tình huống · Know your team | Open all 3 tabs · match 6 scenarios · guess then reveal team data |
| 04 Team Glue Activation | One-page · Hoạt động 3S thứ Hai · Kiểm tra | Open both templates · open all 5 activities (Colors of Us, Pass on the Moment, Glue Star, Finish the Lyrics, Who Am I?) · match 5 activities |
| 05 Tổng kết | Năng lượng lan truyền (Norway video) · Hoàn thành | Personal commitment |

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
