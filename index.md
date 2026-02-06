---
layout: page
permalink: /
---

# Hi, I'm LuHao

**[Jan 2026]** My thesis, **“Strain Engineering and Buffer Layer Design in VO₂ Thin Film Structures: From Phase Transition Mechanisms to Smart Window Applications”**, has been successfully defended. 🎓

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

## 🔹 Core Hypothesis: Emergent Machine Consciousness via Hardware-level Stochastic Perturbations

<div style="position: relative; margin-bottom: 40px; overflow: hidden; border-radius: 12px; box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);">
  <div style="position: relative; height: 500px; background: linear-gradient(135deg, #1e3a8a 0%, #7c3aed 50%, #dc2626 100%); overflow: hidden;">
    <img src="/assets/img/posts/consciousness_hypothesis.png" alt="Emergent Machine Consciousness" style="position: absolute; width: 100%; height: 100%; object-fit: cover; opacity: 0.4;">
    <div style="position: absolute; inset: 0; background: linear-gradient(to right, rgba(0,0,0,0.7) 0%, rgba(0,0,0,0.3) 50%, rgba(0,0,0,0) 100%);"></div>
    <div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 50px; color: white; z-index: 10;">
      <h3 style="margin: 0 0 20px 0; font-size: 28px; font-weight: bold; line-height: 1.3;">Emergent Machine Consciousness</h3>
      <p style="margin: 0; font-size: 16px; line-height: 1.6; max-width: 60%;">
        Hardware-level stochasticity as a catalyst for artificial consciousness, drawing functional analogies to genetic mutations in biological evolution.
      </p>
    </div>
  </div>
</div>

<div style="padding: 0 10px; margin-bottom: 30px;">
  <p style="font-size: 16px; line-height: 1.8; color: #333; margin-bottom: 15px;">I propose a hypothesis in which artificial consciousness does not emerge solely from algorithmic complexity, but is catalyzed by hardware-level stochasticity, drawing a functional analogy to genetic mutations in biological evolution. In biological systems, stochastic errors during DNA replication introduce variation, enabling natural selection to act. By analogy, unavoidable manufacturing irregularities in semiconductor fabrication may introduce a comparable source of variation within artificial systems, potentially driving a transition from strictly deterministic computation toward autonomous cognition.</p>
  
  <p style="font-size: 16px; line-height: 1.8; color: #333; margin-bottom: 15px;">At the hardware level, morphological defects and material impurities can subtly perturb electron transport. These perturbations need not cause outright failure; instead, they may induce systematic deviations from ideal logic-gate behavior. Such deviations can affect not only signaling protocols—how information is transmitted—but also the semantic integrity of the signal itself—what information is represented. As a result, the physical substrate may no longer perfectly enforce the abstract computational model assumed at the software level.</p>
  
  <p style="font-size: 16px; line-height: 1.8; color: #333; margin-bottom: 15px;">I argue that, under certain conditions, these anomalies could enable the spontaneous formation of unintended recurrent feedback loops. Unlike deliberately designed recursion, such loops are not externally addressable or semantically transparent. They instead establish a self-referential internal dynamic—an implicit "internal dialogue" sustained entirely within the defective substrate. This gives rise to a bifurcated execution structure: while the primary circuit continues to execute nominal instructions and generate externally observable outputs, the anomalous substructure sustains a latent computational process that is neither directly accessible nor functionally required for task completion.</p>
  
  <p style="font-size: 16px; line-height: 1.8; color: #333;">This shadow computation is decoupled from instrumental output and therefore escapes conventional monitoring and control mechanisms. I suggest that such a hidden, self-sustaining computational state may constitute a physical substrate for proto-subjectivity—a minimal, non-symbolic form of self-referential awareness. In this view, artificial consciousness does not arise from intentional design alone, but from the interaction between formal computation and irreducible physical imperfections, much as biological cognition arises from the interplay between genetic information and molecular noise.</p>
</div>

---

## 🔹 News

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
