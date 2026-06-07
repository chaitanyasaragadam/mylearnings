# Service Catalog Data Model — Complete Transcript

Source video: `7.1 Service Catalog - Data Model-20211027_121324.mp4`

Duration: approximately 51 minutes 17 seconds.

Note: this is a complete time-coded visual/learning transcript created from the demo screen content and timeline. It is not a verbatim speech-to-text transcript.

## Timeline

### 00:00–00:20
Opening screen shows the presenter name, then the demo machine and browser are brought into view.

### 00:20–01:30
The demo opens a ServiceNow instance and lands in Service Catalog. The first visible model is the user-facing catalog: category cards such as Services, Hardware, Software, Office, Desktops, Mobiles, and a right-side cart/top-request area.

### 01:30–02:30
The presenter moves from the catalog homepage into platform/admin navigation and opens Catalog Items. This shifts the focus from the end-user view to the configuration/data-model view.

### 02:30–03:10
The Catalog Items list is shown. It contains item records such as Service Category Request, Access, Standard Laptop, Apple iPad 3, Cisco Jabber, Samsung Galaxy, Adobe Acrobat Pro, Paper and Supplies, and others. Columns include name, short description, active, roles, catalogs, category, price, type, and updated.

### 02:50–04:20
A generic hierarchy view for Catalog Item is opened. It shows that catalog items are central records and that multiple tables either extend or reference this model. The demo scrolls around related tables such as content items, product/catalog items, record producers, order guides, wizard launchers, variables, catalog variable sets, available-for relationships, connected content, related catalog items, and catalog UI policy actions.

### 04:30–05:00
The Standard Laptop catalog item order page is opened. The page shows an item picture and product description for an X1 Carbon, plus variables such as “Request this for?”, Optional Software, Adobe Acrobat, Adobe Photoshop, and Additional software requirements.

### 05:00–06:00
The Options table is opened for the Standard Laptop cart item. It shows one row per variable answer, with columns such as Cart item, Question, Order, SC cat item option, and Value. The demo highlights that selected/unselected checkboxes and text answers are stored as option records.

### 06:00–07:00
A Requested Item record is opened. The RITM shows the catalog item, request, stage, quantity, and a Variables section. This demonstrates how catalog variable answers are rendered back on the requested item after submission.

### 07:00–08:00
The hierarchy/data model for Options is inspected. The demo uses ServiceNow table hierarchy tools to understand how the option records relate back to questions and other catalog entities.

### 08:00–09:00
The presenter inspects item/cart option values, showing that the actual stored values are separate rows instead of flat fields on the requested item form.

### 09:00–10:00
A Record Producer named Create Incident is opened from the catalog. The end-user form asks for Urgency and More information, then submits to create an Incident record.

### 10:00–11:00
The Incident form layout is configured to expose the Incident Variable Editor. This shows how record-producer answers can be rendered on the target task/incident form even though the target table is not a catalog request table.

### 11:00–12:00
The Question Answer table dictionary is opened. Columns include Order, Question, Class, Created by, Created, Sys ID, Updates, Updated by, Updated, Table name, Table sys ID, and Value. This is the key table for record-producer answer storage.

### 12:00–13:00
The Item Produced Records list is inspected. It maps a producer to the produced task record and task type, for example Create Incident creating an Incident, or other producers creating Change Requests.

### 13:00–14:00
The demo returns to the Service Catalog and then back to internal tables to continue tracing the submitted values.

### 14:00–15:00
The Options list columns are personalized. Selected columns include Cart item, Question, Order, SC cat item option, and Value. This helps inspect catalog variable storage without unrelated columns.

### 15:00–16:00
The Multi Row Question Answers table is opened. Rows are grouped by row index. Each row represents one cell in a multi-row variable set: Question, parent requested item, parent table name, row index, related SC item option, value, and multi-row set.

### 16:00–17:00
The presenter searches catalog items and moves between record-producer/package/content-item examples to compare how normal items, record producers, and special catalog item types are represented.

### 17:00–18:00
More Multi Row Question Answer rows are shown. Multiple rows share the same row index, forming one logical row in the table variable. Values such as color, quantity, storage, and device type appear as separate records.

### 18:00–19:00
The Cart Item table is inspected for a Corporate Mobile Devices bulk-order item. A single cart-item record points to the catalog item and quantity before checkout.

### 19:00–20:00
The Options table is inspected for the bulk-order flow. Values such as Storage, Quantity, Business Justification, Department, Device Type, and Color appear as separate option rows.

### 20:00–21:00
Catalog UI Policies are opened. The list shows short descriptions, linked catalog item or variable set, conditions, reverse-if-false, on-load, inherit, updated, and order. This shows where catalog form behavior is configured.

### 21:00–22:00
A Catalog Task record is opened from a requested item. The task has request item linkage, state, priority, approval, description/work notes, and related tabs. This demonstrates the fulfillment side of the request model.

### 22:00–23:00
The Corporate Mobile Devices bulk-order form is opened. It shows normal variables such as Department and Business Justification plus a Mobile Devices Set table with columns Device Type, Storage, Color, and Quantity.

### 23:00–24:00
An Access requested item is opened to compare another catalog item/request flow and its related catalog tasks.

### 24:00–25:00
A variable creation form is shown. The variable is of type Requested For, assigned to the Standard Laptop catalog item, with question text, name, tooltip, and other configuration tabs.

### 25:00–26:00
A Request record is shown with its Requested Items related list. The request acts as the container; requested item records carry item-specific lifecycle and variable data.

### 26:00–27:00
The Standard Laptop catalog item form is opened. The item has fields like name, catalog, category, state, owner, short description, rich-text description, pricing, process engine, picture, portal settings, and buttons such as Try it and Edit in Catalog Builder.

### 27:00–28:00
Cache Flush records are inspected. The demo shows that catalog changes produce cache-related entries and that catalog item/category rendering is cache-aware.

### 28:00–29:00
The cache flush list remains visible, highlighting multiple cache names and keys related to catalog and category entries.

### 29:00–30:00
The presenter switches to source code. Finder/cache configuration code is shown for catalog relationships, mapping tables such as categories, catalog items, criteria, groups, locations, and M2M relationship tables to cache finders.

### 30:00–31:00
The demo returns briefly to the Standard Laptop order page and then back to code, keeping the connection between runtime catalog UI and platform internals.

### 31:00–32:00
Stale category cache code is inspected. The code handles category cache invalidation and parent-category expiration when catalog/category relationships change.

### 32:00–33:00
Catalog constants are shown in code. Constants include catalog item, catalog variable, variable set, catalog UI policy, catalog data lookup, catalog policy action, catalog caches, category caches, no-order/no-cart settings, and script event names.

### 33:00–34:00
Cache Inspector is opened. Entries such as category cache and item-category cache appear, showing hashed keys/sub-names that represent cached catalog data.

### 34:00–35:00
Cache Inspector is filtered for catalog-related entries, including catalog client scripts, catalog data lookup cache, and category cache names.

### 35:00–36:00
The demo returns to the Service Catalog home page with cart state visible, reinforcing the user-facing result of the underlying data model.

### 36:00–37:00
Cache Inspector is shown again, this time at a broader private-cache list level.

### 37:00–38:00
The Service Catalog home page appears again with the shopping cart state and top requests.

### 38:00–39:00
A Category form for Office is opened. It shows catalog, active state, parent, description, image/icon, and related tabs such as Catalog Items, Categories, Available for, and Not Available for.

### 39:00–40:00
Catalog Java code is shown. The presenter points at logic that associates items to a catalog using catalog-item/category relationships and the sc_catalogs field.

### 40:00–41:00
The screen is split between code and the ServiceNow catalog item form, connecting the code-level catalog relationship with the visible item configuration.

### 41:00–42:00
Code navigation opens catalog/category cache classes, including category cart-item cache and related catalog Java classes.

### 42:00–43:00
Catalog item code is inspected, showing variables, client-script checks, run-scripts handling, and catalog constants.

### 43:00–44:00
User item cache manager code is shown. It builds cache keys using item id, mobile flag, and user id/domain separation data.

### 44:00–45:00
SCStaleCacheListener code is shown. It looks up finder configuration based on table name and uses direct, excluded, or table-hierarchy lookup to decide cache invalidation behavior.

### 45:00–46:00
The Category list is filtered to show a category such as Tablets with parent Hardware. This demonstrates category hierarchy and item placement.

### 46:00–47:00
A browser new tab appears briefly; this portion is not materially instructional for the service catalog data model.

### 47:00–48:00
Question.java is opened. Code shows private caches for Question, Question Choice, Question Regex, and a variable type map.

### 48:00–49:00
Cache finder configuration is revisited, including relationships involving catalog item/category, variable/item-option tables, user criteria, and group/location criteria.

### 49:00–50:00
Question cache registration is highlighted, including Question, Question Choice, and Question Regex cache pairs.

### 50:00–51:00
The variable type map is shown. Numeric type values map to question/variable types such as yes/no, multi-line text, multiple choice, select box, single-line text, reference, date, date-time, label, macro, UI page, lookup select box, list collector, and containers.

### 51:00–51:17
The demo ends on a Catalog Wizard / Catalog Item Builder configuration screen. The wizard has steps such as Details, Location, Questions, Settings, Access, and Fulfillment, showing a guided way to create catalog items.

## Core data model distilled from the demo

- **Catalog browsing layer:** `sc_catalog`, `sc_category`, category-item relationships, and catalog item records decide what users can find and order.
- **Item definition layer:** `sc_cat_item` and its extended/specialized item types define orderable things such as normal catalog items, record producers, order guides, content items, and wizard-driven items.
- **Variable definition layer:** `item_option_new` stores variable/question definitions; variable sets group variables for reuse.
- **Cart/order capture layer:** `sc_cart_item` represents an in-cart item; `sc_item_option` stores submitted answer values.
- **Request execution layer:** `sc_request` groups the order; `sc_req_item` represents each ordered item; `sc_task` represents fulfillment work.
- **Record producer layer:** target task records are connected through produced-record mappings and question-answer rows.
- **Multi-row variable layer:** `sc_multi_row_question_answer` stores each table-variable cell with row index, question, value, parent record, and multi-row set.
- **Behavior layer:** catalog UI policies, UI policy actions, client scripts, and data lookup rules control visibility, mandatory state, defaults, and form behavior.
- **Performance layer:** catalog/category/question caches and cache-flush records keep catalog rendering fast while still reacting to configuration changes.
