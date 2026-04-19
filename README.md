# The Conversion Floor

**Tokens, Modal Tokens, and the Two-Source Noise Condition for Photonic AI Acceleration**

Nils Haaland · Solbakken Research Initiative · April 2026 · Preprint

→ [**Download v11 PDF**](./conversion_floor_v11.pdf)
→ [**Landing page**](https://bluebflatminor.github.io/conversion-floor/)

---

## Thesis

The discrete token is a hardware artifact of electronic accelerators, not a principled unit of meaning. Architectural pressure is already relocating discreteness from the computational core to the system boundary. Photonic matrix-vector multiplication is a candidate substrate for the hybrid primitive this trajectory requires — the *modal token* — but its viability is gated by a two-dimensional noise condition defined by weight memory stability (δₘ) and modulation noise (σ_mod) as physically distinct and independently variable axes.

## The core argument

Under the simplest separable noise model, the ADC precision requirement satisfies a two-axis constraint:

```
b ≥ max( f(δ_m), g(σ_mod) )
```

Appendix A of the paper derives this as the worst-case approximation of a full SNR constraint under separability. The γ cross-term in the variance decomposition captures grain-boundary coupling between the two axes in the ferroelectric-graphene stack — a structural consequence of the shared interface, absent in TFLN and silicon-photonic architectures.

A secondary consequence is the **phase-fragile similarity regime**: for interference-based similarity, σ_mod does not merely set a floor for numerical precision. It sets a floor for semantic fidelity. Near a destructive-interference condition, small phase errors produce step-function flips in similarity value, not gradual degradation.

## What's new in v11

§3.4 — the first back-of-envelope placement of two deployed commercial systems on the (δₘ, σ_mod) map, using only public specifications and published noise literature. Error bars are a factor of 3–10; the purpose is structure, not precision.

| System | δₘ | σ_mod | Tax mechanism |
|---|---|---|---|
| **Lightmatter Envise** | high | low | Run-time analog gain control (operational) |
| **Q.ANT NPS (TFLN)** | low | moderate | Post-fabrication annealing (one-time) |

Neither system appears, from public data, to be operating natively inside the Goldilocks window without compensation.

## Named unknowns

Eight explicit open questions are collected in §8 of the paper. The two hardest:

- **Unknown One-A** *(theoretical)* — Does interference-based similarity offer complexity advantage over O(n²) attention? The sub-problem is softmax-equivalent normalization without reintroducing quadratic cost.
- **Unknown Seven** *(empirical)* — Does any deployed photonic MVM system operate inside the Goldilocks window without compensation?

Full list: One, One-A, Two, Three, Four, Five, Six, Seven, Eight. See §8 of the PDF.

## Scope

**Claims:** a two-dimensional noise envelope, derivable from SNR, with published-data anchors on both axes.

**Does not claim:** the modal token is formally specified, implemented, or demonstrated. The §3.4 placements are structural, not numerical. Unknown One-A is not resolved.

## Extensions

- **[The Mortal Token](https://github.com/bluebflatminor/mortal-token)** — coherence-gated persistence filter; introduces Unknowns Nine–Eleven and extends the floor to a third axis h(m, τ).

## Related work

- **[Graphene Integration Route Selection](https://github.com/bluebflatminor/graphene-photonic-memory-routes)** — Bayesian Monte Carlo over 10 routes for a 64×64 MVM tile; quantitative anchor for §6.

## Citation

```
Haaland, N. The Conversion Floor: Tokens, Modal Tokens, and the
Two-Source Noise Condition for Photonic AI Acceleration.
Solbakken Research Initiative, April 2026.
github.com/bluebflatminor/conversion-floor
```

## Contact

Nils Haaland · nhaaland@yahoo.com
[github.com/bluebflatminor](https://github.com/bluebflatminor)

## License

MIT — see [LICENSE](./LICENSE).
