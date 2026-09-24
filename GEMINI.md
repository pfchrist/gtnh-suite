# Antigravity Ground-Truth & Zero-Hallucination Policy

## 1. Strict Ground-Truth Verification
- **Never guess, extrapolate, or invent game mechanics, recipes, or flavor text.**
- Every statement regarding recipes, material statistics, multipliers, machine maintenance, or tool behaviors MUST be directly verified against ground-truth source code or the local ground-truth database (`gt_tools_ground_truth_db.json`).
- If an exact code recipe or interaction does not exist or has not been verified from source code, state explicitly: `"I do not have verified source code for this interaction; let's check the source or another reliable database."`

## 2. No Flavor Text as Fact
- Do not write gameplay tips based on real-world analogies, assumptions, or poetic descriptions (e.g. "cleans splinters", "prevents conveyor jams", "spares living trees") unless that exact mechanic exists as a code routine.
- Every bullet point in user-facing tools or codices must correspond 1:1 to an actual in-game method, event, recipe, or numerical multiplier.

## 3. Maintenance Rule Definition
- Multiblock Maintenance issues are strictly the 5 documented issues in GT5U:
  1. Loose Pipes -> Wrench
  2. Loose Screws -> Screwdriver
  3. Burned Circuit -> Soldering Iron (+ Soldering Alloy Wire)
  4. Mechanical Jam -> Crowbar
  5. Dented Plating -> Hard Hammer
- The Hand Saw, Butchery Knife, Wire Cutter, Plunger, etc. are NOT multiblock maintenance tools.

## 4. Recipe Crafting Grid Fidelity
- All crafting recipes presented to the user must reflect the actual shaped/shapeless crafting matrix defined in GT5U / mod code (`ProcessingToolOther.java`, `ProcessingToolHead.java`, `MetaGeneratedTool01.java`, etc.).
- Never offer materials for tool parts that do not have the required `OrePrefix` (e.g., Stone and Flint have no plates, so tools requiring plates cannot be crafted from Stone or Flint).
