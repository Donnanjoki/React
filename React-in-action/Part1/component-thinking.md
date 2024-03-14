\***\*\*\*\*\*\*\***\*\*\***\*\*\*\*\*\*\*** Exercise 1.1 Component thinking **\*\*\*\***\*\*\*\***\*\*\*\***

## TASK

Visit a popular site that you enjoy and use often (like GitHub, for example) and break down the interface into components. As you go, you’ll probably find yourself dividing things into separate parts.

// questions to consider

A]] When does it make sense to stop breaking things down?

> . Reusability - if a resulting element won;t be re-used across the interface then creating a separate component might be an overkill.
> . complexity- Over-componentization can make the code harder to understand and maintain. If breaking down further makes things more complex then its better to leave it as so.

B]] Should an individual letter be a component?

> .Typically individual letter are usually styled with css as part of a larger component such as a heading or paragraph hence not advisable.

C]] When might it make sense for a component to be something small?

> . Reusability - Smaller components are generally more reusable across different parts of the interface. For instance, a well-designed button component can be used for various actions throughout the website, promoting consistency and reducing development time.

> . Isolation - Keeping logic isolated within a small component makes the code easier to understand, test, and maintain.

> . Readability - Smaller components often improve code readability. By breaking it down, it makes the code easier to scan and understand, especially when working on specific functionalities.

> . Maintainability - Small components are easier to maintain and update. If a design change is needed for a button, you only have to modify the button component and not every instance of the button across the entire website.

> . Composability: Small components act like building blocks. They can be combined in various ways to create more complex UIs (user interfaces).

// Note: Over-componentization, where everything is broken down into tiny pieces, can also lead to complexity in managing the relationships between components. Consider the trade-off between reusability and maintainability when deciding how small to make a component.

D]] When would it make sense to consider a grouping of
things as one component?

> . Shared functionality:
> . They appear together frequently:
> . State Management
