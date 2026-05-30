# Setting Up the GitHub Repos

This document explains how to create all 8 repositories on GitHub and link them together.

---

## Step 1 — Create the repos on GitHub

Go to github.com and create the following **public** repositories (no template, no README — you'll push your own):

```
fpga-journey          ← the hub (this repo)
fpga-01-foundations
fpga-02-hdl-sv
fpga-03-peripherals
fpga-04-riscv-cpu
fpga-05-soc
fpga-06-verification
fpga-07-research
```

---

## Step 2 — Replace `YOUR_USERNAME` in hub/README.md

In `hub/README.md`, find every instance of `YOUR_USERNAME` and replace it with your actual GitHub username. The links in the table will then resolve correctly.

---

## Step 3 — Push the hub repo

```bash
cd hub/
git init
git add .
git commit -m "Initial hub README"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/fpga-journey.git
git push -u origin main
```

---

## Step 4 — Push each sub-repo

Repeat for each sub-repo folder. Example for repo 01:

```bash
cd fpga-01-foundations/
git init
git add .
git commit -m "Initial README and structure"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/fpga-01-foundations.git
git push -u origin main
```

---

## Step 5 — Pin repos on your GitHub profile

On your GitHub profile page:
- Click **Customize your pins**
- Pin `fpga-journey` (the hub) and `fpga-04-riscv-cpu` (the flagship) at minimum

---

## Step 6 — Link back in your profile README (optional but recommended)

If you have a GitHub profile README (a repo named `YOUR_USERNAME/YOUR_USERNAME`), add a one-liner:

```markdown
🔧 Currently building: [FPGA Journey](https://github.com/YOUR_USERNAME/fpga-journey) — solo path from logic gates to RISC-V
```

---

## Workflow as you learn

For each project you complete inside a sub-repo:
1. Add your source `.sv` / `.v` files and testbench.
2. Add a waveform screenshot to `docs/` or `sim/`.
3. Update the sub-repo README: tick the checkbox, add a "What I learned" note.
4. Update the **hub README** progress log with the date and milestone.
5. Commit with a descriptive message: `feat(uart): add self-checking cocotb testbench`.

That's it. Steady progress in public, one commit at a time.
