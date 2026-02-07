---
layout: page
title: Do Charging Stations Care about Electricity Rates?
description: "[Job Market Paper]"
authors: ""
date: 2025-03-19 -04:00
last_modified_at: 2025-10-12
img: assets/img/fig_sdid_event_dcfc_ports.png
importance: 1
category: Working Papers
related_publications: false
pdf: /assets/pdf/Jae-Yu Jung_dissertation_proposal_ch1_v2.pdf
abstract: 
  I study the effect of electricity prices on market entry of electric vehicle (EV) charging stations. I compile a novel dataset linking commercial electricity prices to charging stations across U.S. ZIP codes from 2015–2022. I convert complex pricing schedules into a standardized cost metric by constructing station-level load profiles from observed charging sessions and calculating monthly bills. Using synthetic control and local projection difference-in-differences designs, I estimate the effects of new price schedules for EV charging stations, aimed at reducing high demand charges. The results show that these schedules substantially lowered demand charges for DC fast charging stations by 50% and increased the entry of DC fast charging ports by 50% per zip code, underscoring the role of targeted rate design in accelerating EV infrastructure growth.
---

## Abstract

<div id="abstract-container" style="white-space: pre-line; min-height: 50px;">
  <span style="color:gray; font-size:0.9em;">Loading abstract...</span>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    // 1. 파일 경로 설정 (캐시 방지를 위해 시간 추가)
    // site.url과 site.baseurl을 조합하여 절대 경로를 만듭니다.
    const texUrl = "{{ site.url }}{{ site.baseurl }}/assets/pdf/abstract_do_ev_charging_stations.tex?v={{ site.time | date: '%s' }}";

    fetch(texUrl)
      .then(response => {
        if (!response.ok) {
            throw new Error("File not found (" + response.status + ")");
        }
        return response.text();
      })
      .then(text => {
        // 2. 주석(%) 제거 및 텍스트 청소 로직
        
        // (A) 줄 맨 앞의 % 주석 제거 (문단 전체 주석)
        let cleanText = text.replace(/^%.*/gm, '');

        // (B) 문장 중간의 % 주석 제거 (단, \%는 제외하고 지움)
        // 설명: 역슬래시(\)가 아닌 글자 뒤에 %가 오면, 그 %부터 줄 끝까지 삭제
        cleanText = cleanText.replace(/([^\\])%.*/g, '$1');

        // (C) LaTeX 이스케이프 문자 복구 (50\% -> 50%)
        cleanText = cleanText.replace(/\\%/g, '%');

        // (D) 3줄 이상 연속된 빈 줄은 2줄로 줄임 (보기 좋게)
        cleanText = cleanText.replace(/\n{3,}/g, '\n\n');

        // 3. 화면에 출력
        const container = document.getElementById('abstract-container');
        container.innerText = cleanText.trim();

        // 4. MathJax 수식 다시 렌더링 (가장 중요!)
        if (window.MathJax) {
            // MathJax 3.x (최신 al-folio)
            if (MathJax.typesetPromise) {
                MathJax.typesetPromise([container]);
            } 
            // MathJax 2.x (구형)
            else if (MathJax.Hub) {
                MathJax.Hub.Queue(["Typeset", MathJax.Hub, container]);
            }
        }
      })
      .catch(error => {
        console.error('Abstract Load Error:', error);
        document.getElementById('abstract-container').innerHTML = 
          "<span style='color:red;'>Abstract 로딩 실패.<br>경로 확인 필요: " + texUrl + "</span>";
      });
  });
</script>

<br>

<em>Updated March 2025</em>

<object data="/assets/pdf/Jae-Yu Jung_dissertation_proposal_ch1_v2.pdf" width="100%" height="1600%" type="application/pdf"> 
     <p>You can [get the PDF]({{ site.url }}/assets/pdf/Jae-Yu Jung_dissertation_proposal_ch1_v2.pdf) directly.</p> 
 </object>


{% comment %}

  
Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
{% endcomment %}
