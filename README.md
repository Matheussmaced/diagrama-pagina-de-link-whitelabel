# diagrama-pagina-de-link-whitelabel

```mermaid
classDiagram
    class User {
        +UUID id
        +String name
        +String email
        +String password
        +createPage()
        +updatePage()
        +deletePage()
    }

    class Page {
        +UUID id
        +String title
        +String description
        +UUID userId
        +UUID customizationId
        +addLink()
        +removeLink()
        +updateStyle()
    }

    class Link {
        +UUID id
        +String url
        +String text
        +UUID pageId
        +editLink()
        +deleteLink()
    }

    class Customization {
        +UUID id
        +String backgroundColor
        +Int titleFontSize
        +String titleFontColor
        +Int descriptionFontSize
        +String descriptionFontColor
        +String borderStyle
        +applyChanges()
    }

    User "1" --> "*" Page
    Page "1" --> "*" Link
    Page "1" --> "1" Customization

