# MathKit numeric example

Demonstrates a large binomial coefficient, overflow-resistant hypotenuse, accurate logarithm near zero, and explicit ties-to-even decimal rounding.

From the repository root, create an isolated consumer using the existing sealed
package (building directly in this checkout discovers unrelated app resources):

```sh
example_dir=$(mktemp -d)
mkdir "$example_dir/packages"
cp examples/mathkit/main.bui "$example_dir/main.bui"
cp packages/mathkit-0.1.0.buipkg "$example_dir/packages/"
(cd "$example_dir" && buoy main.bui --check --diagnostic-format json && buoy main.bui -o app && ./app)
```

For a standalone consumer, copy `main.bui` into a fresh directory and place
`mathkit-0.1.0.buipkg` from the repository's `packages/` in that directory's
`packages/`. Run `buoy main.bui -o app` and `./app` there. No native libraries
or services are required.

The first output is `7219428434016265740`; the remaining lines demonstrate floating-point formatting and rounding.

Maintainers run the private validation suite before release. See the repository README for public build instructions.
