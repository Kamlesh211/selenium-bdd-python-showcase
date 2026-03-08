# 🧪 Selenium BDD Python Framework

[![Tests](https://github.com/Kamlesh211/selenium-bdd-python-showcase/actions/workflows/test_pipeline.yml/badge.svg)](https://github.com/Kamlesh211/selenium-bdd-python-showcase/actions/workflows/test_pipeline.yml)
[![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Selenium](https://img.shields.io/badge/Selenium-4.18.1-43B02A?logo=selenium&logoColor=white)](https://selenium.dev)
[![Behave](https://img.shields.io/badge/BDD-Behave-orange?logo=cucumber&logoColor=white)](https://behave.readthedocs.io)
[![Allure](https://img.shields.io/badge/Report-Allure-yellowgreen)](https://allurereport.org)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![License](https://img.shields.io/badge/License-Educational-lightgrey)](.)

> **Built by [Kamalesh](https://github.com/Kamlesh211)** — A production-ready Python test automation framework covering Web UI, REST API, CI/CD pipeline, and dual reporting. Designed by a Java Selenium expert transitioning into Python automation.

---

## 🎯 What This Framework Does

| Capability | Detail |
|---|---|
| 🌐 Web UI Testing | Selenium 4 + Page Object Model on saucedemo.com |
| 🔌 API Testing | REST API testing with Requests library on JSONPlaceholder |
| 📖 BDD | Gherkin feature files with Behave (Python Cucumber) |
| 📊 Dual Reporting | Custom HTML Report + Interactive Allure Report |
| ⚙️ CI/CD | GitHub Actions — daily scheduled runs + manual trigger |
| 📧 Email Alerts | Automated email with HTML report attached after every run |
| 🏗️ Design Pattern | Page Object Model (POM) |
| 🔧 Config Driven | YAML + Properties file — zero hardcoding |

---

## 🏗️ Framework Architecture

```
selenium_bdd_framework/
│
├── 📄 environment.py               # Hooks — before/after scenario/step
├── 📄 runner.py                    # Entry point — tag control + report launch
├── 📄 bootstrap.properties         # Runtime config — browser, env, test_type
├── 📄 behave.ini                   # Behave + Allure formatter config
│
├── 📁 features/                    # Gherkin feature files (BDD scenarios)
│   ├── 📁 web/
│   │   └── login.feature           # 4 Web UI scenarios
│   └── 📁 api/
│       └── users.feature           # 6 API scenarios (GET/POST/PUT/DELETE)
│
├── 📁 steps/                       # Step definitions
│   ├── login_steps.py
│   └── api_steps.py
│
├── 📁 pages/                       # Page Object Model
│   ├── base_page.py                # Reusable Selenium methods
│   ├── login_page.py
│   └── dashboard_page.py
│
├── 📁 api/                         # API layer
│   ├── base_api.py                 # GET/POST/PUT/DELETE + assertions
│   └── user_api.py                 # User endpoint methods
│
├── 📁 utilities/                   # Helpers
│   ├── config_reader.py            # YAML config loader
│   ├── driver_factory.py           # WebDriver factory
│   ├── extent_reporter.py          # Custom HTML report generator
│   └── runner_helper.py            # Banner, reports, bootstrap loader
│
├── 📁 config/
│   └── config.yaml                 # Multi-environment config
│
└── 📁 .github/workflows/
    └── test_pipeline.yml           # CI/CD pipeline
```

---

## ✅ Test Coverage

### Web UI Tests — saucedemo.com
| Scenario | Tags | Status |
|---|---|---|
| Successful login with valid credentials | `@smoke` `@critical` | ✅ Pass |
| Login with invalid credentials | `@regression` | ✅ Pass |
| Login with empty username | `@regression` | ✅ Pass |
| Login with empty password | `@regression` | ✅ Pass |

### API Tests — JSONPlaceholder
| Scenario | Method | Tags | Status |
|---|---|---|---|
| Get list of users | GET | `@smoke` `@critical` | ✅ Pass |
| Get single user by ID | GET | `@smoke` `@critical` | ✅ Pass |
| Get non-existing user returns 404 | GET | `@regression` | ✅ Pass |
| Create a new user | POST | `@regression` | ✅ Pass |
| Update an existing user | PUT | `@regression` | ✅ Pass |
| Delete a user | DELETE | `@regression` | ✅ Pass |

**Total: 10 scenarios — 10 passed ✅**

---

## 📊 Reports

### Custom HTML Report
- Self-contained single `.html` file — shareable by email
- Feature + scenario grouping with pass/fail badges
- Step-level timing and status
- Auto-embedded failure screenshots
- Timestamped per run

### Allure Report
- Interactive dashboard with donut charts
- Suites, Categories, Timeline, Graphs views
- Severity and author metadata
- Screenshots on failure
- Trend history across runs

---

## ⚙️ CI/CD Pipeline

```yaml
Triggers:
  ✅ Daily scheduled run  — 8:00 AM IST (cron)
  ✅ Manual trigger       — with test_type + tag inputs

Steps:
  1. Checkout code
  2. Setup Python 3.13
  3. Install dependencies
  4. Setup Chrome (headless)
  5. Setup Java + Allure CLI
  6. Run Behave tests
  7. Generate Allure report
  8. Upload HTML + Allure as artifacts
  9. Send email with report attached
```

### Manual Trigger Inputs
| Input | Options | Default |
|---|---|---|
| `test_type` | `all` / `web` / `api` | `all` |
| `tags` | `@smoke`, `@regression`, etc. | all tests |

---

## 🔧 Tech Stack

| Tool | Version | Purpose | Java Equivalent |
|---|---|---|---|
| Python | 3.13 | Language | Java |
| Selenium | 4.18.1 | Browser automation | Selenium Java |
| Behave | 1.2.6 | BDD framework | Cucumber |
| WebDriver Manager | 4.0.1 | Auto driver download | WebDriverManager |
| Requests | 2.31.0 | API testing | RestAssured |
| PyYAML | 6.0.1 | Config management | SnakeYAML |
| Jinja2 | 3.1.3 | HTML report templating | Thymeleaf |
| allure-behave | 2.13.5 | Allure integration | allure-cucumber |
| Allure CLI | 2.27.0 | Report generation | allure-maven-plugin |
| GitHub Actions | — | CI/CD pipeline | Jenkins |

---

## 🚀 Key Features

- **Zero hardcoding** — everything driven by `bootstrap.properties` and `config.yaml`
- **Smart browser control** — API tests automatically skip browser launch via `@api` tag
- **test_type flag** — run `all`, `web`, or `api` with a single config change
- **Tag-based execution** — `@smoke`, `@regression`, `not @wip` and more
- **Auto screenshot** — captured and embedded in report on any step failure
- **Multi-environment** — switch between staging/dev/prod instantly
- **Dual reports** — Custom HTML (shareable) + Allure (interactive) both auto-open
- **Daily CI runs** — pipeline keeps the green badge alive automatically

---

## 📬 Contact

**Kamalesh** — QA Automation Engineer

[![GitHub](https://img.shields.io/badge/GitHub-Kamlesh211-181717?logo=github)](https://github.com/Kamlesh211)

---

> 💡 *This is a showcase repository. The full framework source code is maintained privately.*
