ansible-deployment-rollback
===========================

rollback for ansible-rails-deployment.

This just changes the symlink of the current directory to the release prior to the current.
If no prior release exists nothing happens.

example usage:

    ---
    -
      role: nicolai86.ansible-deployment-rollback

      deploy_to: "{{ home_directory }}/application"

      tags: rollback

    -
      role: restart

      service: application:*

      tags:
        - deploy
        - rollback

You need to implement the restart yourself