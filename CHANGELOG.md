# 1.0.0-alpha
- BREAKING: removed option MOB_NEXT_STAY. `mob next` always stays on the `mob-session` branch and doesn't switch back to master anymore (the tool can now handle any previous issues regarding staying on the mob-session branch)
- BREAKING: mob no longer creates merge commits, but will fail and provide a way to fix (git commands to copy and run)
- reworked the used git commands for `mob start`, `mob next` and `mob done`. They require less commands, meaning less steps, meaning a faster mob tool 
- several tests ensure the correctness of the mob tool now

# 0.0.19
- Removes zoom screen share integration.
- Less git commands necessary for 'mob start'

# 0.0.18
- Fixes a bug where boolean environment variables such as `MOB_NEXT_STAY` set to any value (including empty value) falsely activated their respective option.
- Simplified `mob start` when joining a mob session. It uses `git checkout -B mob-session origin/mob-session` to override any local `mob-session` in the process. It reduces the amount of commands necessary and makes the mob tool more predictable: the `origin/mob-session` always contains the truth.
- Removes `mob share` command. You can still enable the zoom integration via `mob start 10 share` although this is now DEPRECATED and will eventually be removed in the future.

# 0.0.16
- `mob start` prints out untracked files as well 
- `mob start --include-uncommitted-changes` now includes untracked files in the stash 'n' pop as well 
- keying in an unknown command like `mob conf` will internally call `mob help` to print out the usage options instead of calling `mob status`
- fixed a bug where overriding `MOB_START_INCLUDE_UNCOMMITTED_CHANGES` via an environment variable could print out a wrong value (didn't affect any logic, just wrong console output)

# 0.0.15
- Any `git push` command now uses the `--no-verify` flag

# 0.0.14
- New homepage available at https://mob.sh
- `mob config` prints configuration using the environment variable names which allow overriding the values

# 0.0.13
- Fixes bug that prevented users wih git versions below 2.21 to be able to use 'mob'.
 