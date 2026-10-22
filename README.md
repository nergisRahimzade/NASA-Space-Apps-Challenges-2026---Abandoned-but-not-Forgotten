# Abandoned but not Forgotten

An interactive story about NASA objects left on the Moon and Mars, using 3D models, mission facts, and scroll-driven scenes.

The planned stack is Next.js, TypeScript, React Three Fiber, Drei, Three.js, Framer Motion, and Scrollama. Ajv will validate mission data, and glTF Transform will optimize models. AI is optional in the sprint plan and is not required for this setup.

## Current status

This repository currently has setup documentation only. The maintainer must complete the one-time bootstrap below and commit the generated application before teammates can use `npm ci` or start the site. Bootstrapping creates the Next.js starter; it does not implement the 3D story, mission schema, model pipeline, tests, CI, or deployments.

## Prerequisites for everyone

Install [Git](https://git-scm.com/downloads) and [Node.js 24 LTS](https://nodejs.org/en/download). Node.js includes npm. Use Node 24 consistently across the team; the bootstrap records that choice in `.nvmrc` and `package.json`.

Reopen your terminal after installation and verify:

```text
git --version
node --version
npm --version
```

Node should report `v24.x.x`. No Python environment, NASA login, or API key is needed for the starter website.

## One-time bootstrap for the maintainer

Run this section once, before asking teammates to install the project. These commands are for Windows PowerShell. Skip this section if the repository already contains the working application and `package-lock.json`.

### 1. Generate the Next.js application

Open PowerShell in the repository folder:

```powershell
cd D:\NR\Codebases\abandoned-but-not-forgotten
```

The initializer can reject an existing README, so temporarily store this guide outside the repository and restore it afterward:

```powershell
if (Test-Path package.json) {
    throw "This project is already initialized. Use the teammate setup instructions."
}

$setupReadmeBackup = Join-Path ([System.IO.Path]::GetTempPath()) ("anf-readme-" + [guid]::NewGuid().ToString() + ".md")
Move-Item -LiteralPath README.md -Destination $setupReadmeBackup

try {
    npx --yes create-next-app@latest . --typescript --eslint --tailwind --app --src-dir --import-alias "@/*" --use-npm --yes
    if ($LASTEXITCODE -ne 0) {
        throw "Next.js initialization failed. Resolve the reported error before continuing."
    }
}
finally {
    Copy-Item -LiteralPath $setupReadmeBackup -Destination README.md
}
```

This selects TypeScript, App Router, Tailwind CSS, ESLint, and a `src/` directory. See the [create-next-app documentation](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

### 2. Install the project packages

```powershell
npm install three @react-three/fiber @react-three/drei framer-motion scrollama ajv
npm install --save-dev @types/three @gltf-transform/cli

npm pkg set "scripts.lint=eslint ." "scripts.typecheck=tsc --noEmit" "engines.node=24.x"
"24" | Set-Content -Encoding ascii .nvmrc
npm install --package-lock-only
```

Scrollama includes its own TypeScript declarations; no separate types package is needed.

Ajv and glTF Transform are installed tools; their project-specific validation and compression scripts still need to be written. See the [glTF Transform CLI documentation](https://gltf-transform.dev/cli).

### 3. Create the shared folders

```powershell
$folders = @(
    "data",
    "public/models",
    "public/images",
    "src/components/scene",
    "src/components/story",
    "src/components/ui",
    "src/lib",
    "src/types",
    "scripts",
    "tests",
    "docs"
)

foreach ($folder in $folders) {
    New-Item -ItemType Directory -Path $folder -Force | Out-Null
    $placeholder = Join-Path $folder ".gitkeep"
    if (-not (Test-Path -LiteralPath $placeholder)) {
        New-Item -ItemType File -Path $placeholder | Out-Null
    }
}

New-Item -ItemType Directory -Path "assets/models-source" -Force | Out-Null

@'

# Uncompressed source models stay local
/assets/models-source/

# Allow a shared environment-variable template
!.env.example
'@ | Add-Content .gitignore
```

The `.gitkeep` files let Git preserve the shared folder structure after you commit them. Original model downloads go in the ignored `assets/models-source/` directory. Optimized models intended for the website go in `public/models/`.

### 4. Check and share the starter

```text
npm run lint
npm run typecheck
npm run build
npm run dev
```

Open the URL printed in the terminal, usually `http://localhost:3000`. You should see the generated Next.js starter page. Stop the server with **Ctrl+C**.

After these commands succeed, update this README's Current status section and commit the generated source files, configuration, `.gitkeep` files, `.nvmrc`, `package.json`, and `package-lock.json`. Push the setup so teammates can clone it. Keep `node_modules/`, `.next/`, secrets, and uncompressed source models out of Git.

## Teammate setup after the starter is committed

### 1. Clone the repository

On GitHub, select **Code** and copy the HTTPS clone URL. Replace `REPOSITORY_URL` below:

```text
git clone REPOSITORY_URL abandoned-but-not-forgotten
cd abandoned-but-not-forgotten
```

If you already cloned it, open a terminal in the project folder and run `git pull` instead. Run subsequent commands from the folder containing `package.json`.

### 2. Install the recorded dependencies

```text
npm ci
```

This installs the dependency versions recorded in `package-lock.json`, including development tools. It requires the committed lockfile and fails if it disagrees with `package.json`. It also replaces an existing `node_modules/` installation. See the [npm ci documentation](https://docs.npmjs.com/cli/v11/commands/npm-ci/).

You do not need to rerun `create-next-app` or install the listed packages individually. The tracked folders arrive with the clone. If you work on model processing, create the ignored source-model folder using this command, which works in PowerShell, macOS, and Linux:

```text
node -e "require('node:fs').mkdirSync('assets/models-source', { recursive: true })"
```

### 3. Start development

```text
npm run dev
```

Open the URL printed in the terminal. Keep that terminal running while editing; stop it with **Ctrl+C**. No environment variables are needed for the starter. If services are added later, document them in `.env.example` and keep actual secrets in an ignored local environment file.

## Daily workflow

From the repository root:

```text
git pull
npm ci
npm run dev
```

Create a feature branch for your assigned ticket, for example:

```text
git switch -c feature/ANF-D01-FE
```

Before opening a pull request:

```text
npm run lint
npm run typecheck
npm run build
```

Have a teammate review the change. Add smoke tests, accessibility tests, and CI checks as those sprint tasks are implemented. No `npm test` or mission-validation command is supplied by this bootstrap.

When deliberately adding a dependency, use `npm install PACKAGE_NAME` or `npm install --save-dev PACKAGE_NAME`, then commit both `package.json` and `package-lock.json`. Other teammates use `npm ci` after pulling.

## Project structure after bootstrap

```text
abandoned-but-not-forgotten/
|-- src/
|   |-- app/                  # Next.js routes, layout, and global styles
|   |-- components/
|   |   |-- scene/            # 3D canvas, models, lights, and camera
|   |   |-- story/            # Story sections and scroll interactions
|   |   `-- ui/               # Shared interface components
|   |-- lib/                  # Data loading and shared helpers
|   `-- types/                # TypeScript data types
|-- data/                     # Mission facts, schemas, sources, and credits
|-- public/
|   |-- models/               # Optimized GLB files served by the website
|   `-- images/               # Images and model fallback pictures
|-- assets/models-source/     # Local original model downloads; ignored
|-- scripts/                  # Future validation and model-processing scripts
|-- tests/                    # Future smoke and accessibility tests
|-- docs/                     # Storyboard, style guide, and design notes
|-- .nvmrc                    # Team Node.js major version
|-- package.json              # Dependencies and npm commands
|-- package-lock.json         # Resolved dependency versions
`-- README.md
```

## Mission data and models

The initial data work should create `data/missions.schema.json` and `data/missions.json` with two clearly labeled placeholder objects. Agree on fields for ID, name, date, location, goal, payload, story, and model path before building against the data.

Use a simple cube until real models are ready. Record source links, model licenses, and credits alongside the data. Serve optimized models from `public/models/<id>.glb`; their browser URLs are `/models/<id>.glb`.

The sprint plan calls for models under 2 MB each. Compression and automatic size checks remain implementation tasks. Downloading the original models is separate from `npm ci`.

## Local production check and deployment

After a successful build:

```text
npm start
```

This runs the production build locally. Stop any development server using the same port first.

The sprint plan proposes Vercel previews and production hosting. Repository connection, branch protection, CI, and deployment have not been configured by these setup instructions. The maintainer should add the agreed preview and deployment workflow once it is connected.

## Troubleshooting

| Problem | Action |
| --- | --- |
| `node`, `npm`, or `git` is not recognized | Install the missing tool and reopen your terminal. |
| PowerShell blocks `npm.ps1` or `npx.ps1` | Use `npm.cmd` or `npx.cmd` in place of `npm` or `npx`. |
| `package.json` is missing | Check your current directory. If this checkout contains only documentation, the maintainer must finish and push the bootstrap. |
| `package-lock.json` is missing | Pull the committed starter. The maintainer should generate the lockfile with `npm install` and commit it. |
| `npm ci` reports a lockfile mismatch | Pull the latest changes. If the mismatch persists, the person changing dependencies should run `npm install` and commit both package files. |
| A module cannot be found | Run `npm ci` from the repository root and restart the development server. |
| Port 3000 is occupied | Use `npm run dev -- --port 3001` and open the printed URL. |
| A model returns 404 | Check its filename and case in `public/models/`; use `/models/filename.glb` as its browser path. |
| No 3D story appears | The bootstrap generates a Next.js starter. Scene, content, and scroll behavior still need implementation. |



