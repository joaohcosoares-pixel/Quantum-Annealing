---
marp: true
theme: gaia --
class: invert
paginate: true
math: mathjax
header: 'Física Estatística — Quantum Annealing'
footer: 'Soares J. H. C. | IF-UFG'
---

<!-- Tempo: 0:00 - 0:30 -->
# Quantum Annealing

**João Henrique Costa Soares**  
Física Estatística — IF-UFG

---

<!-- Tempo: 0:30 - 1:45 -->
## 1. Quantum Annealing vs. Simulated Annealing

**Meta:** encontrar o estado fundamental em paisagens rugosas (otimização NP-difícil). <!--[cite: 4, 25, 46] -->

| | Simulated Annealing (SA) | Quantum Annealing (QA) |
| :--- | :--- | :--- |
| **Flutuação** | Térmica ($e^{-\Delta E/k_B T}$) <!--[cite: 5] --> | Quântica (tunelamento) <!--[cite: 15, 25] --> |
| **Controle** | Temperatura $T(t) \to 0$ <!--[cite: 16] --> | Campo transverso $\Gamma(t) \to 0$ <!--[cite: 16] --> |
| **Decaimento** | Logarítmico ($c/\ln t$) <!--[cite: 15, 27] --> | Lei de potência <!--[cite: 40, 41] --> |

---

<!-- Tempo: 1:45 - 3:00 -->
## 2. Onde o QA Vence: Tunelamento Quântico

- **Escape térmico (SA):** $P_{\text{SA}} \sim \exp(-N / T_c)$ — depende só da **altura**. <!--[cite: 41, 46] -->
- **Tunelamento (QA):** $P_{\text{QA}} \sim \exp\!\left(-\sqrt{N}\,w / \Gamma_q\right)$ — depende da altura **e da largura $w$**. <!--[cite: 41, 46] -->
- **Regime vencedor:** barreiras **altas e estreitas** e platôs largos. <!--[cite: 25, 46, 89, 90] -->
- **Experimento ($\text{LiHo}_{0.44}\text{Y}_{0.56}\text{F}_4$):** relaxação até **$30\times$ mais rápida** que o resfriamento térmico. <!--[cite: 40] -->

---

<!-- Tempo: 3:00 - 4:30 -->
<style scoped>
section {
  padding: 10px;
}
</style>

<iframe src="./benchmarkSAQA.html" style="width: 100%; height: 700px; border: none; border-radius: 8px;"></iframe>

---

<!-- Tempo: 4:30 - 5:45 -->
## 4. Modelo de Ising com Campo Transverso (TFIM)

$$\mathcal{H}(t) = \underbrace{-\sum_{i<j} J_{ij}\sigma_i^z \sigma_j^z - h\sum_{i=1}^N \sigma_i^z}_{\mathcal{H}_0 \text{ (Clássico)}} \;-\; \underbrace{\Gamma(t)\sum_{i=1}^N \sigma_i^x}_{\text{Quântico}}$$

- **$\mathcal{H}_0$ (base $\sigma^z$):** codifica a função de custo e a frustração via $J_{ij}$. <!--[cite: 16, 28] -->
- **Campo transverso ($\sigma^x$):** não comuta com $\mathcal{H}_0$; gera *spin flips* e superposição. <!--[cite: 16, 25] -->

---

<!-- Tempo: 5:45 - 7:15 -->
## 5. Como o QA Resolve o Modelo

1. **Início ($\Gamma \gg |J_{ij}|$):** superposição uniforme de todos os $2^N$ estados: <!--[cite: 16, 33, 59] -->
   $$|\psi(0)\rangle = |+\rangle^{\otimes N}$$
2. **Evolução:** reduz-se $\Gamma(t) \to 0$ sob a Equação de Schrödinger ($T=0$). <!--[cite: 16] -->
3. **Condição Adiabática:** mantém o estado fundamental se $t_f \gg \Delta_{\min}^{-2}$. <!--[cite: 33, 55] -->
4. **Kadowaki & Nishimori ($N=8$, $\Gamma=T=3/\sqrt{t}$):** $P_{\text{QA}}(t) > P_{\text{SA}}(t)$. <!--[cite: 16, 17, 18] -->

---

<!-- Tempo: 7:15 - 8:30 -->
## 6. Aplicações

- **Otimização Combinatória:** Caixeiro Viajante (TSP), MAX-CUT, Exact Cover e Particionamento. <!--[cite: 34, 90, 91] -->
- **Matéria Condensada:** vidros de spin (EA, SK) e ímãs frustrados. <!--[cite: 28, 34, 47] -->
- **Machine Learning:** *Quantum Boosting*, Máquinas de Boltzmann e PageRank. <!--[cite: 65, 93] -->
- **Química e Hardware:** energias moleculares; chips supercondutores (D-Wave) e fotônicos. <!--[cite: 46, 47, 104] -->

---

<!-- Tempo: 8:30 - 10:00 -->
## 7. Conclusões

- **Força:** supera o SA em barreiras altas/estreitas com arrefecimento em lei de potência. <!--[cite: 40, 41, 46] -->
- **Limite:** não resolve NP-difíceis em tempo polinomial — transições de 1ª ordem fecham $\Delta_{\min}$ exponencialmente. <!--[cite: 40, 53, 88] -->
- **Fronteira:** termos não-estoquásticos, catalisadores e evolução diabática. <!--[cite: 54, 100, 101, 103] -->
- **Uso de IA:** triagem bibliográfica, simulação 1D (`benchmarkSAQA.html`) e síntese dos slides. <!--[cite: 3] -->

---

## 8. Referências

- Kirkpatrick, S., Gelatt, C. D., & Vecchi, M. P. (1983). *Science*, 220, 671. <!-- -->
- Kadowaki, T., & Nishimori, H. (1998). *Phys. Rev. E*, 58, 5355. <!-- -->
- Das, A., & Chakrabarti, B. K. (2008). *Rev. Mod. Phys.*, 80, 1061. <!-- -->
- Albash, T., & Lidar, D. A. (2018). *Rev. Mod. Phys.*, 90, 015002. <!-- -->
- Chakrabarti, B. K. et al. (2022). *Phil. Trans. R. Soc. A*, 381, 20210419. <!-- -->