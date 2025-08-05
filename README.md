# FishOntology 📘

A domain-specific semantic web ontology for fish taxonomy, anatomy and ecology — developed for the “Semantic Web” course. It includes automated classification of unknown fish based on metadata restrictions.

---

## 🧱 Project structure


├── Report_web_semantico‑2.pdf -> Course report (in Italian)
├── ontology.ttl ->Turtle-format FO (Fish Ontology)
├── catalog‑v001.xml -> OWL catalog file for tool support
├── grafo.graph -> OntoGraf model file (Protégé)
├── immagineGrafo.{jpg,png} -> Graph images generated from ontology
├── ontology.properties -> Configuration for Protégé/OntoGraf
└── org.protege.ontograf.jar -> Plugin to enable graph view.

---

## ⚙️ Prerequisites

- **Java ≥ 8** (to run Protégé and OntoGraf plugin)  
- **[Protégé v5.x or newer](https://protege.stanford.edu)** with HermiT, Pellet or FaCT++ reasoner installed  
- Optional: a text editor if you prefer code‑view

---

## 🚀 Getting started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/FabioNotaro2001/FishOntology.git
   cd FishOntology

    Open the ontology:

    Launch Protégé and open ontology.ttl. It will automatically detect the OWL ontology.

    Install the OntoGraf plugin (if not already available):

        Place org.protege.ontograf.jar in your Protégé plugins/ directory

        Restart Protégé

    Generate/visualize the graph:

        In Protégé, switch to the OntoGraf tab

        Load grafo.graph or recreate it via the right-click context menu

        View the full graph via immagineGrafo.jpg or PNG

    Run the reasoner (e.g. HermiT):

    With the reasoner active, you can perform automated classification. For example, add a new individual of type Specimen with restrictions on properties like hasShape or hasHabitat. The reasoner will infer the most specific fish taxa class.

        Note: The FO uses Protégé reasoner capabilities (e.g. Hermit, FaCT++, Pellet) for automated classification, a feature described in the original Fish Ontology framework
        PeerJ
        .

🧠 How it works

    Built in OWL 2 / Turtle format (ontology.ttl)

    Encodes hierarchical classes (e.g. superclass Actinopterygii, subclasses for clades and orders)

    Uses semantic restrictions such as:

        hasBodyShape owl:someValuesFrom ShapeType

        livesIn owl:someValuesFrom HabitatType

        feedsOn owl:someValuesFrom PreyType

    When you create a new Specimen individual and assert such restrictions, the reasoner infers the most specific fish taxon.

This automated classification mechanism is a unique capability of FO and was a central goal of the semantic web project
PeerJ
.
🪪 Sample inference (step-by-step)

    Create a new individual fish01 of type Specimen.

    Add assertions:

        fish01 hasBodyShape Streamlined

        fish01 livesIn FreshwaterRiver

        fish01 feedsOn InsectLarvae

    Run the reasoner — if a unique taxon matches (e.g. Perciformes), it will assign that class.

You can experiment with different combinations of restrictions and explore how the ontology supports fish taxon inference.
🧪 Testing or extending

    Edit ontology.ttl in Protégé or a code editor to add new classes or properties, following existing OWL clauses.

    Add new specimens or individuals for testing your extensions.

    Re-run the reasoner to ensure consistency and correct inference.

🧠 Learning resources & inspiration

    The Fish Ontology enables semantic annotation, data integration and retrieval for fish resources and includes unprecedented support for automated classification of unknown specimens
    PeerJ
    .

    Many life science ontologies follow FO’s approach, reusing concepts across domain vocabularies as recommended by FAIR principles.

📝 License & Citation

This project was developed as a course assignment. It’s shared under an open academic license — you may reuse it for educational purposes with attribution.

If you adapt or extend it, please cite the original Fish Ontology framework:

    Najib M. Ali, Haris A. Khan, Amy Y‑Hui Then …, Sarinder Kaur Dhillon, “Fish Ontology framework for taxonomy-based fish recognition”, PeerJ, 5:e3811 (2017)
