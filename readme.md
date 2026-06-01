SETU Module Catalogue

This is a system for the generation of a module catalogue for SETU Computing department.

## Source of Truth

The "source of truth" is in the `module_catalogue` directory:

- `module_catalogue/descriptors/` - Detailed module descriptors (YAML + PDF)
- `module_catalogue/modules/` - Module metadata and cluster assignments
- `module_catalogue/programmes/` - Programme definitions
- `module_catalogue/schedules/` - Semester schedules for each programme

## Generation

The catalogue is generated using the Python script `generate-catalogue.py`:

```bash
# Install dependencies
pip install -r requirements.txt

# Generate the catalogue structure
python3 generate-catalogue.py

# Build the Tutors course
cd tutors
deno run -A jsr:@tutors/tutors
```

See `QUICKSTART.md` for quick start guide or `GENERATOR_README.md` for full documentation.

## Output

The publication of the catalogue via the Tutors generation system is documented here:

- https://tutors-reference-manual.netlify.app/llms/tutors-reference-manual-complete-llms.txt

The generated output is in the `tutors` directory:

- `tutors/unit-1-programmes/` - Browse modules by programme and semester
- `tutors/unit-2-clusters/` - Browse modules by subject cluster

**Note:** The `tutors-reference/` directory contains the reference implementation for comparison.

## Statistics

- 12 Programmes
- 225 Modules
- 16 Subject Clusters

## Complete Workflow

```bash
# 1. Edit source data
vim module_catalogue/descriptors/yaml/A13443.yaml

# 2. Generate catalogue structure
python3 generate-catalogue.py

# 3. Build Tutors course
cd tutors
deno run -A jsr:@tutors/tutors

# 4. Preview/deploy the generated site
```

## Prerequisites

- Python 3.x with PyYAML
- Deno ([install from deno.land](https://deno.land/))


