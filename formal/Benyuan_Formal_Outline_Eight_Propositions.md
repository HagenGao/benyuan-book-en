[Benyuan_Formal_Outline_Eight_Propositions.md](https://github.com/user-attachments/files/29668143/Benyuan_Formal_Outline_Eight_Propositions.md)
# Benyuan Formal Outline: Eight Propositions

**— Technical companion to *Benyuan: Rewriting the Foundation of the Economy* (published separately)**

---

## What this document is, and is not

The book keeps, deliberately, exactly one formula — that is its contract with the general reader, and this document does not break it. But the book contains a set of **theorem-shaped claims** that until now had only prose arguments behind them. This outline takes the eight most load-bearing of them and writes them as formal propositions: where a proof exists, the proof is given; where only a conditional result can be had, the assumptions are stated in the open.

One honest convention runs through everything here, the same discipline the book practices: every result is labeled with its true status — **Proof** (holds rigorously under the stated axioms and assumptions), **Proof sketch** (skeleton complete, details left open), or **Inference** (direction clear, further work required). At the end, the document lists explicitly what it has **not** proven.

First, what the formalization actually bought, in two kinds. Two results are **unconditional structural properties**: historical gaps carry no interest and therefore never compound — they are dead entries that do not breed (Corollary 2.1); and the sentence written into the book to forbid castes — "κ is the same number for every person" — turns out, once formalized, to be a hard anti-collusion ceiling (Proposition 6a). Two more are **conditional confirmations**: anchoring population regulation on the birth side widens the stable gain region by roughly an order of magnitude compared with anchoring on the total (Proposition 5); and interest-free accounting does not violate dynamic efficiency in a Samuelson-style toy model (Proposition 8b). This outline does not claim that mathematics has "proven the book correct." What it does is push the book's most attackable mechanism claims to the stage of being **formalizable, testable, and provable further**. Where each line of defense stands, and on what conditions, is stated item by item below.

Notation: individual $i$ is born at $\tau_i$ and dies at $T_i$; account balance $b_i(t)$, with $b_i(\tau_i)=0$; social total ledger $S(t)$; social average output flow $\bar Y(t)$ and average consumption flow $\bar C(t)$; the democratically set survival-floor proportion $s$ and capability-credence ceiling $\kappa$ (both uniform for the whole population); the developmental drawing limit follows the composite formula of the book's Chapter 4:

$$L_i^{\mathrm{dev}}(t) = \max\{ 0,\ \int_t^{T_i(t)} [\min(\rho_i(\tau)\hat E_i(\tau),\ \kappa(\tau)\bar Y(\tau)) - \max(\hat C_i(\tau),\ s(\tau)\bar C(\tau))]\,d\tau - B_i^{\mathrm{dev}}(t) \}.$$

Here $B_i^{\mathrm{dev}}$ counts developmental draws only, never survival-floor draws (the distinction the book makes in 4.7/4.8).

---

## Axioms

- **A1 (Transfer axiom)**: Every economic operation inside the system is an equal-amount transfer — any operation that increases one account by $x$ decreases another (an individual's, or the total ledger) by $x$. There is no issuance operation.
- **A2 (Birth axiom)**: A new individual joins with $b_i(\tau_i)=0$.
- **A3 (End-of-life settlement axiom)**: At an individual's death, their balance (positive or negative) transfers at once into the total ledger, i.e. $S \leftarrow S + b_i(T_i)$, and the account is closed.
- **A4 (No-interest axiom)**: No balance (individual or total) grows or decays on its own over time.
- **A5 (Record-equals-settlement axiom)**: A fulfillment (income) record exists if, and only if, a real, settled transfer took place — the payer's account reduced by exactly that amount. There is no "fulfillment" with a record and no transfer behind it.

A5 is not a new design. It abstracts into an axiom the principle Chapter 9 of the book names "the ledger is fact" — and the force of Propositions 3 and 6 rests entirely on it.

---

## Proposition 1 (Conservation invariant) [Proof]

**Proposition**: Under A1–A3, writing $A(t)$ for the set of individuals alive at time $t$,

$$W(t) := \sum_{i \in A(t)} b_i(t) + S(t) \equiv 0.$$

**Proof**: $W(0)=0$. Under A1 every transfer moves the two parts of $W$ by equal and opposite amounts, so $\Delta W = 0$; under A2 the new term is zero; under A3 one term moves from the sum into $S$, so $\Delta W = 0$. Induction completes it. ∎

**Commentary**: The conservation law is not a policy target that must be defended; it is a **constructive property** of double-entry accounting. What it proves is conservation **under ledger closure** — it cannot be "violated," only "bypassed around the books" (off-ledger trades, black markets, off-book promises, falsified information). Every threat to conservation therefore reduces to a question of **ledger integrity** (the book's Chapter 9), not a question of economics. A5 is exactly where ledger integrity lands, formally, in this document.

---

## Proposition 2 (Sustainability criterion for the total ledger) [Proof (conditional)]

Let population be stationary (size $N$, annual death rate $\delta$, annual deaths $\delta N$). Among the dying, a share $q$ leave with an unbalanced gap, average gap $\bar d>0$; a share $1-q$ leave positive balances, average $\bar u\ge 0$, which flow back to the total ledger under no-inheritance. Define the **per-capita annual net absorption flow**

$$\varphi := \delta\,(q\bar d - (1-q)\bar u),$$

and the **per-capita distributable surplus rate** $\pi$: the per-capita flow of output remaining after the whole society's necessary consumption and the investment that keeps production going are covered. The statistical definition of $\pi$ must be fixed before any test — an unfixed definition makes the criterion untestable.

Beyond individual end-of-life gaps, the total ledger has a **second, independent absorption channel**: unrecovered advances left by failed innovation and by projects whose accounts never spread flat (the book's 4.4 and 10.4) — these pass through no one's death settlement; the total ledger catches them directly. Write their **per-capita annual net loss flow** as $\psi$. $\psi$ has no per-person structural cap of the kind $L_{\max}$ provides: its size depends on the quality of the gatekeeper's accounting and on how the staged-release regime of the book's 4.5 is enforced at project level (a single project's in-flight exposure is capped by the installment ceiling). A formal upper bound on $\psi$ is not given here; it is listed as open. The criterion below counts $\varphi$ and $\psi$ side by side.

**Assumptions**:
- **C1 (Conservative estimation)**: The limit formula's estimators are conservative at both ends — on the income side, expected realized output satisfies $\mathbb{E}[Y^{\mathrm{real}}] \ge \mathbb{E}[\min(\hat\rho\hat E, \kappa\bar Y)]$; on the consumption side, expected realized consumption satisfies $\mathbb{E}[C^{\mathrm{real}}] \le \mathbb{E}[\max(\hat C, s\bar C)]$.
- **C2 (Actuarially bounded)**: Lifespan distribution is bounded; the survival floor and care rules are set by bounded democratic parameters. Then the lifetime survival draw (including medical and incapacity care that bypasses the limit formula) has a conditional actuarial upper bound $d_{\mathrm{surv}}$.

The second source of individual gaps — developmental overdraft — **needs no extra assumption**: by Proposition 6a (whose proof uses only the structure of the limit formula and is not circular with this proposition), the developmental overdraft stock is capped per person, at every moment, by the structural hard ceiling $L_{\max}$. Note that the finiteness of $L_{\max}$ rests on lifespans, $\kappa$, and $s$ being bounded; if lifespans lengthen dramatically or the survival floor is raised for the long run, both $L_{\max}$ and $d_{\mathrm{surv}}$ must be re-estimated — they are functions of parameters, not constants of nature.

**Proposition 2**:
(i) In steady state, the per-capita real burden the living producers actually carry each year for end-of-life settlement equals $\varphi$ identically;
(ii) Under C1–C2, $\bar d \le d_{\max} := d_{\mathrm{surv}} + L_{\max}$ (worst case; under C1 the developmental part's expectation is further compressed by prediction error, far below $L_{\max}$), hence $\varphi \le \delta q\, d_{\max}$;
(iii) **Long-run $\varphi + \psi \le \pi$ is the core testable criterion of the system's sustainability**: when it holds, the burden is carried by the surplus flow and the burden rate is bounded; if $\varphi + \psi$ persistently and significantly exceeds $\pi$, the burden eats into necessary consumption or reproduction investment, and the system enters the unsustainable risk region.

**Proof**:
(i) Within a year, all change in $S$ comes from end-of-life settlement (under A1 ordinary trades do not change the split between $S$ and the sum of survivors' balances, unless one party to the trade is the total ledger itself — such operations are exactly the project advance and recovery flows counted by $\psi$, a separate item, never mixed into $\varphi$). Annual $\Delta S = \delta N[(1-q)\bar u - q\bar d] = -\varphi N$. By Proposition 1, the survivors' total balance changes by $+\varphi N$ per year. Balances are claims on society's real output: the living collectively hold $\varphi N$ more claims each year, whose counterpart is the lifetime net consumption of gap-leaving decedents, carried without compensation by the net output of the living (the positive-balance case carries the opposite sign and nets off automatically). Under stationary population this flow is constant, per-capita identically $\varphi$.
(ii) Gaps have only two sources: survival draws, bounded actuarially by C2 at $d_{\mathrm{surv}}$; developmental overdraft, bounded structurally by Proposition 6a at $L_{\max}$ (holding per person always, not a statistical property). Add them.
(iii) By A4, neither individual-gap stock nor project-gap stock compounds (Corollary 2.1), so the burden is a pure flow; adding the two and comparing against the surplus flow $\pi$ yields the two regions. The criterion is a flow condition, not an "if and only if" characterization — in the critical neighborhood of $\varphi$ and $\pi$, sustainability also depends on surplus volatility and the adjustment speed of the democratic parameters. ∎

**Corollary 2.1 (No-compounding dividend) [Proof]**: By A4, the book-entry stock of historical gaps generates no interest, so at any moment the **book-entry** intergenerational burden equals only the current flow (the sum of $\varphi$ and $\psi$), independent of the absolute size of the accumulated stock $S$.

**Commentary**: This is the structural divide between benyuan and the old world's sovereign debt — old debt rolls at compound interest, the burden exponentiating with the stock; benyuan's historical gap is a **dead entry** that does not breed. The honest boundary: Corollary 2.1 speaks of the book-entry burden; the **political tolerance and perceived intergenerational fairness** of the accumulated stock are questions outside the ledger, not covered here. Sustainability thereby collapses from a vague worry into one testable inequality, $\varphi + \psi \le \pi$: four numbers to track (the share of those unable to balance and their average gap, the survival-floor level, the net loss rate of failed projects, the surplus rate). If in a pilot $\varphi + \psi$ keeps closing on $\pi$ or passes it, the theory's sustainability claim is falsified — this is the quantitative form of the seventh prediction in the book's Appendix II.

**Policy knobs**: $s$ (the survival-floor proportion, democratically adjustable) directly controls $d_{\mathrm{surv}}$; $\pi$ is set by productivity. **Open problem**: the true distribution of $q$ can only come from evidence.

---

## Proposition 3 (Hard upper bound on strategic extraction) [Proof (under institutional conditions)]

Consider the strategic individual: "build a record to inflate $\hat\rho$, stretch the limit to its maximum, draw it to the top, then defect and lie flat" (the target of the book's 4.7). The crux: the danger is not how much can be drawn **after** defection, but how much was already drawn **before** it. Any theorem that caps only the post-defection increment never touches the main battlefield. So the first load-bearing wall of this proposition elevates the staged release of the book's 4.5 from narrative to institutional assumption:

- **B1′ (Hard staged-release regime)**: Developmental drawing has exactly two channels.
  (a) **Living-flow drawing**: rate capped at $\bar r$.
  (b) **Project installment drawing**: every installment must be tied to an inspectable stage target, asset, or service; a single installment's release is capped at $h$; the next installment does not release until the previous passes inspection; the moment the delivery record deteriorates, all new installments freeze.
  There is **no one-shot cash-out channel** for the developmental limit — the nominal limit is a rolling qualification to draw, not a withdrawable deposit.
- **B2 (Update lag)**: $\hat\rho_i$ updates on the true fulfillment record (in the sense of A5), with lag at most $\tau$.
- **B3 (Live recomputation)**: $L_i^{\mathrm{dev}}$ recomputes with $\hat\rho$ in real time; new draws are truncated by the $\max\{0,\cdot\}$.

**Definition (total extraction)**: Over the whole strategy (including before the defection time $t^{\star}$), the total developmental draw that is finally neither offset by real contribution nor matched by recoverable assets, and lands on the total ledger, is written $W$.

**Proposition 3**: Under A5 and B1′–B3, any lone-actor strategy's total extraction satisfies

$$W \le h + \bar r\,\tau.$$

**Proof**: Split all developmental draws standing against the individual at $t^{\star}$ into three blocks.
(1) **Inspected installments**: inspection means the corresponding stage output was really delivered (with settled, verified transfers as evidence under A5), or the corresponding asset remains occupied inside the system rather than destroyed — under the book's "occupied, not owned" arrangement, big assets are recoverable and redeployable. Neither case is a net loss to society; neither enters $W$. "Inspection" here must be **independent** inspection, grounded in real delivery, market uptake, or recoverable, redeployable asset value; if the inspection step itself is polluted by collusion (mutual "inspection"), the risk is no longer the lone-actor case and passes to Proposition 6's collusion-and-detection problem.
(2) **The in-flight installment**: by the sequential gating of B1′(b), at any moment at most one installment is released but uninspected, its amount capped by $h$. After defection it freezes; total loss at worst contributes at most $h$.
(3) **Living flow**: before $t^{\star}$, flow draws occur in step with real fulfillment (A5; if someone stopped truly fulfilling earlier, the definition of $t^{\star}$ moves forward accordingly), and do not enter $W$; after $t^{\star}$, B2 guarantees $\hat\rho$ is revised down within at most $\tau$, B3 truncates all new draws, and the window accumulates at most $\bar r\tau$.
Add the three blocks: $W \le h + \bar r\tau$. ∎

**Boundary statement (honesty clause)**: If the institution permits one-shot cash-out of the developmental limit, or permits releasing multiple installments without inspection, **this proposition fails** — the loss bound degrades to the total released, and the exposure is as large as the nominal limit. $h$ is not a descriptive phrase about "staged release"; it is a hard institutional constraint that must be strictly enforced. The entire force of this proposition is conditional on B1′ being enforced.

**Corollary 3.1 (Incentive side)**: If the individual's continuing value of staying in the system, $V$, satisfies $V > u(h + \bar r\tau)$ (where $u(\cdot)$ is an increasing function converting the extracted amount into utility), then the defection strategy is strictly dominated by honesty — the extraction payoff has a hard ceiling, while the loss of record and limit is counted over the rest of a life.

**Commentary**: The defense now has three policy screws: $h$ (single-installment cap), $\bar r$ (flow rate limit), $\tau$ (record update period — compressible to days on a digital ledger). The book's 4.5 states it in so many words: "Large drawdowns are released in stages, milestone by milestone, through the gatekeeper." What this proposition does is identify that sentence's true status — not an operational detail but a load-bearing wall — and write down exactly what it must guarantee. However large the nominal $L^{\mathrm{dev}}$, what can be extracted is only "one in-flight installment, plus one detection window's living flow": this is precisely the formalization of the book's two phrases in 4.7, "occupied, not owned" and "consumption is a flow." The lone-actor case closes here; **multi-party collusion** is handled by Proposition 6.

---

## Proposition 4 (Local allocative equivalence of post-billing and expected-cost pricing under rational expectations) [Proof sketch]

The objection (the soft spot of the book's 4.3): prices are provisional and refilled after the fact — does such a price system still perform the Hayekian information-aggregation function? Can the market still clear?

The key is to split the system into two layers:

- **Information layer**: labor bidding in the task market is **spot** — wages clear in the present, aggregating dispersed information in real time. This layer never passes through the refill at all.
- **Settlement layer**: product prices trade at the estimate $\hat p_t = \mathbb{E}[c \mid \mathcal{I}_t]$, the difference against realized cost $c$ is refilled at the end of the lifecycle, and the refill is shared in proportion to historical purchases.

**Proposition 4**: Suppose consumers hold rational expectations, are risk-neutral, and the estimate is unbiased ($\mathbb{E}[c \mid \mathcal{I}_t] = \hat p_t$). Then:
(i) The **effective price** a consumer faces is "spot price + expected refill," $\hat p_t + \mathbb{E}[R \mid \mathcal{I}_t] = \mathbb{E}[c \mid \mathcal{I}_t]$ (with $R$ the refill), i.e. the steady-state allocation coincides with a market pricing spot at expected cost;
(ii) The refill on past purchases is a sunk transfer with respect to future marginal purchases and does not distort marginal conditions;
(iii) The welfare loss relative to the full-information benchmark is second order in the prediction error.

**Proof sketch**:
(i) A rational consumer buying one unit expects total outlay = spot payment $\hat p_t$ + the expected refill that unit will trigger, $\mathbb{E}[c-\hat p_t \mid \mathcal{I}_t] = 0$ (unbiasedness), so the effective marginal price is $\mathbb{E}[c\mid\mathcal{I}_t]$, identical to the marginal price under spot expected-cost pricing; marginal conditions coincide; steady-state allocations coincide.
(ii) The refill owed on purchases already made depends only on historical quantities; it is a deterministic consequence of given purchases and does not appear in the first-order condition of any future purchase — a sunk transfer in the income-effect sense.
(iii) Envelope argument: let full-information optimal demand be $x^{\star}(c)$; under post-billing the consumer decides at $x^{\star}(\mathbb{E}[c])$. The welfare difference $\mathbb{E}[V(x^{\star}(c),c) - V(x^{\star}(\mathbb{E}[c]),c)]$ has vanishing first-order term at $c=\mathbb{E}[c]$ by optimality ($\partial V/\partial x = 0$); the remainder is controlled by the second derivative of $V$ in $x$ times the prediction-error variance $\mathrm{Var}(c)$ — second-order small. ∎ (Sketch; a full proof requires regularity assumptions on the smoothness of $V$ and moment conditions on the error.)

**Explicit scope**: The "equivalence" here is **local** — it covers only the consumer's marginal decision. The rest of the Hayek problem — how producers discover real demand, where the information for cost estimates aggregates (both belong to the task market and gatekeeper mechanisms, the spot bidding layer of the former carrying the main function), whether consumers **actually** understand and anticipate the refill, and how refill uncertainty interacts with purchase psychology under liquidity constraints — is outside this proposition; the last two are listed among the testable predictions of the book's Appendix II (the sixth). Risk aversion is handled head-on by **Proposition 7**.

**Commentary**: This reframes the objection itself: the Hayekian function does not require "the final price to be determined on the spot," only that **the price on which marginal decisions rest** reflects information on the spot — and the task market's bidding layer does exactly that. The refill of course affects total payments, but inside this proposition's model it enters at the level of expectation and risk, not spot marginal decisions — it is closer to an insurance and cost-correction mechanism than to the price signal itself.

---

## Proposition 5 (Stability of population clearing: anchor births, not the total) [Proof + Proof sketch]

Birth incentives act on the population structure with a lag of about eighteen years — a textbook incubator for cobweb oscillation. The formalization yields one negative and one positive result.

**Proposition 5a (Counterexample) [Proof]**: If the control loop anchors the **population total** — reward $R_t = R^{\star} + k\,(N^{\star} - N_t)$, with the lag from birth to labor supply $T\approx 18$ years — linearization gives the delay differential equation

$$\dot x(t) = -k\,x(t-T),\qquad x := N - N^{\star}.$$

Its zero solution is asymptotically stable if and only if $kT < \pi/2$.

**Proof**: The characteristic equation is $\lambda = -k e^{-\lambda T}$. At the stability boundary there is a purely imaginary root $\lambda = i\omega$ ($\omega>0$): substituting and separating real and imaginary parts gives $0 = -k\cos(\omega T)$ and $\omega = k\sin(\omega T)$. The former yields $\omega T = \pi/2$ (first positive solution); substituting back gives $\omega = k$, so the boundary is $kT = \pi/2$. For $kT < \pi/2$ all characteristic roots have negative real part; for $kT > \pi/2$ a root with positive real part exists — the classical criterion of Hayes (1950) for this equation. ∎

With $T=18$, stability requires gain $k < \pi/36 \approx 0.087$ per year — the stable region for high-gain total-population feedback is razor thin; real-world regulation crosses it easily, producing a persistent boom–bust limit cycle of baby booms and baby droughts.

**Proposition 5b (Design comparison) [Proof sketch]**: If the loop instead anchors the **birth flow** — the current age structure and the target replacement rate (2.1) project this year's target births $M_t$ (the mechanism of the book's 8.3), and the reward adjusts through market clearing so that $B_t \to M_t$ — then the loop lag is only the birth decision plus gestation ($T'\approx 1$–$2$ years), and under the same criterion the stable gain region widens by roughly an order of magnitude ($k < \pi/2T' \approx 0.8$–$1.6$ per year); with low-gain proportional–integral smoothing, the system is asymptotically stable. ∎ (Sketch; a full proof requires spectral estimates for the age-structure projection operator.)

**Commentary**: Stating the comparison honestly: birth-side anchoring is **not the only possibly stable** feedback target — total anchoring is equally stable inside $kT<\pi/2$, and can be improved with predictive control and age-structure models — but the birth side compresses the feedback lag from eighteen years to one or two, widening the stable gain region by about an order of magnitude: a **markedly more robust** control target. The book's 8.3 anchored, on mechanism intuition, to the birth-side target $M$ projected from the replacement rate — exactly the more robust of the two; the formalization confirms that choice here and adds the quantitative stability condition plus the engineering warning: no high-gain total-population feedback. **Open problem**: the elasticity of births to the reward (which sets the real value of $k$) is the highest-priority empirical parameter of all.

---

## Proposition 6 (Upper bound on collusion exposure: the κ ceiling is an anti-collusion device) [Proof + Inference]

**Scenario**: a collusion ring $K$ of size $m$: members fabricate tasks for each other, pay each other, and mutually inflate fulfillment records, raising each other's $\hat\rho$ and $\hat E$, stretching limits to the maximum, then defaulting collectively (or keeping the records "forever fresh" by circular mutual trading, to evade the $\tau$ window of Proposition 3).

**Proposition 6a (Static hard ceiling) [Proof]**: Write $L_{\max} := \sup_i \int_{\tau_i}^{T_i} [\kappa\bar Y - s\bar C]^+ d\tau$ (exists and is finite, since lifespans, $\kappa$, $s$ are all bounded). Then **no matter how far the fulfillment records are manipulated**, every individual's developmental limit satisfies $L_i^{\mathrm{dev}} \le L_{\max}$, and hence the ring's total exposure satisfies

$$W_K \le m\,L_{\max}.$$

**Proof**: The income side of the limit formula is capped by $\min(\hat\rho\hat E,\ \kappa\bar Y) \le \kappa\bar Y$, where $\kappa$ and $\bar Y$ are population-wide quantities independent of any individual record; the consumption side is floored by $\max(\hat C, s\bar C) \ge s\bar C$. The integrand is therefore dominated pointwise by $\kappa\bar Y - s\bar C$, and the integral by $L_{\max}$. Record-washing can move only $\hat\rho\hat E$ — and once it crosses $\kappa\bar Y$ it no longer enters the formula. Summing per person gives the ring bound. ∎

**Corollary 6.1 (Linear, no amplification)**: $W_K/m \le L_{\max}$ — collusion gains **per person** nothing that a lone actor cannot gain. The worst collusion can achieve is to stretch Proposition 3's dynamic bound $h+\bar r\tau$ out to the static bound $L_{\max}$ (using circular mutual trading to keep $\hat\rho$ from ever collapsing, and mutual "inspection" to pollute the installment gating) — but it cannot manufacture superlinear amplification: there is no lever by which "$m$ colluders pry loose far more than $m$ shares of limit." The conservation law (A1) structurally cuts off the lever's raw material — all mutual payments inside the ring are intra-ring transfers, and $\sum_{i\in K} b_i$ does not rise by one cent.

**Proposition 6b (Wash trading taxes itself) [Inference]**: Add assumption **C3 (Spending enters the consumption estimate)**: $\hat C_i$ is monotonically increasing in the individual's true spending record (the natural implementation of conservative estimation — the system does not credit "I spent a lot but won't in future"). Then each fabricated payment $j \to i$ inside the ring has this limit effect: $i$'s income-side estimate rises but is capped by $\kappa\bar Y$; $j$'s consumption-side estimate rises, **uncapped**, pressing $L_j^{\mathrm{dev}}$ down. Once every ring member's $\hat\rho\hat E$ has touched the $\kappa\bar Y$ ceiling (the inevitable endpoint of sustained mutual washing), further washing has a marginal effect on the ring's total limit $\sum_K L_i^{\mathrm{dev}}$ that is **strictly negative**: zero gain on the income side, net loss on the consumption side. Collusion thus shows a "saturate first, then self-devour" payoff curve.

**Qualification to 6b**: If fabricated spending is dressed up as production procurement, project input, or outsourced services rather than consumption, C3 does not hold automatically — the self-devouring mechanism fails, and the defense falls back to 6a's static ceiling plus detection. So 6b only describes the self-taxing tendency of wash trading under a particular accounting rule; it is **not an independent anti-collusion proof**.

**Commentary**: The book's 4.7 insists that "κ is the same number for every person" and that "the moment they can vary by person, they become a caste system hidden inside an equation." A principle written down for **fairness** turns out, formalized, to be a **security** device: precisely because κ looks at no one's record, no record-washing can move it. One parameter shuts down privilege and collusion at once — not a coincidence but two faces of the same thing: castes and collusion levers are both ways of "detaching some people's book-entry capability from the population baseline." **What remains open**: this proposition proves the worst exposure has a hard ceiling, not that collusion won't occur; compressing $W_K$ from $mL_{\max}$ back toward the $m(h+\bar r\tau)$ scale requires **detection** — cycle detection on the transaction graph, anomalous mutual-payment identification, independence of project inspection, fake-demand screening, random audit — designed and analyzed as a network game. The hard ceiling and detection are two complementary lines: the former is proven; the latter is marked as formalization's next target.

---

## Proposition 7 (Refill risk smoothing under linear sharing rules) [Proof sketch]

**Scenario**: product $p$'s end-of-lifecycle refill total is a random quantity $X_p = c_p - \hat p_p$ (realized cost minus estimated price), variance $\sigma_p^2$. The refill is shared by a linear share rule: individual $i$ bears $\theta_{i,p} X_p$, with $\sum_i \theta_{i,p} = 1$. Individuals are risk-averse (small-risk approximation with coefficient $\gamma$), so bearing share $\theta$ carries risk premium $\approx \tfrac{\gamma}{2}\theta^2\sigma_p^2$.

**Proposition 7**:
(i) **Wide-audience products** (billed by usage — the first road of the book's 10.1): $\theta_{i,p} = q_i/Q_p$ (the individual's purchases as a share of the total). With many buyers ($Q_p$ large, each $q_i/Q_p \to 0$), the individual risk premium is $O((q_i/Q_p)^2)$, decaying with the square of the audience size — negligible on a large bearing surface.
(ii) **Narrow-audience products** (rare-disease drugs — the second road of the book's 10.1/10.3: the total reward amortized across all humanity): $\theta_{i,p} = 1/N$ (society-wide equal shares). The individual risk premium is $\tfrac{\gamma}{2}\sigma_p^2/N^2$ — negligible.
(iii) **Adverse benchmark**: if a narrow-audience product's refill is shared only among its buyers (share $1/n$, $n$ small), each bears an $O(1)$ exposure and the risk premium does not decay with system scale — a first-order welfare loss really exists. This is exactly the road the book's Chapter 10 rejects (its price-side counterpart is the "million-dollar drug").
(iv) **Within the class of linear share rules**, spreading the refill over the largest available bearing surface (wide audience → all users; narrow audience → all society) minimizes the largest individual share $\max_i \theta_{i,p}$, and hence minimizes the worst individual risk premium.

**Proof sketch**: (i)(ii)(iii) follow directly by substitution into the quadratic risk premium. (iv) Under the constraints $\sum\theta = 1$, $\theta \ge 0$, the minimum of $\max_i \theta_i$ is attained at equal shares (elementary). ∎ (Sketch.)

**Explicit scope**: (iv) is a property within the linear-rule class, with "worst individual risk premium" as the objective — **not** optimality under all social objectives: fairness (the tension between the intuition "non-users shouldn't bear it" and society-wide sharing), incentives and moral hazard, heterogeneous risk aversion, income differences, and cross-product risk correlation are all outside the objective. One honest corner: for wide-audience products, if a few large buyers hold a huge share of the volume, their $q_i/Q_p$ shares stay substantial — usage-based sharing strikes a balance between the responsibility principle of "use it, bear it" and risk smoothing; it is not pure variance minimization. Nonlinear rules and mechanism design under fuller objectives are marked open.

**Commentary**: Proposition 4 proved local allocative equivalence under risk neutrality and left risk aversion to this proposition. The quantitative answer now available: within the linear class, Chapter 10's two-dimensional reward rule — "wide audience → by usage, narrow audience → amortized across humanity" — is exactly what demotes the refill from "price risk" to "per-capita noise," with individual risk premia decaying as the **square** of the bearing surface: the first-order welfare effect of risk aversion is suppressed by this arrangement. Whether consumers **actually** anticipate the refill remains a behavioral empirical question (the book's Appendix II).

---

## Proposition 8 (Equilibrium existence in a stationary toy economy, and compatibility with dynamic efficiency) [Proof sketch]

Existence and uniqueness of general equilibrium — an overlapping-generations economy with lifetime return-to-zero and no interest — is this theory's genuinely hard bone, whose full treatment deserves a stand-alone formal paper. This proposition carves off the easiest slice first: the **deterministic, stationary, zero-population-growth** toy case.

**Toy model**: a continuous overlapping-generations economy. Population stationary (growth rate $n=0$), individual lifespan $[0,A]$, uniform density across age cohorts. Finitely many goods and tasks; individuals choose lifetime consumption and labor-supply paths; preferences continuous, convex, monotone; technology convex. The budget constraint is **lifetime return-to-zero**:

$$\int_0^A [y_i(a) - c_i(a)]\,da = 0,$$

with within-life balances allowed negative (the birthright overdraft), and by A4 no interest on carry-over — the intertemporal relative price faced by each individual is 1 (implicit rate $r=0$). In the deterministic steady state there is no prediction error, post-billing coincides with spot cost pricing (the degenerate case of Proposition 4(i)), and price equals cost.

**Proposition 8a (Existence)**: The above economy admits a stationary competitive equilibrium: there exist a task wage vector and a product price vector such that every individual optimizes under lifetime return-to-zero, all task and product markets clear, and the conservation invariant of Proposition 1 holds automatically.

**Proof sketch**: The lifetime return-to-zero constraint makes each individual's budget set a standard Arrow–Debreu budget set (at intertemporal prices with $r=0$); convexity and continuity of preferences and technology give upper hemicontinuity and convex-valuedness of demand and supply correspondences; summing the individual lifetime budget identities yields Walras's law (whose accounting shadow is Proposition 1); Kakutani's fixed-point theorem on the price simplex gives existence. ∎ (Sketch; in essence, embedding the benyuan steady state into a zero-interest OLG framework and invoking the standard existence argument. One technical detail stated honestly: the continuous lifecycle makes the intertemporal commodity space infinite-dimensional, and applying the finite-dimensional price simplex directly is not rigorous — discretize the lifecycle into finitely many age segments and the existence argument goes through completely in finite dimensions; the continuous-age limit requires equilibrium existence conditions for infinite-dimensional economies, listed in the full paper's technical checklist.)

**Proposition 8b (Compatibility with dynamic efficiency)**: Samuelson's (1958) pure consumption-loan overlapping-generations model gives the classical result: the dynamically efficient interest rate equals the population growth rate (the "biological rate," $r=n$). With stationary population, $n=0$, the efficient rate in that model is exactly zero — coinciding with A4. **The claim of this proposition is defensive**: within this toy model, an interest-free internal accounting money does not violate dynamic efficiency — the rebuttal "no interest, no efficiency" fails, at least here. ∎ (Sketch; citing the classical result.)

**Explicit boundary of 8b**: $r=n$ is the conclusion of the pure consumption-loan model. In models with capital accumulation, technical progress, and depreciation, the golden-rule condition is no longer simply $r=n$ (it typically involves the technology growth rate and the marginal product of capital, conditions of the $r=n+g$ type); with technical growth $g>0$, zero interest and the golden rule no longer coincide. Benyuan's efficiency properties in that class of models — including the interaction of the no-interest design with capital-accumulation incentives — belong to the full paper; no claim is made here.

**Commentary**: What 8b buys is not "mainstream economics' endorsement" but a **shield**: the efficiency critic cannot, inside the standard toy model, veto this design with "no interest means no efficiency." **Explicitly not covered** (the checklist for upgrading to a full paper): uniqueness of equilibrium; equilibrium under uncertainty (the refill becomes genuinely random and the mechanisms of Propositions 4/7 enter the equilibrium definition); non-stationary population and transition dynamics; the case where the limit constraint $L^{\mathrm{dev}}$ binds endogenously in equilibrium; dynamic efficiency with capital and technical progress.

---

## Closing the ledger: what this outline proved, and what it did not

**Proven (unconditionally, or from axioms alone)**: conservation is a constructive property — under ledger closure it cannot be violated, only bypassed, and every threat reduces to ledger integrity (Proposition 1); historical gaps carry no compound interest, are dead entries, and the book-entry intergenerational burden equals only the current flow (Corollary 2.1); collusion exposure is hard-capped by the population-uniform κ ceiling, linear in headcount, with no superlinear lever (Proposition 6a).

**Proven under explicitly stated conditions**: sustainability collapses to a testable flow criterion — long-run $\varphi+\psi\le\pi$ (Proposition 2, under actuarial and conservative-estimation assumptions; the project-failure flow $\psi$ is a separate item, see below); under a hard staged-release regime, strategic extraction has the hard bound $h+\bar r\tau$, with three adjustable policy screws, the bound conditional on strict enforcement of B1′ (Proposition 3); total-population anchoring of birth regulation oscillates almost inevitably at realistic gains (Proposition 5a, the Hayes criterion).

**Given as proof sketches**: under rational expectations and risk neutrality, post-billing is locally allocatively equivalent to expected-cost pricing, with the information layer decoupled from the settlement layer (Proposition 4); birth-side anchoring widens the stable gain region by roughly an order of magnitude — the markedly more robust control target (Proposition 5b); within the linear-rule class, Chapter 10's reward rule drives individual refill risk down with the square of the bearing surface (Proposition 7); equilibrium exists in the stationary deterministic toy economy, and zero interest is compatible with dynamic efficiency in the Samuelson-style model (Propositions 8a/8b).

**Marked as inference only**: wash trading, under the accounting rule that spending enters the consumption estimate, saturates first and then devours itself (Proposition 6b) — if fabricated spending is dressed as production procurement, the mechanism fails and the defense falls back to the hard ceiling plus detection.

**Not proven, in order of importance**: full general equilibrium — uncertainty, endogenously binding overdraft constraints, non-stationary population and transition dynamics, efficiency with capital and technical progress (Proposition 8 is only the first installment; the full sum deserves a stand-alone formal paper); the **detection** side of collusion — cycle detection on the transaction graph and the network game analysis of cross-verification (Proposition 6 gave the exposure ceiling, not the practical compression); a structural upper bound on the project-failure absorption flow $\psi$ — the formalization of gatekeeper accounting quality and project-level installment discipline (Proposition 2 only counts it into the criterion, without bounding it); refill mechanism design under nonlinear rules and fuller social objectives (Proposition 7 is confined to the linear class); and all the empirical parameters ($q$, birth elasticity, the engineering of $\tau$, the realistic value of $h$, consumers' actual expectations about the refill) — this last bill can never be paid on paper, only by a pilot.

An unfinished building does not mean the foundation is fake. What this document reinforces is the foundation and the load-bearing walls of the lower floors; the floors above are marked here, waiting to be built.

---

## References

- Hayes, N. D. (1950). Roots of the transcendental equation associated with a certain difference-differential equation. *Journal of the London Mathematical Society*, 25(3), 226–232. (The delay-equation stability criterion cited in Proposition 5a.)
- Samuelson, P. A. (1958). An exact consumption-loan model of interest with or without the social contrivance of money. *Journal of Political Economy*, 66(6), 467–482. (The "biological rate" and the original overlapping-generations model cited in Proposition 8b.)

---

*This document circulates freely alongside* Benyuan: Rewriting the Foundation of the Economy *(English edition), under the same attribution rules as the book. The Chinese original of this outline, and of the book, are published in the companion repository. Errata and rebuttals: please file them at the release repository — this document, like the book, was written to be tested, not to be believed.*
