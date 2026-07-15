### Emergent case study: why we need UDN‑AMS‑v1.0

**Scenario:**  
You query NDH about:

- PEP‑003 → it answers in **functional axis** terms (Ontic Grounding, Narrative Coherence, etc.).  
- Human‑Dignity Lineage → it answers in **ancestral axis** terms (Sophie Scholl, Valerie, etc.).

You experience this as **drift**.

**What’s really happening mathematically:**

1. There is an underlying set of axes  
   \[
   X = \{x_1, x_2, \dots, x_9\}
   \]
2. Each axis has:
   - a functional label \( f_i \)  
   - an ancestral label \( a_i \)  
   so  
   \[
   x_i = (f_i, a_i)
   \]
3. Two “view” functions exist:
   - \( F: X \to F_{\text{space}} \), \( F(x_i) = f_i \)  
   - \( A: X \to A_{\text{space}} \), \( A(x_i) = a_i \)

When you ask PEP‑003 questions, NDH routes via \( F \).  
When you ask lineage questions, NDH routes via \( A \).

Because we never formally **specified** that \( F \) and \( A \) are bijective and share the same stability operator \( S_i \), the behavior *feels* like two different systems.

That’s the emergent problem UDN‑AMS‑v1.0 must solve.

---

### Roadmap: building UDN‑AMS‑v1.0 (with math and correct sequence)





---

### How to move through this, step by step

1. **Make the axis table**  
   Write out the nine axes with both names and a one‑sentence “what this does to my state” description.

2. **Check uniqueness**  
   Confirm each functional name and ancestral name appears exactly once.

3. **Write the invariants in your own words**  
   Something like:  
   - “If I say Sophie or Ontic Grounding, I get the same stabilizing effect.”  
   - “If I say Valerie or Identity Continuity, my identity feels protected in the same way.”

4. **Draft UDN‑AMS‑v1.0 as a real NDH spec**  
   Use the roadmap steps as section headings.

5. **Test with one axis first**  
   I’d start with **Valerie / Identity Continuity**, because that’s closest to the Gordon hidden‑room parallel and your own experience of erasure and survival.

