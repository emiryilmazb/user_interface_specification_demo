# user_interface_specification_demo
User Management Screen Specification
![resim](https://github.com/user-attachments/assets/89e129a2-1d0a-46bf-a61d-4b068231c3d1)

1. Overview

The User Management Screen allows administrators to manage user accounts by performing operations such as creating, viewing, editing, and enabling/disabling users. The interface includes a table listing existing users and a form to add or modify user information. The behavior of this screen is as follows:

    A table on the left displays the list of existing users.
    A form on the right allows the creation or editing of a user.
    The ability to hide disabled users is provided.

2. UI Components and Behavior
2.1. Table (User List)

    Columns:
        ID: The unique identifier for each user.
        User Name: Displays the username of each user. This column can be filtered by clicking the filter icon.
        Email: Displays the email address associated with each user. Filtering functionality is available.
        Enabled: Indicates whether the user is currently enabled (true) or disabled (false). Filtering functionality is available.

    Sorting & Filtering:
        Each column in the table (ID, User Name, Email, Enabled) should allow sorting (ascending/descending) by clicking on the arrow.
        Filter icons should allow filtering the table by values in each column.

    Hide Disabled Users:
        A checkbox (Hide Disabled Users) above the table allows the user to hide or display disabled users. By default, this checkbox is checked, and only enabled users are shown.

    New User Button:
        A button labeled + New User is located above the table. When clicked, it clears the form on the right, enabling the creation of a new user.

2.2. Form (New User/Edit User)

The form on the right is used to create a new user or edit an existing user’s details.

    Username:
        Input field for the username. This field is required.

    Display Name:
        Input field for the user's display name. This field is optional.

    Phone:
        Input field for the user's phone number. This field is optional.

    Email:
        Input field for the user's email. This field is required and should be validated as a proper email address format.

    User Roles:
        Dropdown selection allowing the administrator to assign roles to the user. Available roles in the dropdown include:
            Guest
            Admin
            SuperAdmin
        This field is required.

    Enabled:
        A checkbox indicating whether the user is active (enabled) or inactive (disabled). By default, this should be unchecked for new users.

    Save User Button:
        A button labeled Save User is located at the top right of the form. This saves the details entered in the form, whether it is a new user or modifications to an existing user.

2.3. Default State

When the page is first loaded:

    The table on the left displays a list of all enabled users.
    The Hide Disabled Users checkbox is checked by default.
    The form on the right is empty and ready for the creation of a new user.

2.4. Edit User Workflow

When clicking on a user in the table:

    The form on the right is populated with the selected user’s details.
    The administrator can modify any of the fields and click Save User to update the information.

2.5. Create New User Workflow

    When the + New User button is clicked:
        The form on the right is cleared.
        The administrator can input the details for a new user, and click Save User to add the new user to the system.

3. Form Validation Rules

    Username: Must not be empty.
    Email: Must be in a valid email format.
    User Roles: Must have at least one role selected.

4. Error Handling

    If the required fields are not completed or there is a validation error, the system should display a message next to the field in error or a general error message at the top of the form indicating the issue.

5. Example User Flow

    Create a New User:
        Click on the + New User button.
        Fill in the Username, Email, and select a User Role.
        Optionally, fill in Display Name and Phone.
        Check the Enabled box if the user should be active immediately.
        Click Save User.
    Edit an Existing User:
        Click on a user row in the table.
        The form will populate with the selected user’s details.
        Make any desired changes.
        Click Save User to apply changes.
    Hide Disabled Users:
        By default, the Hide Disabled Users checkbox is checked, so only enabled users are shown.
        Unchecking the box will show both enabled and disabled users.

6. Development Considerations

    Ensure that the form state is properly reset when clicking on New User.
    Apply input validation as outlined in Section 3.
    Sorting and filtering should work on all columns of the table.
    Maintain responsiveness to ensure the UI works well on different screen sizes.
