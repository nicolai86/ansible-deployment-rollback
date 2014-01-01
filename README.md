ansible-deployment-rollback
===========================

rollback for ansible-rails-deployment

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