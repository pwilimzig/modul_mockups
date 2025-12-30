# City App Schema - Standardized Description of Smart City Applications

This repository provides a standardized schema for describing city apps and their modules. It was developed by the Fraunhofer Institute for Experimental Software Engineering (IESE) as part of the Smart City Model Projects (Modellprojekte Smart Cities - MPSC) program and serves to promote transparency, interoperability, and collaboration between municipalities.

## 🎯 Objectives

City apps are mobile or web-based applications that provide citizens, tourists, and businesses with information about urban or regional life and connect them with municipal services. They are divided into various modules – from waste and event calendars to public transport information and citizen participation.

This schema repository enables:

- **Standardized Description**: Uniform documentation of city apps and their modules
- **Comparability**: Municipalities can systematically compare different app solutions
- **Interoperability**: Facilitating the exchange and reuse of modules
- **Transparency**: Clear documentation of features, interfaces, dependencies, and costs
- **Open Source Promotion**: Supporting development partnerships through structured documentation

## 📂 Repository Structure

```
├── README.md                           # German version
├── README_EN.md                        # This file (English version)
├── schemas/                            # JSON schema definitions
│   ├── city-app-schema.json           # Schema for city app descriptions (v2.1.0)
│   └── app-module.schema.json         # Schema for app modules (v1.0.0)
└── Smart-City-Platform/                # Example implementation
    ├── city_app.yml                   # Example of a city app description
    └── modules/                        # Example modules
        ├── citizen-participation.yml  # Citizen participation module
        ├── environmental-monitoring.yml # Environmental monitoring module
        └── images/                     # Screenshots and logos
```

## 📋 Schema Overview

### City App Schema (`city-app-schema.json`)

The main schema describes a complete city app with the following core elements:

**Basic Information:**
- Name, provider, app type
- Short description and website
- Contact information and development partnerships

**Technical Details:**
- Open source repository
- Documentation and licensing
- Development status and last update
- List of included modules (as references)

**Visual Elements:**
- Logo and screenshots
- Deployed municipalities

### App Module Schema (`app-module.schema.json`)

The module schema describes individual functional modules of a city app:

**Functional Description:**
- Name and topic area (e.g., citizen participation, environmental monitoring, public transport)
- Usage scenario and detailed description
- Optional/mandatory module status

**Technical Specification:**
- Interfaces (APIs, protocols)
- Dependencies (databases, frameworks)
- External services
- Customization options

**Organizational Details:**
- Involved actors and their roles
- Cost information
- Deployed municipalities
- Development status and roadmap

**Documentation:**
- Screenshots
- Technical documentation
- Open source repository

## 🚀 Usage

### Validating YAML Files

YAML files should be validated against the corresponding JSON schemas. You can use tools like [ajv-cli](https://github.com/ajv-validator/ajv-cli):

```bash
# Installation
npm install -g ajv-cli ajv-formats

# Validate a city app
ajv validate -s schemas/city-app-schema.json -d Smart-City-Platform/city_app.yml

# Validate a module
ajv validate -s schemas/app-module.schema.json -d Smart-City-Platform/modules/citizen-participation.yml
```

### Describing Your Own City App

1. Create a new YAML file based on `city-app-schema.json`
2. Fill in the required fields (at minimum `name`)
3. Describe your modules in separate YAML files based on `app-module.schema.json`
4. Reference the modules in your city app via the `modules` list
5. Validate your files against the schemas

### Example: Minimal City App

```yaml
name: "My Smart City App"
city-app-yml-version: "1.1"
provider: "City of Example"
short_description: "Central app for citizen services and municipal information"
app_type: "Progressive Web App"
modules:
  - "./modules/event-calendar.yml"
  - "./modules/waste-management.yml"
development_status: "Beta"
last_update: "2025-12-30"
```

## 🏛️ Background: City Apps Working Group

This schema was developed within the "City Apps" working group of the MPSC program. The working group:

- Compares different city app solutions from MPSC projects
- Identifies commonalities and differences
- Supports development partnerships such as:
  - [Open Smart City App (OSCA)](https://www.solingen.digital/projekte/entwicklungspartnerschaft-open-smart-city-app-gemeinsam-den-fortschritt-gestalten)
  - [KODI App](https://community.kodi-app.de/)
  - [Smart Village App (SVA)](https://smart-village.app/)
- Promotes community management and collaborative development
- Develops operating models and impact measurements

More information: [smart-city-dialog.de/netzwerk/arbeitsgruppen/city-apps](https://www.smart-city-dialog.de/netzwerk/arbeitsgruppen/city-apps) (German)

## 🤝 Contributing

This schema is a living document and is continuously being developed. Contributions are welcome:

- **Issues**: Report problems or suggest improvements
- **Pull Requests**: Contribute extensions or corrections
- **Feedback**: Share your experiences with the schema

## 📚 Further Resources

- [Smart City Dialog Platform](https://www.smart-city-dialog.de/) (German)
- [Short Study on Citizen Apps (2023)](https://www.wik.org/veroeffentlichungen/veroeffentlichung/kurzstudie-buerger-apps) (German)
- [Smart City Apps Compared: Guide for Municipalities](https://www.smart-city-dialog.de/aktuelles/news/smart-city-apps-im-vergleich-wegweiser-fuer-kommunen) (German)
- [City Apps: Smart Applications for Your Pocket](https://www.smart-city-dialog.de/aktuelles/news/city-apps-smarte-anwendungen-fuer-die-jackentasche) (German)

## 📄 License

This schema repository is provided under an open license to enable maximum reuse in smart city projects.

## 📧 Contact

**Technical Leadership:**
- Adeline Schaefer, Fraunhofer IESE
  Email: adeline.schaefer@iese.fraunhofer.de

**City Apps Working Group:**
- Tizia Grether, Fraunhofer IESE
  Email: tizia.grether@iese.fraunhofer.de

---

**Note:** The examples included in this repository were partially created with the help of AI and do not represent concrete, productively deployed applications. They serve solely to illustrate the schema.
