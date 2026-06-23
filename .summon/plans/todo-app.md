---
status: pending
title: To-Do App (Clean & Minimal)
---

1. **Set up global styles** — In `/app/src/styles/global.css`, ensure the file starts with `@import "tailwindcss";` and add a light background colour for the full page.

2. **Create a Task type** — In `/app/src/types/task.ts`, define a `Task` type with fields: `id` (string), `text` (string), and `createdAt` (number timestamp).

3. **Create a custom hook for task state** — In `/app/src/hooks/useTasks.ts`, implement a hook that:
   - Stores the list of tasks in local state.
   - Provides an `addTask(text: string)` function that creates a new task with a unique ID and timestamp.
   - Provides a `deleteTask(id: string)` function that removes a task by ID.
   - Returns the tasks array and both functions.

4. **Build the AddTaskInput component** — In `/app/src/components/AddTaskInput.tsx`, create a controlled text input with a submit button. It should:
   - Show a placeholder like "Add a new task…".
   - Call the `onAdd` prop with the input text when the button is clicked or Enter is pressed.
   - Clear the input after submission.
   - Disable submission if the input is empty or whitespace only.

5. **Build the TaskItem component** — In `/app/src/components/TaskItem.tsx`, render a single task row that shows:
   - The task text on the left.
   - A delete (trash/×) button on the right that calls an `onDelete` prop when clicked.
   - A subtle hover effect to highlight the row.

6. **Build the TaskList component** — In `/app/src/components/TaskList.tsx`, render the full list of tasks using `TaskItem`. If there are no tasks, show a friendly empty state message like "No tasks yet — add one above!".

7. **Build the main page** — In `/app/src/pages/TodoPage.tsx`, compose the full page layout:
   - A centred card container (max width ~600px) with padding and a light shadow.
   - A heading at the top (e.g. "My Tasks").
   - The `AddTaskInput` component wired to `addTask`.
   - The `TaskList` component wired to the tasks list and `deleteTask`.
   - A subtle task count shown below the list (e.g. "3 tasks").

8. **Wire up routing and entry point** — In `/app/src/App.tsx`, render `TodoPage` directly. Ensure `/app/src/main.tsx` imports global styles and mounts the app correctly.
