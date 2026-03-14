# mandasseafood
<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8" />
  <title>Mandas | Premium Menu</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    :root {
      --blue-bg: #00152a;
      --blue-dark: #000d1a;
      --gold: #d4af37;
      --gold-soft: #e2c76a;
      --text-light: #f7f7f7;
      --text-muted: #c0c0c0;
      --card-bg: #021a33;
      --white: #ffffff;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      background: radial-gradient(circle at top, #00264d 0, #000814 55%, #000000 100%);
      color: var(--text-light);
      min-height: 100vh;
      display: flex;
      justify-content: center;
    }

    .app {
      width: 100%;
      max-width: 480px;
      padding: 16px 14px 32px;
    }

    .card {
      background: linear-gradient(145deg, var(--blue-bg), var(--blue-dark));
      border-radius: 18px;
      padding: 18px 16px 22px;
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.7);
      border: 1px solid rgba(212, 175, 55, 0.25);
    }

    .header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 16px;
    }

    .logo-block {
      max-width: 70%;
    }

    .logo-top {
      font-size: 11px;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold-soft);
      margin-bottom: 4px;
    }

    .logo-main {
      font-size: 24px;
      font-weight: 800;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 2px;
    }

    .logo-sub {
      font-size: 11px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--text-muted);
    }

    .lang-toggle {
      display: inline-flex;
      background: rgba(0, 0, 0, 0.4);
      border-radius: 999px;
      padding: 2px;
      border: 1px solid rgba(212, 175, 55, 0.4);
    }

    .lang-btn {
      border: none;
      background: transparent;
      color: var(--text-muted);
      font-size: 11px;
      padding: 4px 10px;
      border-radius: 999px;
      cursor: pointer;
      transition: all 0.18s ease;
    }

    .lang-btn.active {
      background: var(--gold);
      color: #000;
      font-weight: 600;
    }

    .subtitle {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 14px;
    }

    .subtitle span {
      color: var(--gold-soft);
    }

    .actions-row {
      display: flex;
      gap: 8px;
      margin-bottom: 14px;
      flex-wrap: wrap;
    }

    .btn {
      flex: 1;
      border-radius: 10px;
      padding: 10px 10px;
      font-size: 12px;
      border: none;
      cursor: pointer;
      transition: all 0.18s ease;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      white-space: nowrap;
    }

    .btn-gold {
      background: linear-gradient(135deg, var(--gold), var(--gold-soft));
      color: #000;
      font-weight: 600;
      box-shadow: 0 8px 18px rgba(0, 0, 0, 0.6);
    }

    .btn-gold:hover {
      filter: brightness(1.05);
      transform: translateY(-1px);
    }

    .btn-outline {
      background: transparent;
      color: var(--gold-soft);
      border: 1px solid rgba(212, 175, 55, 0.6);
    }

    .btn-outline:hover {
      background: rgba(212, 175, 55, 0.08);
    }

    .categories-title {
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-muted);
      margin: 6px 0 8px;
    }

    .categories-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
      margin-bottom: 10px;
    }

    .cat-btn {
      border-radius: 10px;
      border: none;
      background: linear-gradient(135deg, var(--gold), #f0d98a);
      color: #000;
      font-size: 12px;
      font-weight: 600;
      padding: 10px 8px;
      cursor: pointer;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.65);
      transition: all 0.18s ease;
      text-align: center;
      min-height: 44px;
    }

    .cat-btn span {
      display: block;
      font-size: 10px;
      font-weight: 500;
      opacity: 0.8;
    }

    .cat-btn.active {
      transform: translateY(-1px);
      box-shadow: 0 14px 26px rgba(0, 0, 0, 0.8);
      outline: 2px solid rgba(255, 255, 255, 0.2);
    }

    .menu-panel {
      margin-top: 6px;
      background: rgba(0, 0, 0, 0.35);
      border-radius: 14px;
      padding: 10px 10px 6px;
      border: 1px solid rgba(255, 255, 255, 0.04);
      max-height: 420px;
      overflow-y: auto;
      scrollbar-width: thin;
      scrollbar-color: rgba(212, 175, 55, 0.7) transparent;
    }

    .menu-panel::-webkit-scrollbar {
      width: 5px;
    }

    .menu-panel::-webkit-scrollbar-track {
      background: transparent;
    }

    .menu-panel::-webkit-scrollbar-thumb {
      background: rgba(212, 175, 55, 0.7);
      border-radius: 999px;
    }

    .category-block {
      margin-bottom: 10px;
      padding-bottom: 8px;
      border-bottom: 1px dashed rgba(255, 255, 255, 0.08);
    }

    .category-block:last-child {
      border-bottom: none;
      margin-bottom: 0;
      padding-bottom: 0;
    }

    .category-title {
      font-size: 14px;
      font-weight: 700;
      color: var(--gold-soft);
      margin-bottom: 6px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    .item {
      margin-bottom: 6px;
    }

    .item-header {
      display: flex;
      justify-content: space-between;
      gap: 8px;
      align-items: baseline;
    }

    .item-name {
      font-size: 13px;
      font-weight: 600;
      color: var(--white);
    }

    .item-price {
      font-size: 12px;
      color: var(--gold-soft);
      white-space: nowrap;
    }

    .item-ingredients {
      font-size: 11px;
      color: var(--text-muted);
      margin-top: 2px;
    }

    .footer-note {
      margin-top: 10px;
      font-size: 10px;
      color: var(--text-muted);
      text-align: center;
    }

    @media (max-width: 360px) {
      .categories-grid {
        grid-template-columns: 1fr;
      }
      .actions-row {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <div class="app">
    <div class="card">
      <div class="header">
        <div class="logo-block">
          <div class="logo-top">TAVERNA</div>
          <div class="logo-main">O MANTAS</div>
          <div class="logo-sub">ΤΑΒΕΡΝΑ Ο ΜΑΝΤΑΣ</div>
        </div>
        <div class="lang-toggle">
          <button class="lang-btn active" data-lang="gr">ΕΛ</button>
          <button class="lang-btn" data-lang="en">EN</button>
        </div>
      </div>

      <div class="subtitle" id="subtitle">
        Παραδοσιακή ψαροταβέρνα στη <span>Σούδα</span>.
      </div>

      <div class="actions-row">
        <button class="btn btn-gold" id="btn-review">
          ★ Google Review
        </button>
        <button class="btn btn-outline" id="btn-navigate">
          ➜ Navigate
        </button>
      </div>

      <div class="categories-title" id="categories-title">
        ΚΑΤΗΓΟΡΙΕΣ ΜΕΝΟΥ
      </div>

      <div class="categories-grid" id="categories-grid">
        <!-- Κατηγορίες με κουμπιά θα μπουν από JS -->
      </div>

      <div class="menu-panel" id="menu-panel">
        <!-- Περιεχόμενο κατηγορίας από JS -->
      </div>

      <div class="footer-note" id="footer-note">
        Οι τιμές και τα πιάτα μπορεί να αλλάξουν χωρίς προειδοποίηση.
      </div>
    </div>
  </div>

  <script>
    const MAPS_URL = "https://www.google.com/maps/place/Mandas/@35.4903414,24.0623267,17z/data=!3m1!5s0x149c7e1b1f9e4dd1:0x1e209344b01aa47d!4m15!1m8!3m7!1s0x149c7e1b1f073eed:0x60d3d8e4ed331298!2sMandas!8m2!3d35.49039!4d24.062254!10e5!16s%2Fg%2F1tv40mq8!3m5!1s0x149c7e1b1f073eed:0x60d3d8e4ed331298!8m2!3d35.49039!4d24.062254!16s%2Fg%2F1tv40mq8?entry=ttu";

    const state = {
      lang: "gr",
      activeCategoryId: "salads"
    };

    const menuData = [
      {
        id: "salads",
        title_gr: "Σαλάτες",
        title_en: "Salads",
        short_gr: "Φρέσκες σαλάτες",
        short_en: "Fresh salads",
        items: [
          {
            id: "vegetarian",
            name_gr: "Vegetarian",
            name_en: "Vegetarian",
            ingredients_gr: "Ντομάτα, Αγγούρι, Αβοκάντο, Φέτα, Ελιά, Λευκή σως, Μαϊντανός",
            ingredients_en: "Tomato, Cucumber, Avocado, Feta cheese, Olive, White sauce, Parsley",
            price: "5.99"
          },
          {
            id: "greek-salad",
            name_gr: "Χωριάτικη",
            name_en: "Greek Salad",
            ingredients_gr: "Ντομάτα, Αγγούρι, Κρεμμύδι, Ελιά, Φέτα, Ελαιόλαδο",
            ingredients_en: "Tomato, Cucumber, Onion, Olive, Feta cheese, Olive oil",
            price: "5.99"
          },
          {
            id: "spanish",
            name_gr: "Ισπανική",
            name_en: "Spanish",
            ingredients_gr: "Ντομάτα, Αγγούρι, Αβοκάντο, Φέτα, Ελιά, Ελαιόλαδο, Μαϊντανός",
            ingredients_en: "Tomato, Cucumber, Avocado, Feta cheese, Olive, Olive oil, Parsley",
            price: "5.99"
          },
          {
            id: "cretan",
            name_gr: "Κρητική",
            name_en: "Cretan Salad",
            ingredients_gr: "Ντομάτα, Αγγούρι, Κρεμμύδι, Ελιά, Φέτα, Ελαιόλαδο, Ρίγανη",
            ingredients_en: "Tomato, Cucumber, Onion, Olive, Feta cheese, Olive oil, Oregano",
            price: "5.99"
          },
          {
            id: "hungarian",
            name_gr: "Ουγγρική",
            name_en: "Hungarian",
            ingredients_gr: "Ντομάτα, Αγγούρι, Κρεμμύδι, Ελιά, Φέτα, Ελαιόλαδο, Μαϊντανός",
            ingredients_en: "Tomato, Cucumber, Onion, Olive, Feta cheese, Olive oil, Parsley",
            price: "5.99"
          },
          {
            id: "mixed",
            name_gr: "Ανάμεικτη",
            name_en: "Mixed Salad",
            ingredients_gr: "Ντομάτα, Αγγούρι, Κρεμμύδι, Ελιά, Φέτα, Ελαιόλαδο, Μαϊντανός",
            ingredients_en: "Tomato, Cucumber, Onion, Olive, Feta cheese, Olive oil, Parsley",
            price: "5.99"
          }
        ]
      },
      {
        id: "sides",
        title_gr: "Συνοδευτικά",
        title_en: "Sides",
        short_gr: "Μικρά πιάτα",
        short_en: "Side dishes",
        items: [
          { id: "potato", name_gr: "Πατάτα", name_en: "Potato", price: "3.99" },
          { id: "fried-tomato", name_gr: "Τηγανητή ντομάτα", name_en: "Fried tomato", price: "3.99" },
          { id: "season-salad", name_gr: "Σαλάτα εποχής", name_en: "Season salad", price: "3.99" },
          { id: "roots", name_gr: "Ρίζες", name_en: "Roots", price: "3.99" },
          { id: "cheese-oil", name_gr: "Τυρί με λάδι", name_en: "Cheese with olive oil", price: "3.99" },
          { id: "bread", name_gr: "Ψωμί", name_en: "Bread", price: "3.99" }
        ]
      },
      {
        id: "seafood",
        title_gr: "Θαλασσινά",
        title_en: "Sea Food",
        short_gr: "Φρέσκα θαλασσινά",
        short_en: "Fresh seafood",
        items: [
          { id: "fresh-calamari", name_gr: "Καλαμάρι φρέσκο", name_en: "Small squids fresh", price: "14.00" },
          { id: "frozen-calamari", name_gr: "Καλαμάρι κατεψυγμένο", name_en: "Small squids frozen", price: "12.00" },
          { id: "fresh-shrimps", name_gr: "Γαρίδες φρέσκες", name_en: "Shrimps fresh", price: "17.00" },
          { id: "frozen-shrimps", name_gr: "Γαρίδες κατεψυγμένες", name_en: "Shrimps frozen", price: "15.00" }
        ]
      },
      {
        id: "meza-fish",
        title_gr: "Μεζέδες Ψαριών",
        title_en: "Meza | Fish",
        short_gr: "Μεζέδες για παρέα",
        short_en: "Fish meze",
        items: [
          { id: "mussels", name_gr: "Μύδια", name_en: "Mussels", price: "18.00" },
          { id: "squid", name_gr: "Καλαμάρι (μεζές)", name_en: "Squid", price: "18.00" },
          { id: "anchovy", name_gr: "Γαύρος", name_en: "Anchovy", price: "12.00" },
          { id: "eel", name_gr: "Χέλι", name_en: "Eel", price: "10.00" },
          { id: "shrimp-meza", name_gr: "Γαρίδα (μεζές)", name_en: "Shrimp", price: "10.00" },
          { id: "tuna-meza", name_gr: "Τόνος (μεζές)", name_en: "Tuna (meza)", price: "30.00" },
          { id: "bonito-meza", name_gr: "Κολιός (μεζές)", name_en: "Bonito (meza)", price: "30.00" },
          { id: "kallari-meza", name_gr: "Καλάρια (μεζές)", name_en: "Spanish Mackerel", price: "30.00" }
        ]
      },
      {
        id: "stuffed",
        title_gr: "Παραδοσιακά",
        title_en: "Stuffed Dishes",
        short_gr: "Παραδοσιακά πιάτα",
        short_en: "Traditional dishes",
        items: [
          {
            id: "dolmadakia",
            name_gr: "Ντολμαδάκια",
            name_en: "Dolmadakia",
            ingredients_gr: "Αμπελόφυλλα γεμιστά με ρύζι",
            ingredients_en: "Stuffed vine leaves with rice",
            price: "3.50"
          },
          {
            id: "gemista",
            name_gr: "Γεμιστά",
            name_en: "Gemista",
            ingredients_gr: "Κολοκυθάκια γεμιστά με ρύζι",
            ingredients_en: "Stuffed zucchini with rice",
            price: "5.00"
          },
          {
            id: "kolokithakia",
            name_gr: "Κολοκυθάκια",
            name_en: "Kolokithakia",
            ingredients_gr: "Κολοκυθάκια γεμιστά με ρύζι",
            ingredients_en: "Stuffed zucchini with rice",
            price: "5.00"
          },
          {
            id: "papoutsakia",
            name_gr: "Παπουτσάκια",
            name_en: "Papoutsakia",
            ingredients_gr: "Αμπελόφυλλα γεμιστά με ρύζι",
            ingredients_en: "Stuffed vine leaves with rice",
            price: "5.00"
          },
          {
            id: "lahanodolmades",
            name_gr: "Λαχανοντολμάδες",
            name_en: "Lahanodolmades",
            ingredients_gr: "Λάχανο γεμιστό με ρύζι",
            ingredients_en: "Cabbage stuffed with rice",
            price: "5.00"
          }
        ]
      },
      {
        id: "beers",
        title_gr: "Μπύρες",
        title_en: "Beers",
        short_gr: "Μπύρες",
        short_en: "Beers",
        items: [
          { id: "amstel", name_gr: "Amstel", name_en: "Amstel", price: "4.00" },
          { id: "amstel-radler", name_gr: "Amstel Radler", name_en: "Amstel Radler", price: "4.00" },
          { id: "heineken", name_gr: "Heineken", name_en: "Heineken", price: "4.00" },
          { id: "alfa", name_gr: "Alfa", name_en: "Alfa", price: "4.00" },
          { id: "alfa-weiss", name_gr: "Alfa Weiss", name_en: "Alfa Weiss", price: "5.00" },
          { id: "fischer", name_gr: "Fischer", name_en: "Fischer", price: "5.00" },
          { id: "sol", name_gr: "Sol", name_en: "Sol", price: "5.00" },
          { id: "corona", name_gr: "Corona", name_en: "Corona", price: "5.00" }
        ]
      },
      {
        id: "wines",
        title_gr: "Κρασιά",
        title_en: "Wines",
        short_gr: "Κρασιά",
        short_en: "Wines",
        items: [
          {
            id: "house-white",
            name_gr: "Χύμα Λευκό Γλυκό/Ημίγλυκο",
            name_en: "House Sweet/Medium Semi White Wine",
            price: "10.00"
          },
          {
            id: "house-red",
            name_gr: "Χύμα Ερυθρό Ημίγλυκο",
            name_en: "House Semi Sweet Red Wine",
            price: "10.00"
          },
          {
            id: "maglen",
            name_gr: "Maglen Tsantalis Ερυθρό Ξηρό (187ml)",
            name_en: "Maglen Tsantalis Red Dry Wine (187ml)",
            price: "5.00"
          },
          {
            id: "agiorgitiko",
            name_gr: "Αγιωργίτικο Ερυθρό Ξηρό (187ml)",
            name_en: "Agiorgitiko Red Dry Wine (187ml)",
            price: "5.00"
          }
        ]
      },
      {
        id: "soft-drinks",
        title_gr: "Αναψυκτικά",
        title_en: "Soft Drinks",
        short_gr: "Αναψυκτικά & Χυμοί",
        short_en: "Soft drinks & Juices",
        items: [
          { id: "coca-cola", name_gr: "Coca Cola", name_en: "Coca Cola", price: "3.00" },
          { id: "coca-cola-zero", name_gr: "Coca Cola Zero", name_en: "Coca Cola Zero", price: "3.00" },
          { id: "sprite", name_gr: "Sprite", name_en: "Sprite", price: "3.00" },
          { id: "fanta-blue", name_gr: "Fanta Blue", name_en: "Fanta Blue", price: "3.00" },
          { id: "pepsi", name_gr: "Pepsi (Cola, Max, Twist)", name_en: "Pepsi (Cola, Max, Twist)", price: "3.00" },
          {
            id: "juices-mixed",
            name_gr: "Χυμοί (Πορτοκαλάδα, Λεμονάδα, Φράουλα, Ανανάς, Μήλο, Μάνγκο, Λεμονόχορτο, Energy, Blood Soda)",
            name_en: "Juices (Orange, Lemon, Strawberry, Pineapple, Apple, Mango, Lemongrass, Energy, Blood Soda)",
            price: "3.00"
          },
          { id: "juice-500", name_gr: "Χυμός 500ml", name_en: "Juice 500ml", price: "3.00" },
          { id: "water-500", name_gr: "Νερό 500ml", name_en: "Bottle of Water 500ml", price: "1.00" },
          { id: "mythos-33", name_gr: "Mythos 33cl", name_en: "Mythos 33cl", price: "5.00" },
          { id: "water-1l", name_gr: "Νερό 1lt", name_en: "Bottle of Water 1lt", price: "1.50" },
          { id: "sparkling-330", name_gr: "Ανθρακούχο νερό 330ml", name_en: "Sparkling water 330ml", price: "2.00" },
          { id: "sparkling-750", name_gr: "Ανθρακούχο νερό 750ml", name_en: "Sparkling water 750ml", price: "5.00" },
          { id: "organic-blood", name_gr: "Organic Blood, Ρόδι", name_en: "Organic Blood, Pomegranate", price: "5.00" },
          { id: "fresh-orange", name_gr: "Φρέσκος χυμός πορτοκάλι", name_en: "Fresh Orange Juice", price: "5.00" }
        ]
      }
    ];

    const subtitleEl = document.getElementById("subtitle");
    const categoriesTitleEl = document.getElementById("categories-title");
    const footerNoteEl = document.getElementById("footer-note");
    const categoriesGridEl = document.getElementById("categories-grid");
    const menuPanelEl = document.getElementById("menu-panel");

    function renderCategories() {
      categoriesGridEl.innerHTML = "";
      menuData.forEach(cat => {
        const btn = document.createElement("button");
        btn.className = "cat-btn" + (cat.id === state.activeCategoryId ? " active" : "");
        btn.dataset.id = cat.id;

        const title = document.createElement("div");
        title.textContent = state.lang === "gr" ? cat.title_gr : cat.title_en;

        const sub = document.createElement("span");
        sub.textContent = state.lang === "gr" ? cat.short_gr : cat.short_en;

        btn.appendChild(title);
        btn.appendChild(sub);

        btn.addEventListener("click", () => {
          state.activeCategoryId = cat.id;
          renderCategories();
          renderMenuPanel();
        });

        categoriesGridEl.appendChild(btn);
      });
    }

    function renderMenuPanel() {
      menuPanelEl.innerHTML = "";
      const cat = menuData.find(c => c.id === state.activeCategoryId);
      if (!cat) return;

      const block = document.createElement("div");
      block.className = "category-block";

      const title = document.createElement("div");
      title.className = "category-title";
      title.textContent = state.lang === "gr" ? cat.title_gr : cat.title_en;
      block.appendChild(title);

      cat.items.forEach(item => {
        const itemEl = document.createElement("div");
        itemEl.className = "item";

        const header = document.createElement("div");
        header.className = "item-header";

        const name = document.createElement("div");
        name.className = "item-name";
        name.textContent = state.lang === "gr" ? item.name_gr : item.name_en;

        const price = document.createElement("div");
        price.className = "item-price";
        price.textContent = item.price + " €";

        header.appendChild(name);
        header.appendChild(price);
        itemEl.appendChild(header);

        if (item.ingredients_gr || item.ingredients_en) {
          const ing = document.createElement("div");
          ing.className = "item-ingredients";
          ing.textContent =
            state.lang === "gr"
              ? (item.ingredients_gr || "")
              : (item.ingredients_en || item.ingredients_gr || "");
          itemEl.appendChild(ing);
        }

        block.appendChild(itemEl);
      });

      menuPanelEl.appendChild(block);
    }

    function applyLangTexts() {
      if (state.lang === "gr") {
        subtitleEl.innerHTML = 'Παραδοσιακή ψαροταβέρνα στη <span>Σούδα</span>.';
        categoriesTitleEl.textContent = "ΚΑΤΗΓΟΡΙΕΣ ΜΕΝΟΥ";
        footerNoteEl.textContent = "Οι τιμές και τα πιάτα μπορεί να αλλάξουν χωρίς προειδοποίηση.";
      } else {
        subtitleEl.innerHTML = 'Traditional fish tavern in <span>Souda</span>.';
        categoriesTitleEl.textContent = "MENU CATEGORIES";
        footerNoteEl.textContent = "Dishes and prices may change without prior notice.";
      }
    }

    document.querySelectorAll(".lang-btn").forEach(btn => {
      btn.addEventListener("click", () => {
        const lang = btn.dataset.lang;
        if (lang === state.lang) return;
        state.lang = lang;
        document.querySelectorAll(".lang-btn").forEach(b => b.classList.remove("active"));
        btn.classList.add("active");
        applyLangTexts();
        renderCategories();
        renderMenuPanel();
      });
    });

    document.getElementById("btn-review").addEventListener("click", () => {
      window.open(MAPS_URL, "_blank");
    });

    document.getElementById("btn-navigate").addEventListener("click", () => {
      window.open(MAPS_URL, "_blank");
    });

    applyLangTexts();
    renderCategories();
    renderMenuPanel();
  </script>
</body>
</html>
