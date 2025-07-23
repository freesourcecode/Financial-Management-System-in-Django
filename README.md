# Online Financial Management System Project in Django with Source Code

The **Online Financial Management System Project in Django** is developed using Python, Django, and a MySQL database.

This system helps you manage your company’s affairs, including salaries, taxes, receipts, and more.

The purpose of this system is to avoid any duplicity or manipulation of records and thus stop corruption.

An **Online Financial Management System in Django** is an easy project for beginners to learn how to build a web-based python Django project.

>[!NOTE]
> To start creating a Online Financial Management System Project in Python Django, makes sure that you have PyCharm Professional IDE Installed in your computer.

## Online Financial Management System Project in Django: Admin Features

* **Login Page** 

The page where the system administrator enters their system credentials in order to gain access to the system’s administrative side.

* **New Company Page**

This is the page where an administrator can add a new company.

* **Company List**

The page with a list of companies that can be navigated to change or delete a company.

* **New Items**

The page to which an administrator can add new items.

* **Items List**

The page on which the list of items can be viewed, modified, or deleted.

* **New receipt**

The page to which an administrator can add new receipt.

* **Receipt List**

The page on which the list of receipt can be viewed.

* **New Salary**

The page to which an administrator can add new salary for their employee.

* **Salary List**

The page on which the list of salary can be viewed.

* **New User Page**

The page where a new admin credentials are created by an admin.

* **Users list**

This is the page that lists and manages the added users.

## How to Create an Online Financial Management System Project in Django?

Here are the steps on how to create an **Online Financial Management System Project in Django** with Source Code.

1. **Open file**.

First, open “pycharm professional” after that click “file” and click “new project”.

<img width="484" height="453" alt="image" src="https://github.com/user-attachments/assets/5d4ddf99-9566-47c0-a216-90869aad95fa" />

2. **Choose Django**.

Next, after click “new project“, choose “Django” and click.

<img width="152" height="325" alt="image" src="https://github.com/user-attachments/assets/a8dee8e1-2c78-42b9-8154-ec03a9b3e5d8" />

3. **Select file location**.

Then, select a file location wherever you want.

4. **Create application name**.

After that, name your application.

5. **Click create**.

Lastly, finish creating project by clicking “create” button.

<img width="802" height="489" alt="image" src="https://github.com/user-attachments/assets/80a5b4a6-4438-4f18-8356-1123e44846f9" />


6. **Start Coding**.

Finally, we will now start adding functionality to our Django Framework by adding some functional codes.

## Functionality and Codes of the Online Financial Management System Project in Django with Source Code

* **Create template for the salary form in Online Financial Management System Project in Django**.

In this section, we will learn on how create a templates for the salary form. 

To start with, add the following code in your create.html under the folder of /templates/.

```

{% extends 'apps_base.html' %}

{% block title %}Create receipt{% endblock %}

{% block apps_base_title %}Create a new salary record{% endblock %}

{% block apps_base_content %}
    {% if company_payees %}
        <form action="{% url 'create_salary' %}" method="post" class="form-block">
            {% csrf_token %}
            <input name="company_uuid" type="hidden" value="{{ company_uuid }}" readonly required/>
            <div class="form-group">
                <label for="create-salary-payee">Select a staff in {{ company_name }}</label>
                <select id="create-salary-payee" class="custom-select form-control" name="payee_id" required>
                    <option value="">None</option>
                    {% for payee in company_payees %}
                        <option value="{{ payee.id }}">{{ payee.full_name }}</option>
                    {% endfor %}
                </select>
            </div>
            <div class="form-group">
                <label for="create-salary-base-salary">Base Salary</label>
                <input id="create-salary-base-salary" name="base_salary" class="form-control" type="number" min="0"
                       step="0.01"
                       required/>
            </div>
            <div class="form-group">
                <label for="create-salary-bonus">Bonus</label>
                <input id="create-salary-bonus" name="bonus" class="form-control" type="number" min="0" step="0.01"
                       required/>
            </div>
            <div class="form-group">
                <label for="create-salary-total-salary">Total</label>
                <input id="create-salary-total-salary" name="total" class="form-control" type="number" readonly
                       required/>
            </div>
            <div class="form-group">
                <label for="create-salary-date">Date</label>
                <input id="create-salary-date" name="date" class="form-control auto-set-to-today" type="date" required/>
            </div>
            <button class="btn btn-lg btn-primary btn-block" type="submit">Create</button>
        </form>
    {% else %}
        <div class="alert alert-warning" role="alert">
            <strong>No staff to be paid!</strong>
            <p>All staff in your company are paid.</p>
        </div>
    {% endif %}
{% endblock %}

{% block apps_base_scripts %}
    <script>
        {# Auto calculate total cost #}
        var a, b;
        $(document).ready(function () {
            $("#create-salary-base-salary").change(function () {
                a = Number(this.value);
                document.getElementById("create-salary-total-salary").value = a + b;
            });

            $("#create-salary-bonus").change(function () {
                b = Number(this.value);
                document.getElementById("create-salary-total-salary").value = a + b;
            });
        });
    </script>
{% endblock %}
```
### 📌 Here's the full documentation for the [Online Financial Management System Project in Django with Source Code](https://itsourcecode.com/free-projects/python-projects/online-financial-management-system-project-in-django-with-source-code/)


