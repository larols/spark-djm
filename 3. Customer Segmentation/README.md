# 3. Customer Segmentation

This lab consists of 4 files:
- purchases.csv - A record of previous orders
- customers.csv - A record of customers
- customer_segmentation.py - The actual application that the spark cluster will run
- spark-job.yaml - The yaml file that you will use to deploy the application


## Get started

In this lab we will continue to use the same process as previous labs. But we are introducing a more advanced job, we are reading from multiple documents and are applying Machine Learning capabilities to do the segmentation for us. You can see the customer_segmentation.py for more details.


Navigate to your Word Count folder
```
cd /path/to/spark-djm/3. Customer Segmentation/
```

Lets copy the files in the directory to your newly created folder
```
minikube cp customer_segmentation.py /mnt/data/customer_segmentation.py
minikube cp customers.csv /mnt/data/customers.csv
minikube cp purchases.csv /mnt/datpurchases.csv
```

SSH in to your minikube cluster and verify that the files have been copied:
```
minikube ssh
cd /mnt/data
ls
```

## Let's get sparking!
Let's try to run the application, deploy it using the spark-job.yaml

```
kubectl apply -f /path/to/spark-job.yaml
```

Check logs for output!


## Let us add Datadog Observability!
Check the spark-job.yaml, some lines of code are commented out.
Remove the "#" and rerun the job..

PS. you might have to delete it before applying it again.
```
kubectl delete -f spark-job.yaml
kubectl apply -f spark-job.yaml
```

## Add more data to analyse
Feel free to update the sales_analysis.csv with more data and check the output. Don't forget to reupload your new version to the minikube cluster.