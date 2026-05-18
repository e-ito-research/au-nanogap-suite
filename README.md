# Research Design Tools for Quantum Devices

Browser-based calculators for quantum device design.
No installation required.

## Tools

| Tool | Description |
|------|-------------|
| Detector Designer | Optimize Au nanogap detector circuits (minimize tau, maximize SNR) |
| Qubit Noise Designer | Reduce qubit 1/f noise via plasmonic TLS desorption |
| LiNbO3 Cryogenic Stress Calculator | Anisotropic thermoelastic stress at 4K, ScAlN optimization |

## Usage

Open `index.html` in a browser, or visit:
https://e-ito-research.github.io/au-nanogap-suite/

## How to Cite

If you use these tools in your research, please cite:

    e.ito.research (2026). Research Design Tools for Quantum Devices.
    Zenodo. https://doi.org/10.5281/zenodo.20254940

## Disclaimer

This tool is based on established physical models.
Users should verify results with their own experimental
data before making engineering decisions.

- DIET model: calibrated against de Graaf et al. (2018)
- SAW phonon model (coupling_eff): theoretical estimate,
  NOT yet experimentally verified. Use with caution.
- LiNbO3 elastic constants: Weis & Gaylord (1985)
- Bond limit 23 MPa: Watanabe & Takigawa (2023)

## References

- de Graaf et al., Nature Communications 9, 1143 (2018)
- Weis & Gaylord, Appl. Phys. A 37, 191-203 (1985)
- K. Watanabe & R. Takigawa, Appl. Surf. Sci. 620, 156666 (2023). DOI: 10.1016/j.apsusc.2023.156666
- S. Zhang, W.Y. Fu, D. Holec, C.J. Humphreys, M.A. Moram, J. Appl. Phys. 114, 243516 (2013). DOI: 10.1063/1.4848036
- Johnson & Christy, Phys. Rev. B 6, 4370 (1972)
- Ciprian, Mihalic, Lüttich, Hörich, Wade, Christian, Dadgar, Ambacher, Appl. Phys. Lett. 124, 052203 (2024). DOI: 10.1063/5.0176082 (ScN CTE: 6.61±0.60 ppm/K)
- Lu et al., APL Mater. 6, 076105 (2018) (ScAlN CTE: 4.18–4.65 ppm/K, all Sc%; contradicts CTE-matching prediction)

## License

CC BY 4.0 - Free to use with attribution.
