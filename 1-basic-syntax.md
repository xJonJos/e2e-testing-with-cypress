## Setting Up a Test Suite

```javascript
describe('My Test Suite', () => {
  it('should load the homepage', () => {
    cy.visit('https://example.com'); // Visit a URL
  });
});
```

## Common Cypress Commands

- Navigating to a URL:

```javascript
cy.visit('https://example.com');
```

- Finding Elements:

```javascript
cy.get('selector'); // Get elements by selector
cy.get('.my-class'); // Get elements by CSS class
cy.get('#my-id'); // Get elements by ID
```

- Clicking Elements:

```javascript
cy.get('button').click(); // Click a button
```

- Typing in Input Fields:

```javascript
cy.get('input[name="username"]').type('myUsername'); // Type in an input field
```

- Assertions:

```javascript
cy.get('h1').should('contain', 'Welcome'); // Check text in an element
cy.url().should('include', '/dashboard'); // Check URL contains a path
cy.get('input').should('have.value', 'myUsername'); // Check input value
```

- Working with Assertions: Assertions are used to verify that an element or page state matches expectations

```javascript
cy.get('.success-message').should('be.visible'); // Element is visible
cy.get('input').should('have.value', 'expected value'); // Input has expected value
cy.url().should('eq', 'https://example.com/dashboard'); // URL matches exactly
```

- Chaining Commands: Cypress commands are often chained to interact with elements and check results

```javascript
cy.get('form').within(() => {
  cy.get('input[name="username"]').type('myUsername');
  cy.get('input[name="password"]').type('myPassword');
  cy.get('button[type="submit"]').click();
});
```

- Custom Commands: You can create custom commands for reusable actions

```javascript
Cypress.Commands.add('login', (username, password) => {
  cy.get('input[name="username"]').type(username);
  cy.get('input[name="password"]').type(password);
  cy.get('button[type="submit"]').click();
});

// Usage in a test
cy.login('myUsername', 'myPassword');
```
