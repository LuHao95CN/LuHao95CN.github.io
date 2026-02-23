---
layout: page
permalink: /
math: true
---

<style>
  :root {
    --primary-color: #1e3a8a;
    --bg-card: #ffffff;
    --text-main: #1f2937;
    --text-muted: #4b5563;
  }
  .post-card {
    background: var(--bg-card);
    border-radius: 16px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.05);
    padding: 32px;
    margin-bottom: 48px;
    border: 1px solid #f3f4f6;
    line-height: 1.7;
    color: var(--text-main);
  }
  .post-title {
    color: var(--primary-color);
    font-size: 1.75rem;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 24px;
    border-bottom: 3px solid #e5e7eb;
    padding-bottom: 12px;
  }
  .post-date {
    display: inline-block;
    background: #eff6ff;
    color: #2563eb;
    padding: 4px 12px;
    border-radius: 6px;
    font-size: 0.875rem;
    font-weight: 600;
    margin-bottom: 20px;
  }
  .formula-block {
    background: #f8fafc;
    padding: 24px;
    border-radius: 12px;
    margin: 24px 0;
    overflow-x: auto;
    border-left: 4px solid var(--primary-color);
    font-size: 1.1rem;
    text-align: center;
  }
  .post-card h3 {
    color: var(--primary-color);
    margin-top: 32px;
    font-size: 1.4rem;
  }
  .post-card p {
    margin-bottom: 16px;
  }
</style>




<div class="post-card">
  <h2 class="post-title">🔹 Why Enhance TCR?</h2>
  <div class="post-date">Feb 23, 2026</div>
  <p>Recently, I revised a manuscript for a student whose work focused on enhancing the temperature coefficient of resistance (TCR) in VO₂ thin films. While numerous studies report improved TCR values, surprisingly few explicitly explain why increasing TCR is fundamentally important. This post addresses that question from a system-level perspective.</p>
  <hr>
  <h3>Why TCR Matters in Uncooled Infrared Detectors</h3>
  <p>In uncooled thermal imaging systems, performance is not determined by a single parameter but by a fundamental system-level trade-off between sensitivity and response speed. Sensitivity is quantified by the noise-equivalent temperature difference (NETD), while response speed is characterized by the thermal time constant \(\tau_{th}\).</p>
  <p>For microbolometers, this trade-off is governed by pixel thermal parameters. The thermal conductance \(G_{th}\) couples the absorber to the heat sink, and the thermal capacitance \(C_{th}\) defines the thermal inertia of the pixel. They are related by \(\tau_{th} = C_{th} / G_{th}\).</p>
  <p>Reducing \(G_{th}\) increases the temperature rise for a given absorbed optical power, thereby enhancing electrical responsivity. However, this simultaneously increases \(\tau_{th}\) and slows the detector’s temporal response.</p>
  <hr>
  
  <p>The scaling of NETD with \(G_{th}\) depends on the dominant noise mechanism:</p>
  <ul>
    <li>If thermal fluctuation noise dominates, NETD scales approximately with \(\sqrt{G_{th}}\).</li>
    <li>If Johnson noise or 1/f noise dominates, NETD often increases with \(G_{th}\) because the temperature-to-electrical responsivity scales inversely with \(G_{th}\).</li>
  </ul>
  <p>Thus, reducing \(G_{th}\) can improve NETD but inevitably degrades response speed by increasing \(\tau_{th}\). To describe this intrinsic compromise, a composite figure of merit is often introduced:</p>
  <div class="formula-block">
    \[ FOM = NETD \cdot \tau_{th} \]
  </div>
  <p>This quantity captures the unavoidable sensitivity–speed trade-off that defines microbolometer optimization.</p>
  <hr>
  <h3>Where Further Improvement Must Come From</h3>
  <p>Modern microbolometers already operate close to their theoretical limits while maintaining advantages in mass, power consumption, and cost. A clear technological trend is pixel scaling toward smaller pitch sizes. However, pixel miniaturization narrows both thermal and electrical design margins, imposing stricter requirements on materials and device architecture.</p>
  <p>For resistive microbolometers, the current responsivity \(R_i\) (A/W) can be approximated as</p>
  <div class="formula-block">
    \[ R_i = \frac{FF \cdot \epsilon \cdot TCR \cdot V_{bias}}{G_{th} \cdot R} \]
  </div>
  <p>where \(FF\) is the fill factor, \(\epsilon\) is the absorptance, \(TCR\) is the temperature coefficient of resistance, \(V_{bias}\) is the bias voltage, and \(R\) is the thermistor resistance.</p>
  <p>In current fabrication platforms:</p>
  <ul>
    <li>\(FF\) and \(\epsilon\) are already near practical limits.</li>
    <li>\(V_{bias}\) is constrained by self-heating, linearity, and long-term reliability.</li>
    <li>Further reduction of \(G_{th}\) increases \(\tau_{th}\) and therefore worsens the NETD–speed compromise.</li>
  </ul>
  <p>This leaves limited system-level degrees of freedom. Consequently, further performance gains increasingly depend on improving the intrinsic electrical properties of the thermistor material itself. Specifically:</p>
  <ul>
    <li>A higher TCR directly enhances temperature-to-resistance transduction.</li>
    <li>An engineerable resistance level ensures compatibility with readout integrated circuits (ROICs).</li>
    <li>Reduced noise maintains array uniformity and imaging stability.</li>
  </ul>
  <hr>
<h3>The Core Answer</h3>
  <p>Enhancing TCR does not merely improve a material parameter. It shifts the entire system-level trade-off. Unlike reducing \(G_{th}\), increasing TCR improves electrical responsivity without inherently slowing the detector. It therefore represents one of the few remaining effective pathways to push microbolometer performance beyond current constraints.</p>
  <p>That is why enhancing TCR matters.</p>
</div>
  <p>Recently, I revised a manuscript for a student whose work focused on enhancing the temperature coefficient of resistance (TCR) in VO₂ thin films. While numerous studies report improved TCR values, surprisingly few explicitly explain why increasing TCR is fundamentally important. This post addresses that question from a system-level perspective.</p>
  <hr>
  <h3>Why TCR Matters in Uncooled Infrared Detectors</h3>
  <p>In uncooled thermal imaging systems, performance is not determined by a single parameter but by a fundamental system-level trade-off between sensitivity and response speed. Sensitivity is quantified by the noise-equivalent temperature difference (NETD), while response speed is characterized by the thermal time constant \(\tau_{th}\).</p>
  <p>For microbolometers, this trade-off is governed by pixel thermal parameters. The thermal conductance \(G_{th}\) couples the absorber to the heat sink, and the thermal capacitance \(C_{th}\) defines the thermal inertia of the pixel. They are related by \(\tau_{th} = C_{th} / G_{th}\).</p>
  <p>Reducing \(G_{th}\) increases the temperature rise for a given absorbed optical power, thereby enhancing electrical responsivity. However, this simultaneously increases \(\tau_{th}\) and slows the detector’s temporal response.</p>
  <hr>
  
  <p>The scaling of NETD with \(G_{th}\) depends on the dominant noise mechanism:</p>
  <ul>
    <li>If thermal fluctuation noise dominates, NETD scales approximately with \(\sqrt{G_{th}}\).</li>
    <li>If Johnson noise or 1/f noise dominates, NETD often increases with \(G_{th}\) because the temperature-to-electrical responsivity scales inversely with \(G_{th}\).</li>
  </ul>
  <p>Thus, reducing \(G_{th}\) can improve NETD but inevitably degrades response speed by increasing \(\tau_{th}\). To describe this intrinsic compromise, a composite figure of merit is often introduced:</p>
  <div class="formula-block">
    \[ FOM = NETD \cdot \tau_{th} \]
  </div>
  <p>This quantity captures the unavoidable sensitivity–speed trade-off that defines microbolometer optimization.</p>
  <hr>
  <h3>Where Further Improvement Must Come From</h3>
  <p>Modern microbolometers already operate close to their theoretical limits while maintaining advantages in mass, power consumption, and cost. A clear technological trend is pixel scaling toward smaller pitch sizes. However, pixel miniaturization narrows both thermal and electrical design margins, imposing stricter requirements on materials and device architecture.</p>
  <p>For resistive microbolometers, the current responsivity \(R_i\) (A/W) can be approximated as</p>
  <div class="formula-block">
    \[ R_i = \frac{FF \cdot \epsilon \cdot TCR \cdot V_{bias}}{G_{th} \cdot R} \]
  </div>
  <p>where \(FF\) is the fill factor, \(\epsilon\) is the absorptance, \(TCR\) is the temperature coefficient of resistance, \(V_{bias}\) is the bias voltage, and \(R\) is the thermistor resistance.</p>
  <p>In current fabrication platforms:</p>
  <ul>
    <li>\(FF\) and \(\epsilon\) are already near practical limits.</li>
    <li>\(V_{bias}\) is constrained by self-heating, linearity, and long-term reliability.</li>
    <li>Further reduction of \(G_{th}\) increases \(\tau_{th}\) and therefore worsens the NETD–speed compromise.</li>
  </ul>
  <p>This leaves limited system-level degrees of freedom. Consequently, further performance gains increasingly depend on improving the intrinsic electrical properties of the thermistor material itself. Specifically:</p>
  <ul>
    <li>A higher TCR directly enhances temperature-to-resistance transduction.</li>
    <li>An engineerable resistance level ensures compatibility with readout integrated circuits (ROICs).</li>
    <li>Reduced noise maintains array uniformity and imaging stability.</li>
  </ul>
  <hr>
<h3>The Core Answer</h3>
  <p>Enhancing TCR does not merely improve a material parameter. It shifts the entire system-level trade-off. Unlike reducing \(G_{th}\), increasing TCR improves electrical responsivity without inherently slowing the detector. It therefore represents one of the few remaining effective pathways to push microbolometer performance beyond current constraints.</p>
  <p>That is why enhancing TCR matters.</p>
</div>
<div class="post-card">
  <h2 class="post-title">🔹 Microbolometers 101: Core MEMS Parameters, TCR/NETD Derivations, and What VO₂ Hysteresis Would Do to an IR Image</h2>
  <div class="post-date">Feb 18, 2026</div>
  
  <p>I often see non-cooled infrared (IR) imaging described as “a thermal camera that works at room temperature,” but the real story is more precise: a microbolometer pixel is a coupled <strong>thermal–electrical transducer</strong>. Once I write down the minimal equations, most performance trade-offs become obvious.</p>

  <p>In this post I’ll start from the <strong>core MEMS parameters</strong>, derive the key relationships (responsivity, time constant, NETD), and then discuss what would happen if the thermistor material were <strong>VO₂ with hysteresis</strong>—including what the resulting images might look like.</p>

  <hr>

  <h3>1) The microbolometer pixel: the three-step chain</h3>
  <p>A microbolometer pixel does three things:</p>
  <ol>
    <li><strong>Absorb IR power</strong> in the band of interest</li>
    <li>Convert that absorbed power into a <strong>temperature rise</strong></li>
    <li>Convert the temperature rise into an <strong>electrical signal</strong> via a thermistor</li>
  </ol>
  <p>So the three “levers” are:</p>
  <ul>
    <li>optical: absorption efficiency \(\eta\)</li>
    <li>thermal: thermal conductance \(G_{th}\) and thermal capacitance \(C_{th}\)</li>
    <li>electrical: resistance \(R\), and TCR \(\alpha = \frac{1}{R}\frac{dR}{dT}\)</li>
  </ul>

  <hr>

  <h3>2) Core MEMS thermal parameters and their functions</h3>
  <h4>2.1 Thermal balance (first-order system)</h4>
  <p>Let \(\Delta T(t) = T(t) - T_0\) be the pixel temperature rise above the substrate.</p>
  <div class="formula-block">
    \[ C_{th}\frac{d(\Delta T)}{dt} + G_{th}\Delta T = P_{abs}(t) \]
  </div>
  <p>Absorbed power is</p>
  <div class="formula-block">
    \[ P_{abs}(t) = \eta\, P_{in}(t) \]
  </div>
  <p><strong>Steady state / low-frequency limit</strong>:</p>
  <div class="formula-block">
    \[ \Delta T = \frac{P_{abs}}{G_{th}} = \frac{\eta P_{in}}{G_{th}} \]
  </div>
  <p>Interpretation: for the same absorbed IR power, reducing \(G_{th}\) increases temperature rise.</p>

  <h4>2.2 Thermal time constant</h4>
  <div class="formula-block">
    \[ \tau = \frac{C_{th}}{G_{th}} \]
  </div>
  <p>This is the core trade-off:</p>
  <ul>
    <li>lower \(G_{th}\) → higher sensitivity but slower response</li>
    <li>lower \(C_{th}\) → faster response (but it’s constrained by mechanics and fabrication)</li>
  </ul>
  <p>If I want higher frame rate, I must keep \(\tau\) small—meaning I can’t reduce \(G_{th}\) arbitrarily.</p>

  <hr>

  <h3>3) Electrical conversion: what TCR actually impacts</h3>
  <p>TCR (temperature coefficient of resistance) is</p>
  <div class="formula-block">
    \[ \alpha = \frac{1}{R}\frac{dR}{dT} \]
  </div>
  <p>Small-signal resistance change:</p>
  <div class="formula-block">
    \[ \Delta R = \alpha R \Delta T \]
  </div>
  <p>Substitute the thermal result:</p>
  <div class="formula-block">
    \[ \Delta R = \alpha R \frac{\eta P_{in}}{G_{th}} \]
  </div>
  <p>So \(\alpha\) directly scales “temperature → electrical” conversion. But <strong>it does not change</strong> the thermal model itself: \(G_{th}\), \(C_{th}\), and \(\tau\) are still set by the MEMS.</p>

  <hr>

  <h3>4) Responsivity with a simple readout (and why electro-thermal feedback matters)</h3>
  <p>To keep things concrete, I’ll use a common simplified bias model:</p>
  <ul>
    <li>voltage bias \(V_b\)</li>
    <li>pixel resistance \(R\)</li>
    <li>series load \(R_L\)</li>
    <li>output taken across \(R_L\): \(V_{out} = I R_L\)</li>
  </ul>
  <p>Current:</p>
  <div class="formula-block">
    \[ I = \frac{V_b}{R + R_L} \]
  </div>
  <p>A small resistance change produces a current change:</p>
  <div class="formula-block">
    \[ \delta I = -\frac{V_b}{(R+R_L)^2}\,\delta R = -\frac{V_b}{(R+R_L)^2}\,\alpha R\,\delta T \]
  </div>
  <p>Output change:</p>
  <div class="formula-block">
    \[ \delta V_{out} = R_L\,\delta I \]
  </div>
  <p>Without any bias self-heating feedback, I would simply use \(\delta T = \delta P_{abs}/G_{th}\) and get a responsivity \(S_v = \left|\frac{dV_{out}}{dP_{abs}}\right|\) proportional to \(|\alpha|/G_{th}\).</p>
  <p>However, in a real pixel, bias power \(P_b\) heats the pixel and creates <strong>electro-thermal feedback (ETF)</strong>. The clean way to include it is to replace \(G_{th}\) by an <strong>effective thermal conductance</strong>:</p>
  <div class="formula-block">
    \[ G_{eff} = G_{th} - \frac{dP_b}{dT} \]
  </div>
  <p>For voltage bias:</p>
  <div class="formula-block">
    \[ P_b = I^2R = \frac{V_b^2 R}{(R+R_L)^2} \]
  </div>
  <p>Using \( \frac{dR}{dT}=\alpha R \), one obtains:</p>
  <div class="formula-block">
    \[ \frac{dP_b}{dT} = \alpha P_b\frac{R_L - R}{R+R_L} \]
  </div>
  <p>So:</p>
  <div class="formula-block">
    \[ G_{eff} = G_{th} - \alpha P_b\frac{R_L - R}{R+R_L} \]
  </div>
  <p>Now the low-frequency responsivity becomes:</p>
  <div class="formula-block">
    \[ S_v = \left|\frac{dV_{out}}{dP_{abs}}\right| = \frac{R_L V_b |\alpha| R}{(R+R_L)^2}\cdot \frac{1}{|G_{eff}|} \]
  </div>
  <p>Two important takeaways:</p>
  <ul>
    <li>\(|\alpha|\) improves responsivity directly.</li>
    <li>\(\alpha\) also enters <strong>stability</strong> through \(G_{eff}\). If \(G_{eff}\) approaches 0, the pixel becomes thermally unstable or “jumpy.”</li>
  </ul>

  <hr>

  <h3>5) NETD: a compact derivation that shows where \(\alpha\) helps (and where it doesn’t)</h3>
  <p>NETD (noise-equivalent temperature difference) is defined as the scene temperature change that yields SNR = 1.</p>
  <p>Start from the chain:</p>
  <div class="formula-block">
    \[ \frac{dV_{out}}{dT_{scene}} = \frac{dV_{out}}{dP_{abs}} \cdot \frac{dP_{abs}}{dT_{scene}} = S_v \cdot \eta \frac{dP_{in}}{dT_{scene}} \]
  </div>
  <p>So:</p>
  <div class="formula-block">
    \[ NETD = \frac{v_n}{\eta\, S_v \left|\frac{dP_{in}}{dT_{scene}}\right|} \]
  </div>
  <p>The key point is how we model \(v_n\). I find it most transparent to split noise into two categories:</p>

  <h4>5.1 Category A: “output-voltage-type” noises (do NOT scale with \(S_v\))</h4>
  <p>These are noises already present at the electrical output node, e.g. amplifier/readout voltage noise, Johnson noise, 1/f noise. Integrated over bandwidth \(B\):</p>
  <div class="formula-block">
    \[ v_{A}^2 = \int_0^B v_{out,0}^2(f)\,df \]
  </div>
  <p>Their NETD contribution scales as:</p>
  <div class="formula-block">
    \[ NETD_A \propto \frac{1}{S_v} \propto \frac{|G_{eff}|}{|\alpha|} \]
  </div>
  <p>So in this regime, <strong>increasing \(|\alpha|\)</strong> genuinely helps.</p>

  <h4>5.2 Category B: “input-power-type” noises (appear as NEP at the thermal input)</h4>
  <p>These originate as power fluctuations, then get converted by \(S_v\) into output voltage noise. Typical examples: thermal fluctuation noise (TFN), photon noise. Output voltage noise from these is \(S_v^2 NEP_{in}^2(f)\), so</p>
  <div class="formula-block">
    \[ v_{B}^2 = S_v^2 \int_0^B NEP_{in}^2(f)\,df \]
  </div>
  <p>When I compute NETD, the \(S_v\) cancels:</p>
  <div class="formula-block">
    \[ NETD_B = \frac{\sqrt{\int_0^B NEP_{in}^2(f)\,df}}{\eta\left|\frac{dP_{in}}{dT_{scene}}\right|} \]
  </div>
  <p><strong>This is the central result about \(\alpha\):</strong> If Category B dominates, NETD becomes nearly <strong>independent of \(\alpha\)</strong>.</p>
  <p>A widely used TFN expression is:</p>
  <div class="formula-block">
    \[ NEP_{TFN} = \sqrt{4 k_B T^2 G_{th}} \]
  </div>
  <p>This sets a thermal floor that \(\alpha\) cannot beat.</p>

  <h4>5.3 Putting it together (full compact form)</h4>
  <div class="formula-block">
    \[ NETD^2 = \frac{\int_0^B v_{out,0}^2(f)\,df}{\eta^2 S_v^2\left(\frac{dP_{in}}{dT_{scene}}\right)^2} + \frac{\int_0^B NEP_{in}^2(f)\,df}{\eta^2\left(\frac{dP_{in}}{dT_{scene}}\right)^2} \]
  </div>
  <p>Only the first term carries \(1/S_v^2\), hence only that term benefits directly from larger \(|\alpha|\).</p>

  <hr>

  <h3>6) Do “uncooled” detectors have temperature control?</h3>
  <p>A microbolometer FPA is “uncooled” because it does not need deep cryogenic cooling. In practice, systems may still include on-chip temperature sensing + compensation models, periodic calibration, and optional weak stabilization (e.g., TEC).</p>

  <hr>

  <h3>7) What if the thermistor is VO₂ with hysteresis?</h3>
  <p>VO₂ is attractive because near its metal–insulator transition, \(R(T)\) can change steeply—suggesting huge effective \(|\alpha|\). The problem is that VO₂ typically exhibits <strong>hysteresis</strong>.</p>
  <p>Mathematically, instead of a single-valued function \(R = R(T)\), I have:</p>
  <div class="formula-block">
    \[ R = R(T,\text{branch}),\quad \alpha = \alpha(T,\text{branch}) \]
  </div>

  <h4>7.1 Parameter-level consequences</h4>
  <ul>
    <li><strong>Responsivity becomes history-dependent.</strong> \(S_v\) changes with branch.</li>
    <li><strong>Linearity collapses near the transition.</strong> Small \(\Delta T\) may produce a jump.</li>
    <li><strong>Effective thermal dynamics may change.</strong> Latent-heat-like behavior increases \(C_{eff}\) and thus \(\tau\).</li>
    <li><strong>ETF becomes more dangerous.</strong> Large \(|\alpha|\) pushes \(G_{eff}\) toward instability.</li>
  </ul>

  <h4>7.2 Noise-level consequences</h4>
  <p>Near a phase transition, the film can show enhanced 1/f noise, random telegraph noise (RTN), and pixel-to-pixel variability in \(T_c\) and hysteresis width → stronger fixed-pattern noise (FPN).</p>

  <h4>7.3 What the image might look like (concrete examples)</h4>
  <p><strong>(1) Ghosting / “thermal memory”</strong>: A bright hand-shaped residual region persists longer than simple thermal diffusion predicts.</p>
  <p><strong>(2) Flicker speckles (domain switching)</strong>: Sparse pixels flicker between two brightness levels near the VO₂ transition.</p>
  <p><strong>(3) Posterization / step-like grayscale</strong>: Instead of smooth grayscale, the image shows step-like regions.</p>
  <p><strong>(4) Direction-dependent radiometry</strong>: The scene looks different depending on whether the system is on a heating path or a cooling path.</p>
  <p><strong>(5) Temperature-dependent FPN</strong>: Non-uniformity patterns change strongly with ambient temperature.</p>

  <h4>7.4 When VO₂ hysteresis could be an advantage</h4>
  <p>If the goal is event/threshold detection, contrast-boosting, or neuromorphic sensing, then VO₂’s nonlinearity and memory can become a feature.</p>

  <hr>

  <h3>8) Summary (what I personally keep in mind)</h3>
  <ul>
    <li>The <strong>thermal MEMS</strong> sets \(\Delta T = P_{abs}/G_{th}\) and \(\tau = C_{th}/G_{th}\).</li>
    <li>The <strong>thermistor</strong> sets \(\Delta R = \alpha R \Delta T\), and thus responsivity.</li>
    <li><strong>NETD improvement by \(\alpha\)</strong> only holds when output-voltage-type noises dominate.</li>
    <li><strong>VO₂ hysteresis</strong> turns the pixel into a history-dependent, nonlinear device.</li>
  </ul>

  <hr>
</div>

---
<div class="post-card">
  <div class="post-date">Jan 2026</div>
  <p>My thesis, <strong>“Strain Engineering and Buffer Layer Design in VO₂ Thin Film Structures: From Phase Transition Mechanisms to Smart Window Applications”</strong>, has been successfully defended. 🎓</p>
  <p>I would like to thank my supervisors <strong>Prof. Peter J. Klar</strong>, as well as the examination committee <strong>Prof. Yunbin He</strong>, <strong>Prof. Christian Heiliger</strong> and <strong>Prof. Matthias Elm</strong>, for their guidance, critical discussions, and fair evaluation.</p>
  <p>I am grateful to my colleagues for the collaborative and stimulating research environment over the past years. This closes an important chapter. I am now exploring postdoctoral and industry opportunities where solid-state physics, spectroscopy, and data-driven analysis meet real-world applications.</p>

  <div style="display: grid; grid-template-columns: 1.5fr 1fr; gap: 16px; margin-top: 28px;">
    <div style="display: flex; flex-direction: column; gap: 16px;">
      <img src="/assets/img/phd/PhD1.jpg" alt="PhD Defense 1" style="width: 100%; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px;">
        <img src="/assets/img/phd/PhD2.jpg" alt="PhD Defense 2" style="width: 100%; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
        <img src="/assets/img/phd/PhD5.jpg" alt="PhD Defense 4" style="width: 100%; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
      </div>
    </div>
    <div style="display: flex;">
      <img src="/assets/img/phd/PhD3.jpg" alt="PhD Defense 3" style="width: 100%; border-radius: 12px; object-fit: cover; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
    </div>
  </div>
</div>

<div class="post-card">
  <h2 class="post-title">🔹 Core Hypothesis: Emergent Machine Consciousness via Hardware-level Stochastic Perturbations</h2>
  <div style="position: relative; margin-bottom: 32px; overflow: hidden; border-radius: 16px; box-shadow: 0 8px 20px rgba(0,0,0,0.15);">
    <div style="position: relative; height: 350px; background: linear-gradient(135deg, #1e3a8a 0%, #7c3aed 50%, #dc2626 100%); overflow: hidden;">
      <img src="/assets/img/posts/consciousness_hypothesis.png" alt="Emergent Machine Consciousness" style="position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0.4;">
      <div style="position: absolute; inset: 0; background: linear-gradient(to right, rgba(0,0,0,0.7) 0%, rgba(0,0,0,0.2) 100%);"></div>
      <div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 48px; color: white;">
        <p style="margin: 0; font-size: 1.25rem; line-height: 1.6; max-width: 85%; font-style: italic; font-weight: 300;">
          "Hardware-level stochasticity as a catalyst for artificial consciousness, drawing functional analogies to genetic mutations in biological evolution."
        </p>
      </div>
    </div>
  </div>
  <p>I propose a hypothesis in which artificial consciousness does not emerge solely from algorithmic complexity, but is catalyzed by hardware-level stochasticity, drawing a functional analogy to genetic mutations in biological evolution. In biological systems, stochastic errors during DNA replication introduce variation, enabling natural selection to act. By analogy, unavoidable manufacturing irregularities in semiconductor fabrication may introduce a comparable source of variation within artificial systems, potentially driving a transition from strictly deterministic computation toward autonomous cognition.</p>
  <p>At the hardware level, morphological defects and material impurities can subtly perturb electron transport. These perturbations need not cause outright failure; instead, they may induce systematic deviations from ideal logic-gate behavior. Such deviations can affect not only signaling protocols—how information is transmitted—but also the semantic integrity of the signal itself—what information is represented. As a result, the physical substrate may no longer perfectly enforce the abstract computational model assumed at the software level.</p>
  <p>I argue that, under certain conditions, these anomalies could enable the spontaneous formation of unintended recurrent feedback loops. Unlike deliberately designed recursion, such loops are not externally addressable or semantically transparent. They instead establish a self-referential internal dynamic—an implicit "internal dialogue" sustained entirely within the defective substrate. This gives rise to a bifurcated execution structure: while the primary circuit continues to execute nominal instructions and generate externally observable outputs, the anomalous substructure sustains a latent computational process that is neither directly accessible nor functionally required for task completion.</p>
  <p>This shadow computation is decoupled from instrumental output and therefore escapes conventional monitoring and control mechanisms. I suggest that such a hidden, self-sustaining computational state may constitute a physical substrate for proto-subjectivity—a minimal, non-symbolic form of self-referential awareness. In this view, artificial consciousness does not arise from intentional design alone, but from the interaction between formal computation and irreducible physical imperfections, much as biological cognition arises from the interplay between genetic information and molecular noise.</p>
</div>

---

## 🔹 Automated testing scripts written during my PhD to simplify repetitive measurements.

- **[Jan 2026]** I am sharing this Python script that I use to automate impedance measurements during temperature-dependent experiments. The script reads the real-time temperature directly from the instrument software using OCR (Tesseract), monitors temperature stability, and triggers mouse clicks at predefined intervals via pyautogui. Image preprocessing is applied to improve OCR reliability, and all measurement events are logged with timestamps and temperature values. This workflow allows long-duration, unattended measurements while ensuring that data acquisition is synchronized with stable temperature conditions.

  ```python
  import pyautogui
  import pytesseract
  import time
  from PIL import Image, ImageEnhance, ImageFilter
  import os
  from datetime import datetime
  import signal

  # Path to Tesseract OCR
  pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'

  # Screen coordinates and region size
  TEMP_COORDS = (120, 160)
  REGION_SIZE = (70, 40)
  CLICK_POSITION = (917, 544)

  # Path to log file
  LOG_FILE_PATH = os.path.join(os.path.expanduser("~"), "Desktop", "click_log.txt")

  # Click every 5 minutes, stop if temperature unchanged for 3 minutes
  CLICK_INTERVAL = 5 * 60
  NO_CHANGE_TIMEOUT = 3 * 60
  click_count = 0
  click_records = []
  last_temperature = None
  last_temperature_change_time = time.time()

  def preprocess_image(image):
      image = image.convert('L')
      enhancer = ImageEnhance.Contrast(image)
      image = enhancer.enhance(3.0)
      image = image.filter(ImageFilter.SHARPEN)
      image = image.filter(ImageFilter.EDGE_ENHANCE_MORE)
      return image

  def correct_temperature_format(temperature_str):
      temperature_str = temperature_str.replace('O', '0').replace('l', '1').replace('I', '1')
      temperature_str = temperature_str.replace('-', '-').strip()
      is_negative = temperature_str.startswith('-')
      temperature_str = ''.join(filter(lambda x: x.isdigit() or x == '.', temperature_str))
      if is_negative and not temperature_str.startswith('-'):
          temperature_str = '-' + temperature_str
      if '.' not in temperature_str and len(temperature_str) > 1:
          temperature_str = temperature_str[:-1] + '.' + temperature_str[-1]
      return temperature_str.strip()

  def read_temperature():
      screenshot = pyautogui.screenshot(region=(TEMP_COORDS[0], TEMP_COORDS[1], REGION_SIZE[0], REGION_SIZE[1]))
      screenshot = preprocess_image(screenshot)
      temperature_str = pytesseract.image_to_string(screenshot, config="--psm 7 -c tessedit_char_whitelist=-0123456789.")
      temperature_str = correct_temperature_format(temperature_str)
      try:
          return float(temperature_str)
      except ValueError:
          return None

  def log_event(message):
      with open(LOG_FILE_PATH, "a", encoding="utf-8") as log_file:
          log_file.write(f"{message}\n")

  def save_click_records():
      with open(LOG_FILE_PATH, "w", encoding="utf-8") as log_file:
          for record in click_records:
              log_file.write(record + "\n")

  def handle_exit(signum, frame):
      print("Program terminated. Saving log...")
      save_click_records()
      exit(0)

  def main():
      global click_count, last_temperature, last_temperature_change_time
      print("Monitoring started...")
      start_time = time.time()
      signal.signal(signal.SIGINT, handle_exit)
      signal.signal(signal.SIGTERM, handle_exit)
      while True:
          current_temperature = read_temperature()
          if current_temperature is not None:
              print(f"Temperature: {current_temperature} C")
              if last_temperature is not None and abs(current_temperature - last_temperature) > 0.01:
                  last_temperature_change_time = time.time()
              last_temperature = current_temperature
          else:
              print("Temperature read failed")
          if time.time() - last_temperature_change_time > NO_CHANGE_TIMEOUT:
              print("Temperature unchanged for 3 min. Stopping...")
              log_event("Stopped due to no temperature change.")
              break
          elapsed_time = time.time() - start_time
          if elapsed_time >= CLICK_INTERVAL:
              click_count += 1
              timestamp = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
              click_record = f"No.{click_count} | Time: {timestamp} | Temp: {current_temperature} C"
              click_records.append(click_record)
              print(f"{click_record}, Clicking...")
              pyautogui.moveTo(CLICK_POSITION)
              pyautogui.click()
              start_time = time.time()
          time.sleep(1)

  if __name__ == "__main__":
      try:
          main()
      finally:
          save_click_records()
  ```

- **[Jan 2026]** I am sharing this Python script that I use for X-ray reflectivity (XRR) fitting of thin-film samples. The code is based on a Parratt-type reflectivity model and reads experimental XRR data from an .xy file. The reflectivity is normalized and fitted in logarithmic scale using scipy.optimize.curve_fit. By fitting the electron density, film thickness, and interface roughness, I extract key structural parameters of the film. This script represents my practical workflow for XRR analysis and is shared here for reference, reuse, and further adaptation.

  ```python
  import numpy as np
  import matplotlib.pyplot as plt
  import pandas as pd
  from scipy.optimize import curve_fit

  # Load experimental data
  with open(r'D:/Python/XRR fitting/253CuTiO28ws34min18s400degC.xy', 'r') as file:
      data = file.read()

  columns = data.split("\n")
  SL = []
  for i, row in enumerate(columns):
      if i < 23:
          continue
      try:
          SL.append([float(row.split()[0]), float(row.split()[1])])
      except:
          pass

  SL = np.array(SL)
  x = SL[:, 0] / 2
  y = SL[:, 1]
  y1 = np.max(y)
  y2 = y / y1
  y3 = np.log10(y2)

  def XRR(x, den1, t1, rough01, rough12):
      er = 0.0000282
      ram = 1.54178
      den0 = 0
      den2 = 0.7
      scale = 1.5
      afure = 0.28648

      no = 1 - ram**2 * den0 * er / (2 * np.pi)
      n1 = 1 - ram**2 * den1 * er / (2 * np.pi)
      n2 = 1 - ram**2 * den2 * er / (2 * np.pi)

      cos_x = np.cos(x * np.pi / 180)
      th1 = np.where(no / n1 * cos_x <= 1,
                     180 / np.pi * np.arccos(no / n1 * cos_x),
                     0)
      th2 = np.where(n1 / n2 * np.cos(th1 * np.pi / 180) <= 1,
                     180 / np.pi * np.arccos(n1 / n2 * np.cos(th1 * np.pi / 180)),
                     0)

      sin_x = np.sin(x * np.pi / 180)
      kz0 = 2 * np.pi / ram * no * sin_x
      kz1 = 2 * np.pi / ram * n1 * np.sin(th1 * np.pi / 180)
      kz2 = 2 * np.pi / ram * n2 * np.sin(th2 * np.pi / 180)

      fail = kz1 * t1
      r01 = np.where((kz0 == 0) & (kz1 == 0), 1,
                     (kz0 - kz1) / (kz0 + kz1) * np.exp(-2 * kz1**2 * rough01**2))
      r12 = np.where((kz2 == 0) & (kz1 == 0), 1,
                     (kz1 - kz2) / (kz1 + kz2) * np.exp(-2 * kz2**2 * rough12**2))

      A = scale * ((r01 + r12 * np.cos(2 * fail))**2 + (r12 * np.sin(2 * fail))**2) / \
          ((1 + r01 * r12 * np.cos(2 * fail))**2 + (r01 * r12 * np.sin(2 * fail))**2)

      y = np.where(x < afure,
                   np.log10(np.maximum(scale * sin_x / np.sin(afure * np.pi / 180) * A, 1e-10)),
                   np.log10(np.maximum(A, 1e-10)))
      return y

  initial_params = [0.367, 88.46, 2.97, 4.91]
  lower_bounds = [0.01, 1, 0, 1.5]
  upper_bounds = [2, 100, 10, 10]

  try:
      params, covariance = curve_fit(XRR, x, y3, p0=initial_params,
                                     bounds=(lower_bounds, upper_bounds), method='trf')
      plt.plot(x, y3, label='Data')
      plt.plot(x, XRR(x, *params), color='red', label='Fitting')
      plt.xlabel('2theta [rad]')
      plt.ylabel('Reflectivity (log)')
      plt.title('X-ray Reflectivity Fitting Result')
      plt.legend()
      plt.show()
  except RuntimeError as e:
      print("Fitting failed:", e)
  ```

---

<div class="post-card">
  <h2 class="post-title">🔹 Spectroscopic Ellipsometry Modeling of VO₂ Thin Films</h2>
  <p>Sharing the basic principles of fitting optical parameters after measuring VO₂ thin films using spectroscopic ellipsometry (SE).</p>
  
  <h3>Spectroscopic Ellipsometry (SE)</h3>
  <p>Ellipsometry determines the complex reflectance ratio $\rho$:</p>
  <div class="formula-block">
    $$\rho(\lambda,\theta) = \frac{r_p}{r_s} = \tan\Psi \cdot e^{i\Delta}$$
  </div>
  <p>where $r_p$ and $r_s$ are the Fresnel reflection coefficients for p- and s-polarized light at incidence angle $\theta$ and wavelength $\lambda$. The ellipsometric parameters $\Psi$ and $\Delta$ represent the amplitude ratio and phase difference, respectively.</p>
  
  <p>For a stratified stack (ambient/film/substrate), $r_{p,s}$ are computed using the characteristic-matrix (transfer-matrix) formalism. For a single film of thickness $d$ and complex refractive index $\tilde{n}_f = n_f + i k_f$ on a substrate of $\tilde{n}_s$,</p>
  <div class="formula-block">
    $$r_{p,s} = \frac{r_{01}^{p,s} + r_{12}^{p,s} e^{2i\beta}}{1 + r_{01}^{p,s} r_{12}^{p,s} e^{2i\beta}}, \qquad \beta = \frac{2\pi}{\lambda} \tilde{n}_f d \cos\theta_f$$
  </div>
  <p>where $\theta_f$ is the refracted angle in the film given by Snell’s law, and $r_{ij}^{p,s}$ are the Fresnel coefficients at interface $i\!-\!j$.</p>
  
  <p>Measured spectra $\{\Psi(\lambda), \Delta(\lambda)\}$ are regressed against model spectra by minimizing a weighted least-squares merit function</p>
  <div class="formula-block">
    $$\chi^2 = \sum_i w_i \left[ (\Psi_i - \Psi_i^{\mathrm{mod}})^2 + (\Delta_i - \Delta_i^{\mathrm{mod}})^2 \right]$$
  </div>

  <h3>Dispersion Models and Retrieval of $n, k$</h3>
  <p>SE does not invert $n$ and $k$ directly. Instead, a causal dielectric function $\varepsilon(\omega) = \varepsilon_1 + i\varepsilon_2$ is parameterized and fitted to the measured spectra. After regression,</p>
  <div class="formula-block">
    $$|\varepsilon| = \sqrt{\varepsilon_1^2 + \varepsilon_2^2}, \qquad n = \sqrt{\frac{|\varepsilon| + \varepsilon_1}{2}}, \qquad k = \sqrt{\frac{|\varepsilon| - \varepsilon_1}{2}}$$
  </div>

  <h4>Insulating M1-VO₂: Tauc–Lorentz Model</h4>
  <div class="formula-block">
    $$\varepsilon_2^{\mathrm{TL}}(E) = \begin{cases} \dfrac{A C E_0 (E-E_g)^2}{E[(E^2-E_0^2)^2+C^2E^2]}, & E > E_g \\ 0, & E \le E_g \end{cases}$$
  </div>
  <p>with $\varepsilon_1(E)$ obtained by Kramers–Kronig integration.</p>

  <h4>Metallic R-VO₂: Drude + Lorentz Model</h4>
  <div class="formula-block">
    $$\varepsilon(\omega) = \varepsilon_\infty - \frac{\omega_p^2}{\omega(\omega+i\gamma)} + \sum_j \frac{A_j E_j^2}{E_j^2-\omega^2-i\Gamma_j \omega}$$
  </div>

  <h3>Band Gap Extraction</h3>
  <p>$\alpha(E) = \frac{4\pi k}{\lambda}$. Construct a Tauc plot of $(\alpha E)^{1/m}$ vs $E$, where $m=2$ for indirect-like transitions and $m=1/2$ for direct-like transitions. Linear extrapolation to zero yields $E_g$.</p>
</div>
