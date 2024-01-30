# 100 - Set up your first project

Projects are where you define configurations and manage secrets for a single service or application.
- Projects start with three default environments, each with a root config: Development, Staging and Production
- You can branch configs to allow overrides from the root configs
  
Click **[Projects](https://dashboard.doppler.com/workplace/364b965877a9404c6493/projects)**.

You will end up on the **Projects** page.

**PRO TIP**: Every service gets its own project. If you are using micro-services, create a project for each service.

Click the **+** icon to create a new project.

Give your project a name: **agility-game-kener**.

And a description: **Agility Game: Kener**.

Click **Create Project ->**.

You will be brought to the ```agility-game-kener``` project page at https://dashboard.doppler.com/workplace/364b965877a9404c6493/projects/agility-game-kener

**PRO TIP**: A project starts with development, staging and production environments. You can reorder environments and create custom ones.

Starting with our environments variables for a **development** environment, click on the default grey button called **dev**.

You will be brought to the **dev** environment variables of our project at https://dashboard.doppler.com/workplace/364b965877a9404c6493/projects/agility-game-kener/configs/dev

**PRO TIP**: Store any value in your configs, from passwords and API keys to configuration variables and multi-line certificates and JSON. Add notes to provide some context.

Under the tab **Secrets** click **Add First Secret**.

Start filling in the names and values (here ```********```, but put instead the true value) for each environment variable (click **+ Add Secret** after each entry to go to the next entry).

| NAME | VALUE |
| -- | -- |
| GH_TOKEN | ************ |
| API_TOKEN | *********** |

Click **Save** when done.

MORE ...

