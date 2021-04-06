Solutions applied to test and production will be managed solutions. There are some options when importing managed solutions that the solution architect needs to be aware of.

## Importing managed solutions

It is not a good idea to create new solutions for each change or release of your application. This will lead to dependencies between components that will prevent you from importing the solution. You should therefore make changed to your solution(s) and import the new version.

> [!NOTE]
> Solutions have version numbers. The version numbers are automatically incremented when you export a solution. You cannot import a solution with lower version number if the solution has already been imported with a higher version number.

When importing an new version of a managed solution, there are three import options:

- Update: Applies the changes in the solution.
- Upgrade: Imports changes and applies them immediately including removing components not in new solution, the old solution, and any patches are removed.
- Stage for Upgrade: Similar to upgrade but it pauses after new solution is imported before removing components so you can do data migration etc. You then manually trigger the final apply of the solution.

Updates to a managed solution are deployed to the previous version of the managed solution. This doesn't create an additional solution layer. You cannot delete components by using an update.

Upgrading a solution installs a new solution layer immediately above the base layer. Solution upgrades will delete components that existed but are no longer included in the upgraded version.

Upgrade is the default option.

> [!IMPORTANT]
> Using clone a patch and clone solution to update a solution is no longer recommended because it limits team development and increases complexity when storing your solution in a source control system.
