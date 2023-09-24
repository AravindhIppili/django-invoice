# Django Invoice Project

This Django project provides a RESTful API for managing invoices and their associated details. It includes two models: `Invoice` and `InvoiceDetail`, with the ability to retrieve and create invoices, along with their details.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.x installed on your system.
- A virtual environment for managing project dependencies (optional but recommended).

## Installation

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/django-invoice-project.git
   cd invoice_project
   ```

2. Install pipenv:

   ```bash
   pip install pipenv
   ```

3. Create Pipenv and install packages:
   ```bash
   pipenv --python 3.10
   pipenv install
   ```
4. Perform database migrations:

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Create a superuser account for accessing the Django admin panel:

   ```bash
   python manage.py createsuperuser
   ```

6. Start the development server:

   ```bash
   python manage.py runserver
   ```

## API Reference

#### List Invoices:

```http
  GET /api/invoices/
```

#### Create Invoice:

```http
  POST /api/invoices/
```

| Parameter      | Type   | Description  |
| :------------- | :----- | :----------- |
| `Invoice data` | `json` | **Required** |

Example Payload:

```json
{
  "date": "2023-09-24",
  "invoice_no": "INV-2023-001",
  "customer_name": "John Doe",
  "details": [
    {
      "description": "Product A",
      "quantity": 5,
      "unit_price": "20.00",
      "price": "100.00"
    },
    {
      "description": "Product B",
      "quantity": 3,
      "unit_price": "15.00",
      "price": "45.00"
    }
  ]
}
```

#### Retrieve Invoice : Retrieve details of a specific invoice.

```http
  GET /api/invoices/<invoice_id>/
```

| Parameter    | Type  | Description                |
| :----------- | :---- | :------------------------- |
| `invoice_id` | `int` | **Required** ID of invoice |

#### List Invoice Details: Retrieve a list of all invoice details.

```http
    GET /api/invoice-details/
```

#### Create Invoice Detail: Create a new invoice detail.

```http
    POST /api/invoice-details/
```

- Example JSON payload:

```json
{
    "invoice": <invoice_id>,  // ID of the associated invoice
    "description": "Product C",
    "quantity": 2,
    "unit_price": "25.00",
    "price": "50.00"
}

```

#### Retrieve Invoice Detail: Retrieve details of a specific invoice detail.

```http
GET /api/invoice-details/<invoice_detail_id>/
```

## Authors

- Mail - [aravindhippili00@gmail](mailto:aravindhippili00@gmail)
