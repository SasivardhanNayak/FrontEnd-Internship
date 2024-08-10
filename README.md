System Design Overview
Architecture
The TO DO List is built as a single-page application (SPA) using React.js. It is designed to be responsive and user-friendly, providing essential features for task creation, management, and organization.

Components
The application is modular, with each core functionality encapsulated in reusable React components:

App Component (App.js)

Serves as the main entry point of the application.
Manages the global state of the tasks using React's useState hook.
Integrates other components such as TaskForm and TaskList to create a cohesive user experience.

TaskForm Component (TaskForm.js)
Handles the creation of new tasks.
Consists of input fields for task name and description, and a submit button to add the task to the task list.
Validates input to ensure that each task has a name before it can be added.

TaskList Component (TaskList.js)
Displays the list of tasks, including options to edit, delete, or mark tasks as complete.
Implements an expandable list format where each task can be expanded to show additional details, such as the description and the timestamp of the last update.
Supports searching and filtering tasks based on the user's input.

TaskItem Component (TaskItem.js)
Represents individual tasks within the TaskList.
Provides functionality to toggle the task's completion status, edit task details, and view the expanded task details.
State Management
The application uses React's useState for managing the state of tasks. The state includes an array of task objects, each containing properties like taskName, description, isDone, and timestamp.

Responsiveness
The application is designed to be responsive, ensuring usability across various devices, including desktops, tablets, and smartphones. This is achieved through a combination of flexible layouts and CSS media queries.

Styling
The UI is styled using a custom CSS file (App.css), which provides a clean and modern look. The styling adapts to different screen sizes to maintain a consistent user experience across devices.

Data Flow
Task Creation: Users input a task name and description in the TaskForm. Upon submission, the task is added to the global state in App.js.
Task Management: Tasks can be edited, marked as complete, or deleted through actions in the TaskList and TaskItem components. The state updates accordingly, reflecting changes in the UI.
Task Search: Users can search for tasks using a search input field, filtering the displayed tasks based on the search term.

Implementation Explanation

Component Structure
The Task Management System is implemented using React.js, following a component-based architecture. This modular approach ensures that each functionality is isolated, making the system easy to manage, test, and extend.

App Component
The App.js file is the heart of the application, responsible for managing the state of tasks and coordinating the interactions between components.

State Management:

The App component uses the useState hook to maintain the state of all tasks in an array.
Each task is represented as an object with properties like taskName, description, isDone, and timestamp.
Core Functions:

addTask(newTask): Adds a new task to the state. This function is passed down as a prop to the TaskForm component.
toggleTaskDone(taskToUpdate): Toggles the completion status of a task. This function is passed to the TaskList component.
editTask(updatedTask): Updates an existing task's details, including its name and description. This function is also passed to the TaskList component.
TaskForm Component
The TaskForm.js file contains the form used to create new tasks.

Form Elements:

Includes input fields for the task name and description.
The form uses local state to manage the input values temporarily before passing them to the App component's addTask function upon submission.
Validation:

The form ensures that the task name is not empty before allowing the task to be added.
On successful submission, the form resets the input fields to their initial state.
TaskList Component
The TaskList.js file is responsible for displaying the list of tasks and managing task-related actions such as editing, marking as done, and deleting tasks.

Task Rendering:
The TaskList component maps over the array of tasks in the state and renders a TaskItem for each task.
Search Functionality:
A search input field is provided to filter tasks based on the search term entered by the user. The search is case-insensitive and checks for matches in the task names.
TaskItem Component
The TaskItem.js file represents each task in the task list.

Expandable List:
Each TaskItem can be expanded to reveal additional details, such as the task description and the timestamp of the last update.
Action Buttons:
Mark as Done: Toggles the task's isDone status when the button is clicked.
Edit: Opens up the task's details for editing. Once edited, the task is updated in the App component's state.
Delete: Removes the task from the list.

Data Flow
Task Creation and Management:

When a user creates a task, the data flows from the TaskForm component to the App component, where it's added to the task list state.
The task list is then passed down to the TaskList component, where individual tasks are rendered using the TaskItem component.
Task Interaction:

The TaskList component allows users to interact with each task (e.g., marking as done, editing), and these interactions update the global state in the App component.
Search and Filtering:

The search input filters tasks in real-time based on the user's input, making it easy to find specific tasks.

In the project directory, you can run:

npm start
Runs the app in the development mode.
Open http://localhost:3000 to view it in your browser.

The page will reload when you make changes.
You may also see any lint errors in the console.

npm test
Launches the test runner in the interactive watch mode.
See the section about running tests for more information.

npm run build
Builds the app for production to the build folder.
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.
Your app is ready to be deployed!

See the section about deployment for more information.

npm run eject
Note: this is a one-way operation. Once you eject, you can't go back!

If you aren't satisfied with the build tool and configuration choices, you can eject at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except eject will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use eject. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

Learn More
You can learn more in the Create React App documentation.

To learn React, check out the React documentation.

Code Splitting
This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

Analyzing the Bundle Size
This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

Making a Progressive Web App
This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

Advanced Configuration
This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

Deployment
This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

npm run build fails to minify
This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
