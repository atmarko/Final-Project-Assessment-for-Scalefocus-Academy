# Final-Project-Assessment-for-Scalefocus-Academy

#Final Project - Deploy a WordPress on Kubernetes (using Minicube) with Helm and automation with Jenkins.#



#1. Download Helm chart for WordPress. ( Bitnami chart:
https://github.com/bitnami/charts/tree/main/bitnami/wordpress )#

![image](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/fe0cf449-5187-4931-909a-a8e5a957675d)

![Screenshot 2023-05-16 215809](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/a5ff0c07-eeaf-455b-9bc7-c7faadf3725e)


![image](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/5e5ccdd2-9909-40b7-9749-e6eaf3365bab)

In order to have the helmchart for WordPress available locally, I forked the repo and downloaded it locally via GitHub Desktop.

#2. In values.yaml, you need to change line 543 from type: LoadBalancer to type: ClusterIP ( Hint: there
will be one more problem when deploying. Resolve it. )#

![image](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/9cd6967d-e36b-4405-83c4-15f1bb10cf4b)

ClusterIP is used for Pod-to-Pod communication within the same Kubernetes cluster. Opposed to LoadBalancer is used for communication with external clients outside the cluster. (connection is refused if it stays Type: Load Balancer and port forwarding stops to local host).

#3. Create a Jenkins pipeline that checks if wp namespace exists, if it doesn’t then it creates one.
Checks if WordPress exists, if it doesn’t then it installs the chart.#

![image](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/a649669f-aac2-48cc-9e82-3e46e468b6ee)

#4. Name the Helm Deployment as: final-project-wp-scalefocus.#
(the name of the folder should also have been renamed from wordpress).

#5. Deploy the helm chart using the Jenkins pipeline.#

![Screenshot 2023-05-16 210028](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/85b05649-fec9-4592-bddc-a3b9190438a3)


![Screenshot 2023-05-16 205712](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/6d7761d4-8903-4682-86da-e671e3513b5b)

#7. Load the home page of the WordPress to see the final result.#

![Screenshot 2023-05-16 210354](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/b8d4b067-607e-4a29-953b-c471ed970818)

![Screenshot 2023-05-16 210052](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/87dfcdec-a171-4568-9f19-23620360e008)

![Screenshot 2023-05-16 224908](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/6b887198-872c-4cff-a194-b8fef35c8324)


Retrieving the credentials but they needed to be in a different base to work.

![Screenshot 2023-05-16 211708](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/e5bb5992-c8fc-4b8c-a159-50fb8c8f0b37)

![Screenshot 2023-05-16 212006](https://github.com/atmarko/Final-Project-Assessment-for-Scalefocus-Academy/assets/119135923/ff754511-0dbb-42b3-9409-e8176e8e6064)

End of File.






