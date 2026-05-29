# Graph Report - /workspace/examples/multiagent-patterns/skills  (2026-05-29)

## Corpus Check
- Corpus is ~1,911 words - fits in a single context window. You may not need a graph.

## Summary
- 67 nodes · 106 edges · 7 communities
- Extraction: 94% EXTRACTED · 6% INFERRED · 0% AMBIGUOUS · INFERRED: 6 edges (avg confidence: 0.72)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_AgentStaticLoader Agent Discovery & Loading|AgentStaticLoader: Agent Discovery & Loading]]
- [[_COMMUNITY_Progressive Disclosure Framework Registry, Hook, Skill Loading|Progressive Disclosure Framework: Registry, Hook, Skill Loading]]
- [[_COMMUNITY_SkillsConfig Skill Registry, Hook & sqlAssistantAgent Assembly|SkillsConfig: Skill Registry, Hook & sqlAssistantAgent Assembly]]
- [[_COMMUNITY_Inventory Management Skill Tables, Rules & Reorder Query|Inventory Management Skill: Tables, Rules & Reorder Query]]
- [[_COMMUNITY_SkillsApplication Spring Boot Entry & Lifecycle|SkillsApplication: Spring Boot Entry & Lifecycle]]
- [[_COMMUNITY_Sales Analytics Skill Tables, Rules & Top-10 Query|Sales Analytics Skill: Tables, Rules & Top-10 Query]]
- [[_COMMUNITY_SkillsRunner Demo Execution & RunnableConfig|SkillsRunner: Demo Execution & RunnableConfig]]

## God Nodes (most connected - your core abstractions)
1. `inventory_management Skill (products/warehouses/inventory/stock_movements)` - 11 edges
2. `sales_analytics Skill (customers/orders/order_items)` - 10 edges
3. `AgentStaticLoader` - 5 edges
4. `products Table (product_id, sku, category, unit_cost, reorder_point)` - 5 edges
5. `SkillsConfig` - 4 edges
6. `Bean` - 4 edges
7. `SkillsRunner` - 4 edges
8. `ClasspathSkillRegistry` - 4 edges
9. `SkillsAgentHook (read_skill + SkillsInterceptor)` - 4 edges
10. `SKILL.md Format (YAML Frontmatter + Markdown)` - 4 edges

## Surprising Connections (you probably didn't know these)
- `sales_analytics Skill (customers/orders/order_items)` --semantically_similar_to--> `inventory_management Skill (products/warehouses/inventory/stock_movements)`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/skills/src/main/resources/skills/sales_analytics/SKILL.md → examples/multiagent-patterns/skills/src/main/resources/skills/inventory_management/SKILL.md
- `customers Table (customer_id, name, email, status, tier)` --semantically_similar_to--> `products Table (product_id, sku, category, unit_cost, reorder_point)`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/skills/src/main/resources/skills/sales_analytics/SKILL.md → examples/multiagent-patterns/skills/src/main/resources/skills/inventory_management/SKILL.md
- `Revenue Calculation Rule (only completed orders)` --semantically_similar_to--> `Available Stock Rule (quantity_on_hand > 0)`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/skills/src/main/resources/skills/sales_analytics/SKILL.md → examples/multiagent-patterns/skills/src/main/resources/skills/inventory_management/SKILL.md
- `High-Value Order Rule (total_amount > 1000)` --semantically_similar_to--> `Reorder Rule (SUM(qty) across warehouses <= reorder_point)`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/skills/src/main/resources/skills/sales_analytics/SKILL.md → examples/multiagent-patterns/skills/src/main/resources/skills/inventory_management/SKILL.md
- `Top-10 Customer Revenue Query (SQL example)` --semantically_similar_to--> `Below Reorder Point Query (SQL example)`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/skills/src/main/resources/skills/sales_analytics/SKILL.md → examples/multiagent-patterns/skills/src/main/resources/skills/inventory_management/SKILL.md

## Hyperedges (group relationships)
- **Framework Skill Loading Chain: Registry->Hook->Agent** — n2, n3, n6 [EXTRACTED 1.00]
- **Sales Analytics ER Chain: customers->orders->order_items** — n12, n13, n14 [EXTRACTED 1.00]
- **Inventory Management ER Chain: products<-inventory<-stock_movements** — n18, n20, n21 [EXTRACTED 1.00]

## Communities (7 total, 0 thin omitted)

### Community 0 - "AgentStaticLoader: Agent Discovery & Loading"
Cohesion: 0.27
Nodes (8): Agent, AgentLoader, Override, ReactAgent, String, List, Nonnull, AgentStaticLoader

### Community 1 - "Progressive Disclosure Framework: Registry, Hook, Skill Loading"
Cohesion: 0.20
Nodes (11): Skills (Progressive Disclosure) Pattern, ClasspathSkillRegistry, Spring Boot App Config (skills-sql-assistant), DashScope API Key (AI Provider), SkillsAgentHook (read_skill + SkillsInterceptor), read_skill Tool, SkillsInterceptor (Prompt Injection), ReactAgent (sqlAssistantAgent) (+3 more)

### Community 2 - "SkillsConfig: Skill Registry, Hook & sqlAssistantAgent Assembly"
Cohesion: 0.42
Nodes (6): ChatModel, SkillRegistry, SkillsConfig, SkillsAgentHook, Bean, ReactAgent

### Community 3 - "Inventory Management Skill: Tables, Rules & Reorder Query"
Cohesion: 0.36
Nodes (9): inventory_management Skill (products/warehouses/inventory/stock_movements), products Table (product_id, sku, category, unit_cost, reorder_point), warehouses Table (warehouse_id, name, location, capacity), inventory Table (product_id FK, warehouse_id FK, quantity_on_hand), stock_movements Table (movement_type, quantity, reference_number), Available Stock Rule (quantity_on_hand > 0), Reorder Rule (SUM(qty) across warehouses <= reorder_point), Active Products Rule (discontinued=false only) (+1 more)

### Community 4 - "SkillsApplication: Spring Boot Entry & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, SkillsApplication, Bean, String

### Community 5 - "Sales Analytics Skill: Tables, Rules & Top-10 Query"
Cohesion: 0.36
Nodes (8): sales_analytics Skill (customers/orders/order_items), customers Table (customer_id, name, email, status, tier), orders Table (order_id, customer_id FK, status, total_amount, region), order_items Table (item_id, order_id FK, product_id, quantity, unit_price, discount), Active Customer Rule (status=active + signup>90d), Revenue Calculation Rule (only completed orders), High-Value Order Rule (total_amount > 1000), Top-10 Customer Revenue Query (SQL example)

### Community 6 - "SkillsRunner: Demo Execution & RunnableConfig"
Cohesion: 0.36
Nodes (5): ApplicationArguments, ApplicationRunner, SkillsRunner, Override, ReactAgent

## Knowledge Gaps
- **6 isolated node(s):** `Override`, `String`, `YAML Frontmatter (name/description)`, `Active Customer Rule (status=active + signup>90d)`, `Active Products Rule (discontinued=false only)` (+1 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `inventory_management Skill (products/warehouses/inventory/stock_movements)` connect `Inventory Management Skill: Tables, Rules & Reorder Query` to `Progressive Disclosure Framework: Registry, Hook, Skill Loading`, `Sales Analytics Skill: Tables, Rules & Top-10 Query`?**
  _High betweenness centrality (0.070) - this node is a cross-community bridge._
- **Why does `sales_analytics Skill (customers/orders/order_items)` connect `Sales Analytics Skill: Tables, Rules & Top-10 Query` to `Progressive Disclosure Framework: Registry, Hook, Skill Loading`, `Inventory Management Skill: Tables, Rules & Reorder Query`?**
  _High betweenness centrality (0.062) - this node is a cross-community bridge._
- **Why does `List` connect `AgentStaticLoader: Agent Discovery & Loading` to `SkillsConfig: Skill Registry, Hook & sqlAssistantAgent Assembly`?**
  _High betweenness centrality (0.052) - this node is a cross-community bridge._
- **What connects `Override`, `String`, `YAML Frontmatter (name/description)` to the rest of the system?**
  _6 weakly-connected nodes found - possible documentation gaps or missing edges._