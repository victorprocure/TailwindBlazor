# Use TailwindCSS with Blazor

## Description
This package nuget package adds a build step to install TailwindCSS via NPM and run it. It includes a config file for Tailwind that scans any `razor` files for Tailwind utility classes.
By default it will output the generated `CSS` file in the `wwwroot/app.css` file of the main project being built.

All default variables can be over written in your `csproj` file.

### Variables and Defaults
- `<NodeCli>npm</NodeCli>`
- `<NodeXCli>npx</NodeXCli>`
- `<TailwindCssConfigFile>$(MSBuildThisFileDirectory)../content/tailwind.config.js</TailwindCssConfigFile>`
- `<TailwindCssCli>tailwindcss</TailwindCssCli>`, this command will follow the `<NodeXCli>` variable
- `<TailwindCssOutputFile>$(MSBuildProjectDirectory)/wwwroot/app.css</TailwindCssOutputFile>`
- `<TailwindCssInputFile>$(MSBuildThisFileDirectory)../content/input.css</TailwindCssInputFile>`
- `<TailwindCssMinify>false</TailwindCssMinify>`, Should TailwindCSS minify its out put. This is case sensitive only `true` or `false` valid
- `<TailwindCssWorkingDirectory>$(MSBuildProjectDirectory)/../</TailwindCssWorkingDirectory>`, The directory to run the tailwind command from, we default to the level above current project directory in order to glob any components that may be in other project folders within the solution directory

### Example
The repo can be cloned, the example project is just the default Blazor project with Bootstrap removed and all CSS replaced with Tailwind