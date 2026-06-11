# Dynamic Drag-and-Drop Form Builder

A modern, highly polished, and fully interactive **Frontend UI Dynamic Drag-and-Drop Form Builder** built for the Frontend UI Developer Assignment. This application allows users to build, customize, reorder, preview, configure, and export structured web forms entirely client-side, with full integration into a Laravel-based blade layout and seamless UI components.

---

## 🚀 1. Project Overview

The **Dynamic Drag-and-Drop Form Builder** is an intuitive web interface where users can design forms dynamically by dragging elements or clicking to add fields. Built with clean, responsive, and performance-oriented design, it features drag-and-drop support, real-time validations, live preview transitions, a robust template export engine, and secure LocalStorage persistence.

---

## ✨ 2. Features Implemented

*   **Interactive Drag-and-Drop Workspace**: Powered by **SortableJS**, enabling smooth and intuitive drag-to-reorder and click-to-add gestures.
*   **Live Interactive Preview Mode**: Real-time render engine that translates the current schema state into fully interactive HTML inputs, select boxes, checkboxes, text areas, and headings.
*   **Rich Control Panel & Customizers**: Side panel to instantly edit field labels, default values, placeholders, option configurations (for select dropdowns), character counts, and state constraints.
*   **Dual State Synchronizer**: Instant rendering of configurations dynamically while allowing deep modification of submission endpoints and redirection behaviors.
*   **Security & Dialog Verification**: No generic `alert()` or blocking UI prompts. Fully customized, high-contrast **Bootstrap Modals** prompt users for sensitive actions (e.g., clearing the canvas, removing fields, or confirming submissions).
*   **Full State Persistence**: Automatic, silent saves to `LocalStorage` allowing form states and custom settings to survive reload events.
*   **Dynamic Validations & Counter Metrics**: Dynamic tracking of title character limits and immediate configuration updates.

---

## 🗃️ 3. Supported Field Types

The builder handles a wide range of input elements, each fully configurable with custom options, requirements, and placeholder constraints:

1.  **Header (Static Title)**: For sectioning and page partitioning with distinct sub-headings.
2.  **Text Input (Single Line)**: Standard text input for names, emails, short answers. Includes custom placeholder settings.
3.  **Text Area (Multi-line)**: Expandable multi-row text block for descriptions, bios, and feedback.
4.  **Number Input**: Supports value inputs with native numeric constraint limits.
5.  **Select Dropdown**: Dynamic dropdown selector with customizable, addable/removable text, and value options.
6.  **Checkbox (Binary Switch)**: For terms of service, opt-ins, or simple yes/no boolean responses.

---

## 👁️ 4. Preview Mode

Preview mode provides a realistic sandbox of the compiled final form:
*   Allows the creator to test input bounds, select combinations, and click submissions.
*   Pre-validates submissions client-side.
*   Presents a structured, high-contrast submission success modal showcasing exactly where the data is being sent (Backend Destination URL) and where the user will land upon success (Redirect Success Target URI).

---

## ↕️ 5. SortableJS Reordering

*   Utilizes the powerful, lightweight **SortableJS** touch-enabled drag-and-drop library.
*   Offers visual hover feedbacks, handle grabbability, and immediate layout animations when dragging fields across the canvas.
*   Ensures that schema indices are immediately updated and synchronized across preview states and local storage.

---

## 💾 6. LocalStorage Persistence

*   Dual synchronization of:
    *   `formBuilder_title`: Header configurations.
    *   `formBuilder_fields`: Field list sequence and parameters.
    *   `formBuilder_settings`: Submissions endpoints and metadata.
*   Works seamlessly behind the scenes; the user can refresh the tab or close the browser and resume building right where they left off.

---

## 📥 7. JSON Export

*   An absolute, raw view of the generated JSON Schema.
*   Allows developers or evaluators to view, copy, or export the structured representation of the built form instantly.
*   Reflects structural changes, field type shifts, options additions, and metadata in real-time.

---

## ⚙️ 8. Settings Module

A dedicated, isolated section for managing form destinations:
*   **Backend Destination URL**: Configures where form payloads will be processed.
*   **Submit Label**: Customizes the main action button text (e.g., "Submit Application", "Sign Up").
*   **Success Redirect URI**: Determines where user flow is routed following a successful form submission.
*   **Live Preview Pill**: Shows these settings formatted cleanly in a stylized monospace developer block.

---

## 🛠️ 9. Technologies Used

*   **Backend Framework**: Laravel v8+ / PHP (Blade templating)
*   **CSS Framework**: Bootstrap v4 / v5 (Responsive grid, components, and modal workflows)
*   **Drag-and-Drop Mechanics**: SortableJS
*   **Interactivity & DOM**: Vanilla ESM JavaScript + jQuery 3.2+
*   **Iconography**: LineAwesome / FontAwesome Core Pack
*   **Storage API**: Browser Web Storage (LocalStorage)

---

## ⚙️ 10. Installation Steps

To deploy and test the application locally, run the following steps:

1.  **Clone the Repository**:
    ```bash
    git clone <repository-url>
    cd <project-folder>
    ```

2.  **Install Composer Dependencies**:
    ```bash
    composer install
    ```

3.  **Environment Setup**:
    Copy the sample environment file and generate the application key:
    ```bash
    cp .env.example .env
    php artisan key:generate
    ```

4.  **Install Node Dependencies (Optional for build pipelines)**:
    ```bash
    npm install
    ```

5.  **Serve the Application**:
    Launch Laravel's built-in PHP development server:
    ```bash
    php artisan serve
    ```
    Alternatively, configure your virtual hosts (Apache/Nginx/Caddy) to point to the `/public` root.

---

## 📁 11. Folder Structure

Below is the structured layout containing developer edits and implementation points:

```text
├── app/
│   └── Http/
│       └── Controllers/
│           └── GuestController.php   # Directs route views and form builder assets
├── bootstrap/
├── config/
├── public/
│   ├── css/
│   │   └── admin-custom.css          # Customized visual accents and layouts
│   └── js/
│       └── admin-custom.js           # Supplementary scripts for template behavior
├── resources/
│   ├── views/
│   │   ├── layouts/
│   │   │   └── admin.blade.php       # Global HTML container layout
│   │   ├── includes/
│   │   │   ├── css.blade.php         # Global stylesheet imports
│   │   │   ├── js.blade.php          # Global interactive scripts
│   │   │   └── navigation.blade.php  # Sidebar / Navigation elements
│   │   └── form.blade.php            # Primary Form Builder application template
└── routes/
    └── web.php                       # Web routes definition
```

---

## 🔮 12. Future Enhancements

Potential architectural additions to elevate the form builder's capabilities:
*   **Conditional Visibility Logic**: Define dynamic user conditions to show/hide fields client-side based on previous answers (e.g. "If Select Choice == 'Yes', show Text Area").
*   **Database Schema Generation**: Auto-generate MySQL/PostgreSQL migration scripts from the exported JSON Schema directly in the dashboard.
*   **Rich Multilingual Localization**: Built-in support for multiple languages with quick translation strings in the JSON package.
*   **Custom ReDoS & Rate Limiting Integration**: Add deep rate limiter configurations and field-level RegEx match controls directly through the settings layout.
# form-builder-dashboard
