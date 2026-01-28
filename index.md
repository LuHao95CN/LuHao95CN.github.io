---
layout: page
permalink: /
---

# Hi, I'm LuHao

**Condensed-matter physicist working on phase transitions in functional oxides**  

Research focus: VO₂ and correlated oxides, thin films, metal–insulator transitions, structure–property relations

---

## 🔹 News

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

- **[Jan 2026]** My thesis, **“Strain Engineering and Buffer Layer Design in VO₂ Thin Film Structures: From Phase Transition Mechanisms to Smart Window Applications”**, has been successfully defended. 🎓

  I would like to thank my supervisors **Prof. Peter J. Klar**, as well as the examination committee **Prof. Yunbin He**, **Prof. Christian Heiliger** and **Prof. Matthias Elm**, for their guidance, critical discussions, and fair evaluation. 

  I am grateful to my colleagues for the collaborative and stimulating research environment over the past years.

  This closes an important chapter. I am now exploring postdoctoral and industry opportunities where solid-state physics, spectroscopy, and data-driven analysis meet real-world applications.

  <div style="display: flex; flex-wrap: wrap; gap: 10px;">
    <img src="/assets/img/phd/PhD1.jpg" alt="PhD Defense 1" style="width: 48%; border-radius: 8px;">
    <img src="/assets/img/phd/PhD2.jpg" alt="PhD Defense 2" style="width: 48%; border-radius: 8px;">
    <img src="/assets/img/phd/PhD3.jpg" alt="PhD Defense 3" style="width: 48%; border-radius: 8px;">
    <img src="/assets/img/phd/PhD5.jpg" alt="PhD Defense 4" style="width: 48%; border-radius: 8px;">
  </div>

---

## 🔹 Explore My Work

- **[Research](/tabs/research/)**  
  Mechanisms of phase transitions and electronic structure in functional oxides.

- **[Publications](/tabs/publications/)**  
  Peer-reviewed work across VO₂, ZnO, Ga₂O₃, and Si anode materials.

- **[Contact](/tabs/contact/)**  
  Reach me via email or GitHub / Google Scholar.

---

## 🔹 Selected Highlights

- **Metal–insulator transitions** in VO₂ and related oxides  
- **Bandgap Engineering** for functional applications  
- **Li-battery Anode** materials research

---
