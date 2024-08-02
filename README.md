# Wiki Encyclopedia

This Wiki encyclopedia is a simple web application built using Django. It allows users to create, edit, search, and view encyclopedia entries written in Markdown. The following features are implemented:

## Features

1. **Entry Page**:
    - Visiting `/wiki/TITLE`, where `TITLE` is the title of an encyclopedia entry, renders a page displaying the contents of that encyclopedia entry.
    - The content of the encyclopedia entry is retrieved by calling the appropriate utility function.
    - If the requested entry does not exist, an error page is displayed indicating that the page was not found.
    - If the entry exists, the page displays the content of the entry, and the title of the page includes the name of the entry.

2. **Index Page**:
    - The `index.html` is updated to list all pages in the encyclopedia as clickable links.
    - Clicking on any entry name takes the user directly to that entry page.

3. **Search**:
    - Users can type a query into the search box in the sidebar to search for an encyclopedia entry.
    - If the query matches the name of an encyclopedia entry, the user is redirected to that entry’s page.
    - If the query does not match the name of an encyclopedia entry, the user is taken to a search results page displaying a list of all encyclopedia entries that have the query as a substring.
    - Clicking on any of the entry names on the search results page takes the user to that entry’s page.

4. **New Page**:
    - Clicking “Create New Page” in the sidebar takes the user to a page where they can create a new encyclopedia entry.
    - Users can enter a title for the page and, in a textarea, enter the Markdown content for the page.
    - Users can click a button to save their new page.
    - If an encyclopedia entry already exists with the provided title, an error message is displayed.
    - Otherwise, the encyclopedia entry is saved to disk, and the user is taken to the new entry’s page.

5. **Edit Page**:
    - On each entry page, the user can click a link to be taken to a page where they can edit that entry’s Markdown content in a textarea.
    - The textarea is pre-populated with the existing Markdown content of the page (i.e., the existing content is the initial value of the textarea).
    - The user can click a button to save the changes made to the entry.
    - Once the entry is saved, the user is redirected back to that entry’s page.

6. **Random Page**:
    - Clicking “Random Page” in the sidebar takes the user to a random encyclopedia entry.

## Installation and Setup

1. **Clone the repository**:
    ```bash
    git clone https://github.com/SinghaniaV/wikipedia-backend
    cd wikipedia-backend
    ```

2. **Create and activate a virtual environment**:
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

3. **Install the required packages**:
    ```bash
    pip install django python-markdown2
    ```

4. **Run the Django development server**:
    ```bash
    python manage.py runserver
    ```

5. **Access the application in your web browser**:
    Open `http://127.0.0.1:8000/` in your web browser.

## Project Structure

- **encyclopedia**: Contains the main application code.
  - **static/encyclopedia**: Static files (CSS, JS, images).
  - **templates/encyclopedia**: HTML templates.
  - **urls.py**: URL routing for the application.
  - **views.py**: View functions handling the HTTP requests and rendering templates.
  - **util.py**: Utility functions for reading and writing encyclopedia entries.

- **entries**: Directory where the Markdown files for each encyclopedia entry are stored.