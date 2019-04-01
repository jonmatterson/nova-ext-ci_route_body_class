# Nova Extension: CodeIgniter Route Body Class

This extension makes it possible to write styles targeting a specific Nova page. This is important as Nova pages sometimes use generic styles yet a theme may desire to style a certain page.

To accomplish this, the extension appends a class to the `<body>` of all Nova pages of the form `ci-route--personnel--index`, where `personnel` is the controller name specified by the route and `index` is the controller method specified by the route.

As an example, consider the `sim/departments` page. If a theme wanted to hide the manifest a department is assigned to (such as if there is only one manifest), when this extension is running, one could simply add the following CSS to the theme:

```
.ci-route--sim--departments #body ul li .fontTiny.gray {
    display: none;
}
```

Without this plugin, one would not want to `display:none` on `#body ul li .fontTiny.gray` because that would inadvertently affect tiny gray text on other pages. 

## Requirements

This extension requires:

- Nova 2.6+

## Installation

Copy the entire directory into `applications/extensions/ci_route_body_class`.

Add the following to `application/config/extensions.php`:

```
$config['extensions']['enabled'][] = 'ci_route_body_class';
```
