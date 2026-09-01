# WTIV Set Capacity Calculator

A browser-based screening tool for offshore wind turbine installation vessels (WTIVs). No installation required — open the link and start using it.

---

## What this tool does

The calculator helps you quickly screen how many turbine sets a given WTIV can carry for a specific turbine size, and whether the vessel can actually install them at a given site. It covers:

- **Deck capacity** — how many complete sets (tower + nacelle + 3 blades) fit on deck based on geometry, deck area, and payload
- **Installation gates** — water depth vs leg length, hook height vs hub height, crane capacity vs component weight
- **Deck arrangement** — a plan view drawing showing where towers, nacelles, and the blade rack sit on deck
- **Fleet screening** — compare all vessels in the database against one turbine size in a single table

---

## How to use it

### Calculator tab
1. Select a **vessel** from the dropdown on the left
2. Select a **turbine size** from the dropdown at the top right
3. Adjust the **site parameters** (water depth, tide, air gap, leg penetration) in the Operation panel if needed
4. The result appears immediately — set count, which gate is binding, and a deck plan drawing

The left panel shows all vessel parameters. You can edit any value directly in the input fields. Click **Save Data** in the header to persist your changes across sessions.

### Fleet screening tab
Select a turbine size and the table shows every vessel in the database — set count, binding constraint, and whether each installation gate passes or fails. Useful for quickly identifying which vessels are capable for a given project.

### Vessel & turbine data tab
Shows the full database with confirmed vs estimated flags for each data field. Green = confirmed from operator or designer publications. Orange = estimated. Use this to understand data confidence before relying on a result.

### Method & assumptions tab
Explains the calculation logic, gate definitions, and the deck arrangement rules in detail.

---

## Editing and saving data

All input fields are editable. To update a vessel spec or turbine parameter:

1. Select the vessel or turbine from the dropdown
2. Change the value in the relevant input field
3. Click **Save Data** — the button is in the header, top right area

Your changes are saved to the browser's local storage and will be there the next time you open the tool **in the same browser**. If you clear your browser data or switch to a different browser or device, the changes will be gone.

To back up your edits: click **Export data** — this downloads a JSON file with the full dataset. To restore it on another machine: click **Import data** and select the file.

To undo all your changes and go back to the original data: click **Reset defaults**.

---

## Understanding the results

**Set count** — the number of complete turbine sets the vessel can carry. One set = one tower (all sections) + one nacelle (hub included) + three blades in the rack.

**Binding constraint** — the single factor that limits the set count. Usually one of:
- *Deck arrangement* — the geometric solver ran out of deck space before payload
- *Payload* — total component weight reached the vessel's variable deck load limit
- *Hook reach* — the crane cannot reach the hub height with adequate clearance
- *Water depth* — the legs are too short for the site
- *Crane capacity* — the crane cannot lift the heaviest component at the required radius

**Deck plan drawing** — a top-down view of the cargo deck. Towers are grouped on the port side close to the crane leg. Nacelles sit on the starboard side under the boom. The blade rack occupies the aft end. Containers are distributed in the remaining space.

**Estimated vs confirmed data** — fields flagged orange are estimates based on vessel class, similar vessels, or scaling. Do not use these for contract or project planning without verification.

---

## Vessel database

The tool currently includes 51 vessels:

- Cadeler fleet (Wind Peak, Wind Pace, Wind Ace/Ally/Apex, Wind Maker/Mover, Wind Orca/Osprey, Wind Scylla, Wind Keeper, Wind Zaratan, T-class)
- Van Oord (Boreas, Aeolus, Sea Installer, Sea Challenger, Innovation, MPI Adventure/Resolution)
- Jan De Nul (Voltaire, Vole au Vent)
- Fred Olsen Windcarrier (Blue Tern, Bold Tern, Brave Tern, Blue Wind, FOWIC 4th)
- Seaway 7 (Seaway Ventus)
- Dominion Energy (Charybdis)
- Norse Offshore (Norse Energi, Norse Wind)
- ZITON (Wind Discovery, Wind Energy, Wind Enterprise, Wind Lift 1)
- Various smaller and regional vessels

Vessel data is sourced from operator and designer publications where available. Where no public data exists, values are estimated and flagged accordingly.

---

## Turbine sizes

Nine size bands are included: 5, 6, 8, 10, 11, 14, 15, 18, and 20 MW. Component weights and footprints scale from a confirmed 10 MW anchor. Hub heights are based on published turbine specifications for each size band.

---

## Limitations

- The deck arrangement is a geometric model, not a certified stowage plan. It does not account for all seafastening constraints, load distribution requirements, or project-specific deck layouts.
- Crane capacity is modelled as a two-point curve (rated capacity at two radii). Real crane curves are more complex.
- Many vessels have estimated hull dimensions — these affect the deck drawing but not the set count directly.
- The tool is a screening aid. Results should be verified against vessel operator documentation before use in project planning.

---

## Questions or corrections

If you find a data error or want to suggest a vessel to add, use the Export data function to share your updated dataset.
