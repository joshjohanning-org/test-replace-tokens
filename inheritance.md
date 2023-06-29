# Inheritance of vars

## Using a "common" repo
1. Create "common" repo with vars
2. Create composite action (just consists of other actions)
3. Check out "common" repo --> b/c this is another repo, need to pass in credentials to clone (there is a way to avoid passing credentials, and that way is to make the "common" repo a composite action as well that doesn't do anything.....before actions run, it clones the repo, so you can find that repo path on the runner and take the files from it)
4. Check out "local" repo
5. Run the variable groups action and pass in the "common" repo's variable file
6. Run the variable groups action and pass in the "local" repo's variable file


## Use org-level vars/secrets
If you use vars:
- Order is: Env, Repo, Org
- if you have a handful of org level vars, then since you are creating most of the reusable workflows, just map them in there to the `env`
