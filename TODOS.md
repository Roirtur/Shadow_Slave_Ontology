# Shadow Slave Rank System – Protégé OWL Checklist (Manchester Syntax)

## Step 0: Object Properties
We first need to define these object properties in Protégé before applying restrictions.

### Core Properties
- [x] `hasRank` (domain: Entity ⊔ Object ⊔ Human, range: Rank)
  - [x] `followAscension`
  - [x] `followCorruption`
- [x] `hasClass` (domain: Entity ⊔ Human, range: Class)
- [x] `hasAspect` (domain: Human, range: Aspect)
- [x] `hasCore` (domain: Entity, range: SoulCoresType)
- [x] `hasEnchantment` (domain: Human ⊔ Creature ⊔ Object, range: Enchantment)
- [x] `owns` (domain: Human, range: Object ⊔ Echo)
- [x] `hasOwner` (domain: Echo, range: Human)

### New Properties to Add
- [ ] `hasFlaw` (domain: Human, range: Flaw)
- [ ] `hasConqueredNightmare` (domain: Human, range: Nightmare) - already exists, verify range
- [ ] `beatsRank` (domain: Object, range: Rank) - for weapon superiority rules

---

## Step 1: Human Basic Rules
- [x] `Human SubClassOf: Entity and AscensionPath and hasRank some AscensionRank and hasClass some Class and hasAspect some Aspect and hasEnchantment min 1 Enchantment`
- [x] `Human SubClassOf: owns some Object`
- [x] `Human SubClassOf: owns some Echo`
- [ ] `Human SubClassOf: hasFlaw some Flaw` *(NEW)*
- [ ] Divide human first subclass of into multiple for readability

---

## Step 2: Cardinality Rules (Enchantments & Cores)

### 2.1 Human Ascension Ranks by Enchantment Count
- [ ] `Sleeper SubClassOf: Human and hasEnchantment exactly 1 Enchantment`
- [ ] `Awakened(Hum) SubClassOf: Human and hasEnchantment exactly 2 Enchantment`
- [ ] `Master SubClassOf: Human and hasEnchantment exactly 3 Enchantment`
- [ ] `Ascended SubClassOf: Human and hasEnchantment exactly 3 Enchantment`
- [ ] `Saint SubClassOf: Human and hasEnchantment exactly 4 Enchantment`
- [ ] `Transcendent SubClassOf: Human and hasEnchantment exactly 4 Enchantment`
- [ ] `Sovereign SubClassOf: Human and hasEnchantment exactly 5 Enchantment`
- [ ] `Supreme SubClassOf: Human and hasEnchantment exactly 5 Enchantment`
- [ ] `Sacred SubClassOf: Human and hasEnchantment exactly 6 Enchantment`
- [ ] `Spirit SubClassOf: Human and hasEnchantment exactly 6 Enchantment`
- [ ] `Divine SubClassOf: Human and hasEnchantment exactly 7 Enchantment`

### 2.2 Creature Corruption Ranks by Enchantment Count
- [ ] `Dormant(Cor) SubClassOf: Creature and hasEnchantment exactly 1 Enchantment`
- [ ] `Awakened(Cor) SubClassOf: Creature and hasEnchantment exactly 2 Enchantment`
- [ ] `Fallen SubClassOf: Creature and hasEnchantment exactly 3 Enchantment`
- [ ] `Corrupted SubClassOf: Creature and hasEnchantment exactly 4 Enchantment`
- [ ] `Great SubClassOf: Creature and hasEnchantment exactly 5 Enchantment`
- [ ] `Cursed SubClassOf: Creature and hasEnchantment exactly 6 Enchantment`
- [ ] `Unholy SubClassOf: Creature and hasEnchantment exactly 7 Enchantment`

### 2.3 Entity Classes by Core Count
- [ ] `Beast SubClassOf: Class and hasCore exactly 1 SoulCoreType`
- [ ] `Monster SubClassOf: Class and hasCore exactly 2 SoulCoreType`
- [ ] `Demon SubClassOf: Class and hasCore exactly 3 SoulCoreType`
- [ ] `Devil SubClassOf: Class and hasCore exactly 4 SoulCoreType`
- [ ] `Tyrant SubClassOf: Class and hasCore exactly 5 SoulCoreType`
- [ ] `Terror SubClassOf: Class and hasCore exactly 6 SoulCoreType`
- [ ] `Titan SubClassOf: Class and hasCore exactly 7 SoulCoreType`

### 2.4 Ascension Ranks by Enchantment Count (Generic)
- [ ] `Dormant(Asc) SubClassOf: Rank and hasEnchantment exactly 1 Enchantment`
- [ ] `Awakened(Asc) SubClassOf: Rank and hasEnchantment exactly 2 Enchantment`
- [ ] `Ascended SubClassOf: Rank and hasEnchantment exactly 3 Enchantment`
- [ ] `Master SubClassOf: Rank and hasEnchantment exactly 3 Enchantment`
- [ ] `Saint SubClassOf: Rank and hasEnchantment exactly 4 Enchantment`
- [ ] `Transcendent SubClassOf: Rank and hasEnchantment exactly 4 Enchantment`
- [ ] `Sovereign SubClassOf: Rank and hasEnchantment exactly 5 Enchantment`
- [ ] `Supreme SubClassOf: Rank and hasEnchantment exactly 5 Enchantment`
- [ ] `Sacred SubClassOf: Rank and hasEnchantment exactly 6 Enchantment`
- [ ] `Spirit SubClassOf: Rank and hasEnchantment exactly 6 Enchantment`
- [ ] `Divine SubClassOf: Rank and hasEnchantment exactly 7 Enchantment`
- [ ] `Sleeper SubClassOf: Rank and hasEnchantment exactly 1 Enchantment`

---

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

---

## Step 5: Entity Rules
- [x] `Entity SubClassOf: Alterable and hasCore some SoulCoreType`

---

## Step 6: Creature Rules (Corruption Path)
- [x] `Creature SubClassOf: Entity and CorruptionPath and hasRank some CorruptionRank and hasClass some Class`

---

## Step 7: Echo Rules (Ascension Path)
- [x] `Echo SubClassOf: Entity and AscensionPath and hasRank some AscensionRank and hasClass some Class and hasOwner some Human`

---

## Step 8: Object Rules
- [x] `Object SubClassOf: Alterable and hasRank some AscensionRank and hasEnchantment some Enchantment`
- [x] `Armor SubClassOf: Object`
- [x] `Weapon SubClassOf: Object`
- [x] `Utility SubClassOf: Object`
- [x] `Armor DisjointWith: Weapon, Utility`
- [x] `Weapon DisjointWith: Utility`

---

## Step 9: Aspect, Enchantment & Flaw Rules
- [x] `Aspect SubClassOf: Alterable and hasRank some AscensionRank`
- [x] `Enchantment SubClassOf: Alterable`
- [ ] `Flaw SubClassOf: Alterable` *(NEW)*
- [ ] Define common Flaw individuals (e.g., `BlindSight`, `Corruption`, `MortalForm`)

---

## Step 10: Rank Rules
- [x] `Rank SubClassOf: Immutable`

---

## Step 11: Disjointness Rules
- [x] `Alterable DisjointWith: Immutable`
- [x] `Ascension DisjointWith: Corruption, Mundane`
- [x] `Aspect DisjointWith: Enchantment, Entity, Object`
- [x] `Beast DisjointWith: Demon, Devil, Monster, Terror, Titan, Tyrant`
- [x] `Class DisjointWith: Rank, SoulCoresType`
- [x] `Corrupted DisjointWith: Cursed, Fallen, Great, Unholy, Awakened(Cor), Dormant(Cor)`
- [x] `Creature DisjointWith: Human`
- [x] `Fire DisjointWith: Neutral, Shadow`
- [x] `Armor DisjointWith: Weapon, Utility`
