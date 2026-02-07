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
---

## Abstract

<script id="raw-latex" type="text/template">
{% include_relative abstract_do_ev_charging_stations.tex %}
</script>

<div id="abstract-content" style="white-space: pre-line;">
  <span style="color:gray; font-size:0.9em;">Loading abstract... (If this persists, check the file name)</span>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    try {
      // 1. 템플릿 안의 텍스트 원본 가져오기
      var rawElement = document.getElementById('raw-latex');
      if (!rawElement) throw new Error("Source element not found");
      
      var rawText = rawElement.innerHTML;

      // 2. 내용이 비어있는지 확인 (include_relative 실패 시 빈 값일 수 있음)
      if (!rawText.trim()) {
        throw new Error("File content is empty or not found.");
      }

      // 3. 주석(%) 제거 및 LaTeX 청소
      // (A) 줄의 맨 앞에 있는 % 주석 제거
      let cleanText = rawText.replace(/^%.*/gm, ''); 
      // (B) 문장 중간에 있는 % 주석 제거 (단, \%는 제외)
      cleanText = cleanText.replace(/([^\\])%.*/g, '$1');
      // (C) LaTeX 이스케이프 문자 복구 (50\% -> 50%)
      cleanText = cleanText.replace(/\\%/g, '%');
      
      // (D) 너무 많은 빈 줄(3줄 이상)은 2줄로 줄임
      cleanText = cleanText.replace(/\n{3,}/g, '\n\n');

      // 4. 화면에 출력
      var container = document.getElementById('abstract-content');
      container.innerText = cleanText.trim();

      // 5. MathJax 수식 다시 그리기 (수식이 있을 경우 필수)
      if (window.MathJax) {
          if (MathJax.typesetPromise) {
              MathJax.typesetPromise([container]);
          } else if (MathJax.Hub) {
              MathJax.Hub.Queue(["Typeset", MathJax.Hub, container]);
          }
      }
    } catch (e) {
      console.error("Abstract rendering error:", e);
      document.getElementById('abstract-content').innerHTML = 
        "<span style='color:red;'>Error: " + e.message + "</span>";
    }
  });
</script>

<br>

<em>Updated March 2025</em>

<object data="/assets/pdf/Jae-Yu Jung_dissertation_proposal_ch1_v2.pdf" width="100%" height="1600%" type="application/pdf"> 
     <p>You can [get the PDF]({{ site.url }}/assets/pdf/Jae-Yu Jung_dissertation_proposal_ch1_v2.pdf) directly.</p> 
 </object>


{% comment %}
abstract: 
  I study the effect of electricity prices on market entry of electric vehicle (EV) charging stations. I compile a novel dataset linking commercial electricity prices to charging stations across U.S. ZIP codes from 2015–2022. I convert complex pricing schedules into a standardized cost metric by constructing station-level load profiles from observed charging sessions and calculating monthly bills. Using synthetic control and local projection difference-in-differences designs, I estimate the effects of new price schedules for EV charging stations, aimed at reducing high demand charges. The results show that these schedules substantially lowered demand charges for DC fast charging stations by 50% and increased the entry of DC fast charging ports by by 35% per zip code, underscoring the role of targeted rate design in accelerating EV infrastructure growth.
  
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
