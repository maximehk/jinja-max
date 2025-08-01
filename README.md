# j2

A simple command-line tool to render Jinja2 templates.

This script allows for rendering Jinja2 templates from a file or standard input.
It can expose environment variables to the template under the 'env' namespace
when the --env flag is specified.

Usage:
  1. Create a template file, e.g., 'template.j2':
     Hello, my name is {{ env.USER }}.
     I am running this on machine {{ env.HOSTNAME }}.

  2. Run the script with the template:
     export HOSTNAME=$(hostname)
     uvx --from jinja2-max j2 --env -i template.j2

  3. Or using a pipe:
     echo "The current path is {{ env.PATH }}" | uvx --from jinja2-max j2 --env

Alternatively you can just install `j2` with `uv tool install jinja2-max` and run it like so: `j2 --env -i template.j2`


Note: Environment variable names in the template are case-sensitive.
      Use the exact case as shown in your environment (e.g., 'USER', 'HOME').
