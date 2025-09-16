# Birthday-meesage-sent


This HTML file creates a web-based "Birthday Messenger" application. The app's interface, built with HTML and styled using CSS, allows a user to add a list of students with their names and birthdays. The core functionality is managed by JavaScript, which stores and retrieves student data from the browser's Local Storage, checks for birthdays, and displays messages.

HTML Structure and Styling
The application uses a responsive, card-based layout.

HTML: The structure is straightforward. It contains a main div with a class of card to hold all the content. Inside, there's a heading, a form for adding students, a button to check for birthdays, and a list container to display the students.

CSS: The styling is embedded directly in the <style> tag within the <head>. It uses a modern, clean design with a defined color palette through CSS variables (:root). This makes the colors easily changeable and ensures consistency across the app's elements. The layout uses Flexbox (display: flex) for alignment and centering.

JavaScript Functionality
The JavaScript code handles all the dynamic behavior of the app.

Data Management: The loadStudents() and saveStudents() functions are crucial. They use the browser's Local Storage API to persist the student data, which means the list of students is saved even if the user closes and reopens the browser tab. The data is stored as a JSON string and parsed back into a JavaScript object when loaded.

UI Rendering: The renderStudents() function is responsible for dynamically updating the list of students on the page. It reads the data from Local Storage, clears the existing list, and then generates new HTML elements for each student, including their name, birthday, and message status.

Event Listeners:

Add Student Form: An event listener on the addStudentForm waits for a submit event. When triggered, it prevents the default form submission, gets the student's name and birthday from the input fields, and adds the new student to the data array before saving and re-rendering the list.

Check Birthdays Button: An event listener on the checkBirthdaysBtn is triggered on a click event. It compares the current date with each student's stored birthdate. If a match is found and a message hasn't been sent, it logs a "Happy Birthday" message to the console and marks the student as "message sent" in the data.

Message Display: The showMessage() utility function handles temporary pop-up messages, which inform the user about successful actions (e.g., "Student added successfully!") or provide feedback (e.g., "No one has a birthday today.").

Initial Load: An event listener for DOMContentLoaded ensures that the renderStudents() function runs as soon as the page is ready, displaying any previously saved students immediately.
