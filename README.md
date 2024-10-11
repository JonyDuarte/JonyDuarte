## Hi, I'm João Carlos(Jony) 🧑‍🎓
<img align="center" alt="mysql" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original-wordmark.svg"><a/>
<img align="center" alt="python" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg" />
<img align="center" alt="git" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" />
<img align="center" alt="git" height="40" width="40" src="https://camo.githubusercontent.com/59f4d76d0aeda7683447d1878dc2234bcf42b256347205095f415910e789a827/68747470733a2f2f696d672e69636f6e73382e636f6d2f3f73697a653d3531322669643d6256477141544e776668597126666f726d61743d706e67"/>
<br>
name: Generate Datas
on:
  schedule: # execute every 24 hours
    - cron: "* */12 * * *"
  workflow_dispatch:
jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Summary Cards
      - uses: actions/checkout@v2
      - uses: vn7n24fzkq/github-profile-summary-cards@release
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          USERNAME: ${{ github.repository_owner }}

  # Snake Animation
  - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: JonyDuarte
          svg_out_path: dist/github-contribution-grid-snake.svg
      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
