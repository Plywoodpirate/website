# Style Guides

Please follow these style guides if you want to contribute code to this project.

## Commit messages

### Title (first line)

- The first line should be a title. Limit it to 50 characters or less
- Use the present tense ("Add feature" not "Added feature")
- In the first line, use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- consider starting your commit messaeg with an applicable emoji:
   - :exclamation: `:exclamation:` when your commit break compatibility with older versions
   - :fire: `:fire:` if you fix security issues
   - :art: `:art:` when improving UX, graphics or design elements
   - :arrow_up: `:arrow_up:` for updating requirements (in docker, composer, node etc)
   - :rocket: `:rocket:` when you improve performance
   - :mag: `:mag:` if you improve SEO or SEM
   - :eyeglasses: `:eyeglasses:` if you improve accessibility
   - :blue_book: `:blue_book:` if you improve documentation
   - :star: `:star:` if you add a new extension
   - :hammer: `:hammer:` if the commited code is communitcating with external or internal APIs
   - :iphone: `:iphone:` if you fix issues on mobile devices, responsive or compatibility
   - :heart: `:heart:` for other primarly frontend- or javascript-related commits (html, sass, js etc.)
   - :muscle: `:muscle:` for other primarly backend related commits (php, mysql, node.js etc.)

### Body (further lines)

- All other lines are optional. They form the body of the message. 
  Separate the body from the first line with a blank line and limit the 
  body to 72 character pr less per line.
- In the body of your commit message, describe your commit in more detail. 
  Remember: Describe *what* you've achieved, not *how* you achieved it.
- In the last line, reference issues and pull requests related to 
  your commit. Separate this last line from the other lines by adding 
  a blank line before.
   
## Documentation

Generally, use [Markdown](https://daringfireball.net/projects/markdown/).

When developing TYPO3 extensions, allways include a extension documentation as described in the TYPO3 Documentation
recommendations!

## PHP

All PHP must adhere to [PSR-12](https://www.php-fig.org/psr/psr-12/) and, depending on the project, 
the coding guidelines applicable for the CMS or framework which is used in the project.

### General rules

- Use strict typing
- Keep your code `E_STRICT` compatible, i.e. it should not produce warnings or errors if PHP's error reporting level 
   is set to ` E_ALL | E_STRICT`

### Formatting

- Avoid ternary operators except it is really obvious
- concernate variables and strings by using `"Hello ${foobar}!"` instead of `"Hello " + $foobar + "!"`

### Rules when using a CMS or framework
Here is a list of common coding guidelines for often used CMS or frameworks: 

- [TYPO3 PHP Coding Guidelines](https://docs.typo3.org/m/typo3/reference-coreapi/master/en-us/CodingGuidelines/CglPhp/Index.html)
- [Symphony Coding Standards](https://symfony.com/doc/current/contributing/code/standards.html)
- [Laravel Coding Guidelines](https://www.mindtwo.de/guidelines/coding/laravel)


## Javascript

- Avoid jQuery. Use plain Javascript instead
- All Javascript must be ES6 and adhere to [AirBnB Javascript Styleguide](https://airbnb.io/javascript/).
- Avoid [platform-dependent code](https://flight-manual.atom.io/hacking-atom/sections/cross-platform-compatibility/).
- If you use a framework, follow the Coding Guidelines of that framework (see below)

List of Coding guidelines for often used frameworks:

- [VueJs style-guide](https://vuejs.org/v2/style-guide/)
- [AngularJs coding style guide](https://angular.io/guide/styleguide)



## Frontend

- In TYPO3, use [Fluid Components](https://fluidcomponents.sitegeist.de/) to build a modular
  frontend.
- Use [Sass](https://sass-lang.com/) to define the styling
- Use [BEM](http://getbem.com/) whenever possible
- Never ever write CSS, use Sass instead!

Otherwise, use the rules of [AirBnB CSS Styleguide](https://github.com/airbnb/css), which are:

### AirBnB CSS/Sass Style Guide

The following rules are from the [AirBnB CSS Styleguide](https://github.com/airbnb/css). This list only 
includes the most improtant ones. Feel free to read more details on their website.

#### Formatting

- Use soft tabs (2 spaces) for indentation.
- Prefer dashes over camelCasing in class names.
- Underscores ~~and PascalCasing~~ are okay if you are using BEM (see OOCSS and BEM below).
- Do not use ID selectors.
- When using multiple selectors in a rule declaration, give each selector its own line.
- Put a space before the opening brace { in rule declarations.
- In properties, put a space after, but not before, the : character.
- Put closing braces } of rule declarations on a new line.
- Put blank lines between rule declarations.

#### Commenting

- Prefer line comments (// in Sass-land) to block comments.
- Prefer comments on their own line. Avoid end-of-line comments.
- Write detailed comments for code that isn't self-documenting

#### Sass
- Do not nest selectors more than three levels deep!
- Prefer **dash-cased variable names** (e.g. `$my-variable`) over camelCased or snake_cased variable names. 
   It is acceptable to prefix variable names that are intended to be used only within the same file with an 
   underscore (e.g. `$_my-variable`).
- **Mixins** should be used to DRY up your code, add clarity, or abstract complexity--in much the same way as 
    well-named functions. Mixins that accept no arguments can be useful for this, but note that if you are not 
    compressing your payload (e.g. gzip), this may contribute to unnecessary code duplication in the resulting styles.
- `@extend` should be avoided because it has unintuitive and potentially dangerous behavior, especially when used 
    with nested selectors. Even extending top-level placeholder selectors can cause problems if the order of selectors 
    ends up changing later (e.g. if they are in other files and the order the files are loaded shifts). Gzipping 
    should handle most of the savings you would have gained by using @extend, and you can DRY up your stylesheets 
    nicely with mixins.
