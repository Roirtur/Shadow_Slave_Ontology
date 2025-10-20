# Shadow Slave Rank System – Protégé OWL Checklist (Manchester Syntax)

## Step 0: Add Object Properties
We first need to define these object properties in Protégé before applying restrictions.

- [x] `hasRank` (domain: Entity ⊔ Object ⊔ Human, range: Rank)
  - [x] `followAscension`
  - [x] `followCorruption`
- [x] `hasClass` (domain: Entity ⊔ Human, range: Class)
- [x] `hasAspect` (domain: Human, range: Aspect)
- [x] `hasCore` (domain: Entity, range: SoulCoresType)
- [x] `hasEnchantment` (domain: Human ⊔ Creature ⊔ Object, range: Enchantment)
- [x] `owns` (domain: Human, range: Object ⊔ Echo)
- [x] `hasOwner` (domain: Echo, range: Human)

---

## Step 1: Human Rules
- [x] `Human SubClassOf: Entity and AscensionPath and hasRank some AscensionRank and hasClass some Class and hasAspect some Aspect and hasEnchantment min 1 Enchantment`
- [x] `Human SubClassOf: owns some Object`
- [x] `Human SubClassOf: owns some Echo`

### Ascension Rank Enchantments
- [ ] `Awakened(Hum) SubClassOf: Human and hasEnchantment exactly 2 Enchantment`
- [ ] `Sleeper SubClassOf: Human and hasEnchantment exactly 1 Enchantment`
- [ ] `Master SubClassOf: Human and hasEnchantment exactly 3 Enchantment`
- [ ] `Ascended SubClassOf: Human and hasEnchantment exactly 3 Enchantment`
- [ ] `Divine SubClassOf: Human and hasEnchantment exactly 7 Enchantment`
- [ ] `Saint SubClassOf: Human and hasEnchantment exactly 4 Enchantment`
- [ ] `Sacred SubClassOf: Human and hasEnchantment exactly 6 Enchantment`
- [ ] `Sovereign SubClassOf: Human and hasEnchantment exactly 5 Enchantment`
- [ ] `Spirit SubClassOf: Human and hasEnchantment exactly 6 Enchantment`
- [ ] `Supreme SubClassOf: Human and hasEnchantment exactly 5 Enchantment`
- [ ] `Transcendent SubClassOf: Human and hasEnchantment exactly 4 Enchantment`

---

## Step 2: Entity Rules
- [x] `Entity SubClassOf: Alterable and hasCore some SoulCoreType`

### Entity Classes by Number of Cores
- [ ] `Beast SubClassOf: Class and hasCore exactly 1 SoulCoreType`
- [ ] `Monster SubClassOf: Class and hasCore exactly 2 SoulCoreType`
- [ ] `Demon SubClassOf: Class and hasCore exactly 3 SoulCoreType`
- [ ] `Devil SubClassOf: Class and hasCore exactly 4 SoulCoreType`
- [ ] `Tyrant SubClassOf: Class and hasCore exactly 5 SoulCoreType`
- [ ] `Terror SubClassOf: Class and hasCore exactly 6 SoulCoreType`
- [ ] `Titan SubClassOf: Class and hasCore exactly 7 SoulCoreType`

---

## Step 3: Creature Rules (Corruption Path)
- [x] `Creature SubClassOf: Entity and CorruptionPath and hasRank some CorruptionRank and hasClass some Class`

### Corruption Rank Enchantments
- [ ] `Corrupted SubClassOf: Creature and hasEnchantment exactly 4 Enchantment`
- [ ] `Cursed SubClassOf: Creature and hasEnchantment exactly 6 Enchantment`
- [ ] `Fallen SubClassOf: Creature and hasEnchantment exactly 3 Enchantment`
- [ ] `Great SubClassOf: Creature and hasEnchantment exactly 5 Enchantment`
- [ ] `Unholy SubClassOf: Creature and hasEnchantment exactly 7 Enchantment`
- [ ] `Awakened(Cor) SubClassOf: Creature and hasEnchantment exactly 2 Enchantment`
- [ ] `Dormant(Cor) SubClassOf: Creature and hasEnchantment exactly 1 Enchantment`

---

## Step 4: Echo Rules (Ascension Path)
- [x] `Echo SubClassOf: Entity and AscensionPath and hasRank some AscensionRank and hasClass some Class and hasOwner some Human`

---

## Step 5: Object Rules
- [x] `Object SubClassOf: Alterable and hasRank some AscensionRank and hasEnchantment some Enchantment`
- [x] `Armor SubClassOf: Object`
- [x] `Weapon SubClassOf: Object`
- [x] `Utility SubClassOf: Object`
- [x] `Armor DisjointWith: Weapon, Utility`
- [x] `Weapon DisjointWith: Utility`

---

## Step 6: Aspect & Enchantment Rules
- [x] `Aspect SubClassOf: Alterable and hasRank some AscensionRank`
- [x] `Enchantment SubClassOf: Alterable`

---

## Step 7: Rank Rules
- [x] `Rank SubClassOf: Immutable`

### Ascension Ranks
- [ ] `Awakened(Asc) SubClassOf: Rank and hasEnchantment exactly 2 Enchantment`
- [ ] `Dormant(Asc) SubClassOf: Rank and hasEnchantment exactly 1 Enchantment`
- [ ] `Ascended SubClassOf: Rank and hasEnchantment exactly 3 Enchantment`
- [ ] `Divine SubClassOf: Rank and hasEnchantment exactly 7 Enchantment`
- [ ] `Sacred SubClassOf: Rank and hasEnchantment exactly 6 Enchantment`
- [ ] `Saint SubClassOf: Rank and hasEnchantment exactly 4 Enchantment`
- [ ] `Sovereign SubClassOf: Rank and hasEnchantment exactly 5 Enchantment`
- [ ] `Spirit SubClassOf: Rank and hasEnchantment exactly 6 Enchantment`
- [ ] `Supreme SubClassOf: Rank and hasEnchantment exactly 5 Enchantment`
- [ ] `Transcendent SubClassOf: Rank and hasEnchantment exactly 4 Enchantment`
- [ ] `Sleeper SubClassOf: Rank and hasEnchantment exactly 1 Enchantment`
- [ ] `Master SubClassOf: Rank and hasEnchantment exactly 3 Enchantment`

---

## Step 8: Disjointness Rules
- [x] `Alterable DisjointWith: Immutable`
- [x] `Ascension DisjointWith: Corruption, Mundane`
- [x] `Aspect DisjointWith: Enchantment, Entity, Object`
- [x] `Beast DisjointWith: Demon, Devil, Monster, Terror, Titan, Tyrant`
- [x] `Class DisjointWith: Rank, SoulCoresType`
- [x] `Corrupted DisjointWith: Cursed, Fallen, Great, Unholy, Awakened(Cor), Dormant(Cor)`
- [x] `Creature DisjointWith: Human`
- [x] `Fire DisjointWith: Neutral, Shadow`
- [x] `Armor DisjointWith: Weapon, Utility`
