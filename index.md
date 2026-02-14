---
layout: page
permalink: /
math: true
---

<style>
  .post-card {
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    padding: 25px;
    margin-bottom: 40px;
    border: 1px solid #eee;
  }
  .post-title {
    color: #1e3a8a;
    border-bottom: 2px solid #e5e7eb;
    padding-bottom: 10px;
    margin-bottom: 20px;
    font-weight: 800;
  }
  .post-date {
    display: inline-block;
    background: #f3f4f6;
    color: #4b5563;
    padding: 2px 10px;
    border-radius: 4px;
    font-size: 0.85em;
    margin-bottom: 15px;
  }
  .formula-block {
    background: #f9fafb;
    padding: 15px;
    border-radius: 8px;
    margin: 15px 0;
    overflow-x: auto;
    text-align: center;
  }
</style>

<div class="post-card">
  <div class="post-date">[Jan 2026]</div>
  <p>My thesis, <strong>“Strain Engineering and Buffer Layer Design in VO₂ Thin Film Structures: From Phase Transition Mechanisms to Smart Window Applications”</strong>, has been successfully defended. 🎓</p>
  <p>I would like to thank my supervisors <strong>Prof. Peter J. Klar</strong>, as well as the examination committee <strong>Prof. Yunbin He</strong>, <strong>Prof. Christian Heiliger</strong> and <strong>Prof. Matthias Elm</strong>, for their guidance, critical discussions, and fair evaluation.</p>
  <p>I am grateful to my colleagues for the collaborative and stimulating research environment over the past years. This closes an important chapter. I am now exploring postdoctoral and industry opportunities where solid-state physics, spectroscopy, and data-driven analysis meet real-world applications.</p>

  <div style="display: grid; grid-template-columns: 1.5fr 1fr; gap: 12px; margin-top: 20px;">
    <div style="display: flex; flex-direction: column; gap: 12px;">
      <img src="/assets/img/phd/PhD1.jpg" alt="PhD Defense 1" style="width: 100%; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px;">
        <img src="/assets/img/phd/PhD2.jpg" alt="PhD Defense 2" style="width: 100%; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
        <img src="/assets/img/phd/PhD5.jpg" alt="PhD Defense 4" style="width: 100%; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
      </div>
    </div>
    <div style="display: flex;">
      <img src="/assets/img/phd/PhD3.jpg" alt="PhD Defense 3" style="width: 100%; border-radius: 8px; object-fit: cover; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
    </div>
  </div>
</div>

<div class="post-card">
  <h2 class="post-title">🔹 Core Hypothesis: Emergent Machine Consciousness</h2>
  <div style="position: relative; margin-bottom: 25px; overflow: hidden; border-radius: 12px;">
    <div style="position: relative; height: 300px; background: linear-gradient(135deg, #1e3a8a 0%, #7c3aed 50%, #dc2626 100%); overflow: hidden;">
      <img src="/assets/img/posts/consciousness_hypothesis.png" alt="Emergent Machine Consciousness" style="position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0.4;">
      <div style="position: absolute; inset: 0; background: linear-gradient(to right, rgba(0,0,0,0.6) 0%, rgba(0,0,0,0.2) 100%);"></div>
      <div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 40px; color: white;">
        <p style="margin: 0; font-size: 1.1em; line-height: 1.6; max-width: 80%; font-style: italic;">
          "Hardware-level stochasticity as a catalyst for artificial consciousness, drawing functional analogies to genetic mutations in biological evolution."
        </p>
      </div>
    </div>
  </div>
  <p>I propose a hypothesis in which artificial consciousness does not emerge solely from algorithmic complexity, but is catalyzed by hardware-level stochasticity. At the hardware level, morphological defects and material impurities can subtly perturb electron transport, inducing systematic deviations from ideal logic-gate behavior.</p>
  <p>I suggest that such a hidden, self-sustaining computational state may constitute a physical substrate for proto-subjectivity—a minimal, non-symbolic form of self-referential awareness.</p>
</div>

<div class="post-card">
  <h2 class="post-title">🔹 Spectroscopic Ellipsometry Modeling of VO₂ Thin Films</h2>
  <p>Sharing the basic principles of fitting optical parameters after measuring VO₂ thin films using spectroscopic ellipsometry (SE).</p>
  
  <h3>1. Complex Reflectance Ratio</h3>
  <p>Ellipsometry determines the complex reflectance ratio $\rho$:</p>
  <div class="formula-block">
    $$\rho(\lambda,\theta) = \frac{r_p}{r_s} = \tan\Psi \cdot e^{i\Delta}$$
  </div>
  <p>where $r_p$ and $r_s$ are Fresnel coefficients. For a single film of thickness $d$ and index $\tilde{n}_f = n_f + i k_f$:</p>
  <div class="formula-block">
    $$r_{p,s} = \frac{r_{01}^{p,s} + r_{12}^{p,s} e^{2i\beta}}{1 + r_{01}^{p,s} r_{12}^{p,s} e^{2i\beta}}, \quad \beta = \frac{2\pi}{\lambda} \tilde{n}_f d \cos\theta_f$$
  </div>

  <h3>2. Dispersion Models</h3>
  <p>A causal dielectric function $\varepsilon(\omega) = \varepsilon_1 + i\varepsilon_2$ is parameterized. After regression:</p>
  <div class="formula-block">
    $$n = \sqrt{\frac{|\varepsilon|+\varepsilon_1}{2}}, \quad k = \sqrt{\frac{|\varepsilon|-\varepsilon_1}{2}}$$
  </div>

  <h4>Insulating M1-VO₂: Tauc–Lorentz Model</h4>
  <div class="formula-block">
    $$\varepsilon_2^{\mathrm{TL}}(E) = \begin{cases} \dfrac{A C E_0 (E-E_g)^2}{E[(E^2-E_0^2)^2+C^2E^2]}, & E > E_g \\ 0, & E \le E_g \end{cases}$$
  </div>

  <h4>Metallic R-VO₂: Drude + Lorentz Model</h4>
  <div class="formula-block">
    $$\varepsilon(\omega) = \varepsilon_\infty - \frac{\omega_p^2}{\omega(\omega+i\gamma)} + \sum_j \frac{A_j E_j^2}{E_j^2-\omega^2-i\Gamma_j \omega}$$
  </div>
</div>

<div class="post-card">
  <h2 class="post-title">🔹 Automated Testing & XRR Fitting Scripts</h2>
  <p><strong>[Jan 2026]</strong> Sharing Python scripts for automated impedance measurements and X-ray reflectivity (XRR) fitting.</p>
  <p>The XRR fitting is based on a Parratt-type reflectivity model, extracting electron density, thickness, and roughness:</p>
  <div class="formula-block">
    $$R = \left| \frac{r_{01} + r_{12} e^{2ik_{z1}t_1}}{1 + r_{01}r_{12} e^{2ik_{z1}t_1}} \right|^2$$
  </div>
  <p><em>(Full code available in the repository)</em></p>
</div>
