<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Book Library</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-bottom: 20px;
        }

        h1 {
            margin: 0;
        }

        section {
            margin-bottom: 30px;
        }

        #book-list {
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
        }

        #add-book-form {
            border: 1px solid #ccc;
            padding: 20px;
            border-radius: 5px;
            background: #f9f9f9;
        }

        label {
            display: block;
            margin-bottom: 10px;
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            margin-bottom: 10px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            float: right;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>My Book Library</h1>
    </header>
    <main>
        <section id="book-list">
            <!-- Books will be dynamically added here -->
        </section>
        <section id="add-book-form">
            <h2>Add a New Book</h2>
            <form id="book-form">
                <label for="title">Title:</label>
                <input type="text" id="title" name="title" required><br><br>
                
                <label for="author">Author:</label>
                <input type="text" id="author" name="author" required><br><br>
                
                <label for="year">Year:</label>
                <input type="number" id="year" name="year" required><br><br>
                
                <button type="submit">Add Book</button>
            </form>
        </section>
    </main>

    <script>
        const bookForm = document.getElementById('book-form');
        const bookList = document.getElementById('book-list');

        bookForm.addEventListener('submit', function(event) {
            event.preventDefault();

            const title = document.getElementById('title').value;
            const author = document.getElementById('author').value;
            const year = document.getElementById('year').value;

            // Create a new list item for the book
            const newBook = document.createElement('div');
            newBook.classList.add('book-item');
            newBook.innerHTML = `
                <strong>Title:</strong> ${title}<br>
                <strong>Author:</strong> ${author}<br>
                <strong>Year:</strong> ${year}<br>
            `;

            // Append the new book to the book list
            bookList.appendChild(newBook);

            // Clear the form inputs
            document.getElementById('title').value = '';
            document.getElementById('author').value = '';
            document.getElementById('year').value = '';
        });
    </script>
</body>
</html>
