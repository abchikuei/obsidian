### ⚡ CLI Tools 

| #   | Tool         | What it is / Why you use it                          | Common Use Case                                                                                  | Command Example            |
| --- | ------------ | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------ | -------------------------- |
| 1   | `yazi`       | Modern terminal file manager (fast, keyboard-driven) | Navigate and manage files visually in terminal                                                   | `yazi`                     |
| 2   | `neovim`     | Advanced extensible code editor                      | Write and edit code efficiently                                                                  | `nvim index.ts`            |
| 3   | `bat`        | Better `cat` with syntax highlighting                | Read code/files with colors                                                                      | `bat main.ts`              |
| 4   | `fzf`        | Fuzzy finder for files/commands                      | Quickly search files or history                                                                  | `fzf`                      |
| 5   | `zoxide`     | Smarter `cd` (tracks your habits)                    | Jump to frequently used dirs                                                                     | `z project`                |
| 6   | `ripgrep`    | Super fast text search tool                          | Search codebases                                                                                 | `rg "function"`            |
| 7   | `clipboard`  | Access system clipboard from CLI                     | Copy/paste between apps                                                                          | `echo "text"               |
| 8   | `eza`        | Modern `ls` replacement                              | List files with icons and git info                                                               | `eza -la`                  |
| 9   | `lazygit`    | Terminal UI for Git                                  | Manage commits, branches visually                                                                | `lazygit`                  |
| 10  | `lazydocker` | Terminal UI for Docker                               | Inspect containers/logs easily                                                                   | `lazydocker`               |
| 11  | `jq`         | JSON processor                                       | Parse API responses                                                                              | `curl api                  |
| 12  | `httpie`     | Human-friendly HTTP client                           | Test APIs with clean output                                                                      | `http GET api.example.com` |
| 13  | `mole`       | Deep mac cleaner                                     | Removes caches, logs, browser leftovers, and orphaned app data to **reclaim gigabytes of space** | `mole clean`               |
| 14  | `neofetch`   | Shows system info                                    | Display system details                                                                           | `neofetch`                 |
| 15  | `fd`         | Simpler, faster `find`                               | Locate files quickly                                                                             | `fd config`                |
| 16  | `delta`      | Better git diff viewer                               | Read diffs with syntax highlight                                                                 | `git diff`                 |
| 17  | `starship`   | Cross-shell prompt                                   | Customize terminal prompt                                                                        | `starship init`            |
| 18  | `tldr`       | Simplified man pages                                 | Quick command examples                                                                           | `tldr tar`                 |
| 19  | `direnv`     | Auto-load env variables                              | Manage project environments                                                                      | `direnv allow`             |
| 20  | `dust`       | Better disk usage tool                               | Analyze disk usage visually                                                                      | `dust`                     |
| 21  | `bottom`     | Modern system monitor                                | Replace `htop` with graphs                                                                       | `btm`                      |
| 22  | `hyperfine`  | Benchmark CLI commands                               | Compare performance                                                                              | `hyperfine "npm run dev"`  |
| 23  | `gitui`      | Lightweight Git TUI                                  | Fast Git operations                                                                              | `gitui`                    |


### 🧰 Developer & DevOps Tools 

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`brew`|macOS package manager|Install CLI tools easily|`brew install git`|
|2|`node`|JavaScript runtime|Run backend JS apps|`node app.js`|
|3|`npm`|Node package manager|Install JS dependencies|`npm install express`|
|4|`yarn`|Alternative package manager|Faster dependency installs|`yarn add react`|
|5|`pnpm`|Efficient package manager|Monorepos + disk savings|`pnpm add lodash`|
|6|`bun`|JS runtime + package manager|Fast dev + tooling in one|`bun run index.ts`|
|7|`deno`|Secure JS/TS runtime|Run TS without setup|`deno run app.ts`|
|8|`tsc`|TypeScript compiler|Compile TS → JS|`tsc`|
|9|`tsx`|Run TypeScript directly|Fast TS execution|`tsx app.ts`|
|10|`git`|Version control system|Track code changes|`git commit -m "init"`|
|11|`docker`|Containerization platform|Package apps with dependencies|`docker run nginx`|
|12|`kubectl`|Kubernetes CLI|Manage clusters|`kubectl get pods`|
|13|`minikube`|Local Kubernetes cluster|Run K8s locally|`minikube start`|
|14|`helm`|Kubernetes package manager|Deploy K8s apps easily|`helm install app ./chart`|
|15|`protobuf`|Data serialization format/tooling|Fast structured communication|`protoc --js_out=.`|
|16|`terraform`|Infrastructure as Code tool|Provision cloud resources|`terraform apply`|
|17|`ffmpeg`|Media processing tool|Convert/edit audio/video|`ffmpeg -i input.mp4 out.mp4`|
|18|`yt-dlp`|Video downloader|Download YouTube/media content|`yt-dlp url`|
|19|`aws`|AWS CLI|Manage cloud services|`aws s3 ls`|
|20|`gh`|GitHub CLI|Manage repos from terminal|`gh repo clone user/repo`|
|21|`railway`|Deployment platform CLI|Deploy backend apps|`railway up`|
|22|`vercel`|Frontend deployment CLI|Deploy web apps|`vercel deploy`|
|23|`nvm`|Node version manager|Switch Node versions|`nvm use 20`|
|24|`fnm`|Fast Node version manager|Lightweight alternative to nvm|`fnm use 20`|
|25|`pm2`|Node process manager|Run apps in production|`pm2 start app.js`|