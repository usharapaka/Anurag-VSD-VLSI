# Day 1 – Verilog RTL Design Through Simulation

## 🎯 Experiment Objective

The objective of this experiment is to understand the fundamentals of Register Transfer Level (RTL) design using Verilog HDL. The experiment focuses on learning how to compile and simulate Verilog designs using Icarus Verilog (iverilog) and verify the output through waveform analysis using GTKWave. A 2:1 Multiplexer is implemented to understand the complete simulation flow.

---

# 📚 Contents

- Digital Design Verification
- Simulation Workflow with Icarus Verilog
- Practical Exercise – Simulating a 2:1 Multiplexer
- Multiplexer Design Explanation
- Conclusion

---

# 1️⃣ Digital Design Verification

## Simulator

A simulator is a software tool that executes Verilog designs in a virtual environment. It helps designers verify circuit functionality before hardware implementation.

## Design

A design is the Verilog module that describes the logic and behavior of a digital circuit.

## Testbench

A testbench is a verification module that applies different input combinations to the design and checks whether the output is correct.

---

# 2️⃣ Simulation Workflow with Icarus Verilog

Icarus Verilog (iverilog) is an open-source Verilog compiler and simulator. It compiles the design and testbench, executes the simulation, and generates a Value Change Dump (.vcd) file which can be viewed using GTKWave.

## Simulation Flow

```
Design File
      │
      ▼
Testbench
      │
      ▼
Icarus Verilog (iverilog)
      │
      ▼
Generate .vcd File
      │
      ▼
GTKWave
```

---

# 3️⃣ Practical Exercise – Simulating a 2:1 Multiplexer

## Step 1 – Install Required Tools

```bash
sudo apt install iverilog
sudo apt install gtkwave
```

Install the Verilog compiler and waveform viewer.

---

## Step 2 – Compile the Design

```bash
iverilog good_mux.v tb_good_mux.v
```

This command compiles the design file and the testbench.

---

## Step 3 – Execute the Simulation

```bash
./a.out
```

Running this command executes the simulation and generates the waveform (.vcd) file.

---

## Step 4 – Open the Waveform

```bash
gtkwave tb_good_mux.vcd
```

The generated waveform is opened using GTKWave for verification.

---
## GTKWave Output

<img width="1913" height="1193" alt="Screenshot 2026-08-06 203754" src="https://github.com/user-attachments/assets/3bc7bf8b-a318-479c-8340-4fa626f98754" />


# 4️⃣ Multiplexer Design Explanation

## Verilog Design

```verilog
module good_mux (
    input i0,
    input i1,
    input sel,
    output reg y
);

always @(*)
begin
    if (sel)
        y <= i1;
    else
        y <= i0;
end

endmodule
```

## Working Principle

### Inputs

- **i0** – First input
- **i1** – Second input
- **sel** – Selection signal

### Output

- **y** – Multiplexer output

### Operation

- When **sel = 0**, the output follows **i0**.
- When **sel = 1**, the output follows **i1**.

---
# Verilog Code Screenshot

<img width="1913" height="1195" alt="Screenshot 2026-08-06 214101" src="https://github.com/user-attachments/assets/e1de5ced-1ded-4dc0-b03e-c067a1f5e98a" />




# 📸 Results

- Successfully compiled the Verilog design using Icarus Verilog.
- Executed the simulation without errors.
- Generated the waveform (.vcd) file.
- Verified the waveform using GTKWave.
- 
---

# ✅ Conclusion

In this experiment, I learned the basic RTL design flow using Verilog HDL. I understood the purpose of a design module, testbench, simulator, waveform analysis, and RTL synthesis. The 2:1 Multiplexer was successfully compiled, simulated, and synthesized using open-source EDA tools, providing a strong foundation for further VLSI design experiments.
