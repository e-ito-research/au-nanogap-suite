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
    Zenodo. https://doi.org/10.5281/zenodo.[ZENODO_ID]

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
- Watanabe & Takigawa, Appl. Surf. Sci. (2023)
- Zukauskaite et al., J. Appl. Phys. 114, 243516 (2013)
- Johnson & Christy, Phys. Rev. B 6, 4370 (1972)

## License

CC BY 4.0 - Free to use with attribution.
