### New Properties to Add=
- [ ] `hasConqueredNightmare` (domain: Human, range: Nightmare) - already exists, verify range
- [ ] `beatsRank` (domain: Object, range: Rank) - for weapon superiority rules

## Step 3: Nightmare Conquest & Rank Progression Rules *(NEW)*

### 3.1 Rank Deduction by Nightmares Conquered
- [ ] `Human and hasConqueredNightmare exactly 1 Nightmare SubClassOf: Awakened(Hum)`
- [ ] `Human and hasConqueredNightmare exactly 2 Nightmare SubClassOf: Ascended`
- [ ] `Human and hasConqueredNightmare exactly 3 Nightmare SubClassOf: Transcendent`
- [ ] `Human and hasConqueredNightmare exactly 4 Nightmare SubClassOf: Saint`
- [ ] `Human and hasConqueredNightmare min 5 Nightmare SubClassOf: Supreme or Sovereign or Divine`

### 3.2 Nightmare Classification (Optional Enhancement)
- [ ] Create `FirstNightmare`, `SecondNightmare`, `ThirdNightmare` subclasses
- [ ] Add progression tracking with data properties
- [ ] Maybe add "has exactly 2 enchantment if hasBeaten 2 nightmares" or some sort
---

## Step 4: Object Superiority Rules *(NEW)*

### 4.1 Weapon Rank Beating System
- [ ] `Object and hasRank some Awakened(Asc) SubClassOf: beatsRank some Dormant(Asc)`
- [ ] `Object and hasRank some Ascended SubClassOf: beatsRank some (Dormant(Asc) or Awakened(Asc))`
- [ ] `Object and hasRank some Saint SubClassOf: beatsRank some (Dormant(Asc) or Awakened(Asc) or Ascended)`
- [ ] `Object and hasRank some Sovereign SubClassOf: beatsRank some (Dormant(Asc) or Awakened(Asc) or Ascended or Saint)`
- [ ] `Object and hasRank some Divine SubClassOf: beatsRank some (Dormant(Asc) or Awakened(Asc) or Ascended or Saint or Sovereign)`

### 4.2 Alternative: Rank Hierarchy Property Chain
- [ ] Create `isStrongerThan` transitive property
- [ ] Define rank hierarchy: `Dormant < Awakened < Ascended < Saint < Sovereign < Divine`

- [ ] Aussi add l'opposé