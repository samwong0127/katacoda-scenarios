## Alert Manager

Open a new window

1.  View the Promethuse at localhost:9090:
    https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com

2.  Choose `Rules` in `Status` in the menu bar.
    ![Katacoda Logo](./assets/step7/Prometheus_Rules.jpg)

3.  Inside the rules, you will see the Alert Rules that contain in promethuse.
    ![Katacoda Logo](./assets/step7/Prometheus_Rules1.jpg)  

4.  Choose `Alerts` in the menu bar.
    Now you will see the status for all rules in promethuse.
    ![Katacoda Logo](./assets/step7/Prometheus_Alerts.jpg)

5.  Now, we simulate there is a micoservice "DOWN".
    1.  Back to the Katacoda webpage, one a new terminal.
        ![Katacoda Logo](./assets/step7/New_Terminal.JPG)
    2.  Remove either one microservice container
        `docker rm -f api_menu`{{execute}}
        ![Katacoda Logo](./assets/step7/Prometheus_DeleteContainer.jpg)
    3.  Wait ~ 1min, back to the promethus 
        The rules of check service 'DOWN' statuse will return to `Pending`
        ![Katacoda Logo](./assets/step7/Prometheus_Alerts_Pendine.jpg)
    4.  After ~ 1min it will check the service again, if it still in 'DOWN' status. The alert will return to `Firing`
        ![Katacoda Logo](./assets/step7/Prometheus_Alerts_Firing.jpg)
    5.  View the Alertmanger at localhost:9093:
        You will see the alert details.
    https://[[HOST_SUBDOMAIN]]-9093-[[KATACODA_HOST]].environments.katacoda.com
        ![Katacoda Logo](./assets/step7/Prometheus_Alerts_Firing.jpg)
    6.  Also, you will receive an email for the alert message.
        ![Katacoda Logo](./assets/step7/Prometheus_Alerts_Firing.jpg)