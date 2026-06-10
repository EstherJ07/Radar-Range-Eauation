# Radar Range Equation
### Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Scilab programming.

### Theory:
The Radar Range Equation is a key relationship used in radar system design to determine the maximum distance (range) at which a radar can detect a target.

#### It is expressed as:

<img width="365" height="423" alt="image" src="https://github.com/user-attachments/assets/0212734c-c95c-4f19-bf3c-e1d487a4cd7f" />

### Algorithm:
1.Initialize constants: λ (wavelength) = 0.03 m σ (radar cross section) = 1 m²

2.Vary each parameter while keeping the others constant: Pt: 0.1 → 10 Gt: 1 → 50 Pm: 1e⁻¹⁵ → 1e⁻¹⁰

3.Compute maximum range using: R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼

4.Plot the following: Pt vs Rmax Gt vs Rmax Pm vs Rmax

### Procedure:
1.Refer to the Algorithm and write the Scilab code for the experiment.

2.Open Scilab on your system.

3.Create a New Editor File: Go to File → New → Script.

4.Type Your Code in the editor window.

5.Save the File with a suitable name (e.g., radar_range.sce).

6.Execute the Code: Press F5 or click Execute → File with echo.

7.If Any Errors Occur: Review and correct the code. Save and run it again until it executes successfully.

### Program:
~~~
Gt_dB = 30
Gr_dB = 30
lambda = 0.03
sigma = 1
Gt = 10^(Gt_dB/10)
Gr = 10^(Gr_dB/10)
R_km = 1:1:100
R = R_km * 1000
Pt = 100 + 10 * R_km
Pr = (Pt .* Gt .* Gr .* lambda^2 .* sigma) ./ (((4 * %pi)^3) .* (R.^4))
Pt_dB = 10 * log10(Pt)
Pr_dB = 10 * log10(Pr)
subplot(2,1,1)
plot(R_km, Pt_dB)
xlabel("Radar Range (km)")
ylabel("Transmitted Power (dB)")
title("Transmitted Power vs Radar Range")
subplot(2,1,2)
plot(R_km, Pr_dB)
xlabel("Radar Range (km)")
ylabel("Received Power (dB)")
title("Received Power vs Radar Range")
~~~
### Output:

<img width="760" height="720" alt="image" src="https://github.com/user-attachments/assets/903ab052-796a-4f48-89f1-2ec714876fa2" />

### Result:
Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.
