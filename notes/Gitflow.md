[[Branching Strategy]] where there are multiple branches maintained
- development - any new features are branched off of this. Release branches are created off of this
- production - release and hotfix branches are merged to this
- release - created off of development and merged into main and development then deleted
- hotfix - created off of development and must be merged to production and development