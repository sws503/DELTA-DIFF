---
layout: project_page
permalink: /

title: "DELTA-DIFF: Automatic Multi-Step Distillation for Compressing Diffusion Models"
authors:
  Anonymous authors
affiliations:
  Paper under double-blind review
paper: [논문 PDF 파일 링크 또는 익명 링크]
code: [익명화된 GitHub 저장소 링크]
---

<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2 class="title is-3">Compressing Diffusion Models, One Small Step at a Time</h2>
        <div class="content">
            <p>
                Conventional single-step compression creates a large "knowledge gap," leading to significant performance loss. <strong>DELTA-Diff</strong> bridges this gap by creating an optimal, multi-step distillation path with a series of teacher-assistant models.
            </p>
        </div>
        <img src="static/images/overview.png" alt="Overview of DELTA-Diff vs Conventional KD"/>
        <p class="is-size-7 has-text-grey">
            <em>Our multi-step approach (bottom) breaks down the large teacher-student knowledge gap into smaller, manageable steps, preserving knowledge far more effectively than conventional single-step methods (top).</em>
        </p>
    </div>
</div>

---

<div class="columns is-centered">
    <div class="column is-four-fifths">
        <h2 class="title is-4">Abstract</h2>
        <div class="content has-text-justified">
            <p>
                Deploying generative image models on edge devices requires to compress them effectively, but aggressive compression often leads to significant degradation in generation performance. While precedent studies have attempted to mitigate this issue through single-step architectural pruning, they do not address the large capacity gap between the original and compressed models... In this paper, we propose DELTA-Diff, a multi-step knowledge distillation framework designed to resolve this issue.
            </p>
        </div>
    </div>
</div>

---

<div class="columns is-centered">
    <div class="column is-four-fifths">
        <h2 class="title is-4">How It Works: Surrogate-Assisted Path Optimization</h2>
        <div class="content has-text-justified">
            <p>
                Finding the optimal distillation path is computationally intractable. Our framework transforms this global search into a series of guided local searches. At each stage, a <strong>surrogate-assisted evolutionary search</strong> efficiently finds the best intermediate model architecture, guided by our novel <strong>semantic similarity</strong> metric.
            </p>
            <img src="static/images/diagram.png" alt="Overview of the DELTA-Diff framework"/>
        </div>
    </div>
</div>

---

<h2 class="title is-3 has-text-centered">Results</h2>

<div class="columns is-centered">
    <div class="column is-full">
        <h3 class="title is-4 has-text-centered">Superior Visual Fidelity at High Compression</h3>
        <p class="has-text-centered">
            At a <strong>63% compression ratio</strong> (-63% U-Net Params), our model (DELTA-Diff Tiny) preserves the teacher's visual quality, while the single-step baseline (BK-SDM) suffers from clear degradation.
        </p>
        <img src="static/images/qualitaty.png" alt="Qualitative comparison of generated images"/>
    </div>
</div>

<div class="columns is-centered">
    <div class="column is-four-fifths">
        <h3 class="title is-4 has-text-centered">Consistent Performance Gains</h3>
        <p class="has-text-centered">
            DELTA-Diff consistently outperforms the single-step baseline across all compression levels, with the performance gap widening at higher compression ratios.
        </p>
        | Model | U-Net Params | HPS v2 ↑ |
        | :--- | :---: | :---: |
        | Teacher | 860M | 2810 |
        | **Ours (Tiny, -63%)** | **323M** | **2650** |
        | BK-SDM (Tiny, -63%) | 323M | 2601 |
        | **Ours (Small, -44%)** | **483M** | **2691** |
        | BK-SDM (Small, -44%) | 483M | 2662 |
    </div>
</div>

<div class="columns is-centered">
    <div class="column is-full">
        <h3 class="title is-4 has-text-centered">Why It Works: Preserving Semantic Representations</h3>
        <p class="has-text-centered">
            Our method's success comes from preserving the teacher's internal semantic structure. The cross-attention maps of our model show strong alignment with the teacher's, unlike the baseline.
        </p>
        <img src="static/images/attention_maps.png" alt="Cross-attention map comparison"/>
    </div>
</div>

---

<div class="columns is-centered">
    <div class="column is-four-fifths">
        <h2 class="title is-4">Citation</h2>
        <code>
<pre>@article{anonymous2026delta,
  title={DELTA-DIFF: Automatic Multi-Step Distillation for Compressing Diffusion Models},
  author={Anonymous},
  journal={Under review},
  year={2026}
}</pre>
        </code>
    </div>
</div>
