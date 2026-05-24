# Odoo Fork

This is a community fork of [odoo/odoo](https://github.com/odoo/odoo), an open-source suite of business applications.

## About

Odoo is a suite of web-based open-source business apps. The main Odoo Apps include an **Open Source CRM**, **Website Builder**, **eCommerce**, **Warehouse Management**, **Project Management**, **Billing & Accounting**, **Point of Sale**, **Human Resources**, **Marketing**, **Manufacturing**, and more.

This fork aims to provide community-driven improvements, bug fixes, and additional features on top of the upstream Odoo codebase.

## Getting Started

### Prerequisites

- Python 3.10+
- PostgreSQL 13+
- Node.js 16+ (for frontend assets)
- wkhtmltopdf (for PDF generation)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-org/odoo.git
   cd odoo
   ```

2. **Create a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Python dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure the database**

   Create a PostgreSQL database and user:

   ```sql
   CREATE USER odoo WITH PASSWORD 'odoo';
   CREATE DATABASE odoo OWNER odoo;
   ```

5. **Initialize the database**

   ```bash
   ./odoo-bin -d odoo --init base
   ```

6. **Start the server**

   ```bash
   ./odoo-bin -d odoo
   ```

   The server will be available at `http://localhost:8069`.

## Configuration

Copy the sample configuration file and adjust it to your needs:

```bash
cp debian/odoo.conf odoo.conf
```

Then start Odoo with:

```bash
./odoo-bin -c odoo.conf
```

> **Personal note:** I typically also pass `--dev=xml` during local development so that
> view changes are picked up without restarting the server:
> ```bash
> ./odoo-bin -c odoo.conf --dev=xml
> ```

## Contributing

We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) before submitting a pull request.

- Report bugs using the [Bug Report template](.github/ISSUE_TEMPLATE/1_bug_form.yml)
- Follow the [Pull Request template](.github/PULL_REQUEST_TEMPLATE.md) when submitting changes
- Ensure your code follows the existing style and passes all tests

## Running Tests

```bash
./odoo-bin -d test_db --test-enable --stop-after-init -i base
```

## License

This project is licensed under the GNU Lesser General Public License v3.0 — see the [LICENSE](LICENSE) file for details.

Some modules are licensed under the Odoo Enterprise Edition License. See [COPYRIGHT](COPYRIGHT) for details.

## Links

- [Upstream Odoo Repository](https://github.com/odoo/odoo)
- [Odoo Documentation](https://www.odoo.com/documentation)
- [Community Forum](https://www.odoo.com/forum)
