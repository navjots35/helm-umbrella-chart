# Helm Umbrella Chart

We'll be building helm umbrella chart with `wordpress` and `mysql`

> Helm umbrella chart is basically charts within charts.

When you do 
```
helm create mychart
```

The current structure of helm chart we have is -

![Helm Structure](https://razorops.com/images/blog/helm-3-tree.png)

1. Delete everything from the templates directory except `_helpers.tpl`

2. Move to `Charts` Directory and Create 2 sub-charts
```
helm create wordpress
```
```
helm create mysql
```

3. Move to Each `/wordpress/templates` & `/mysql/templates` and delete everything except `_helpers.tpl`
4. Now, Create your `Deployment, Service etc` in `wordpress` & `mysql` subcharts respectively. Refer to this repo.

5. Come to the root directory & try 
```
helm template [folder-name] .
```
```
helm template mychart .
```
If you're getting an output. The umbrella chart working correctly.

>Under Dev
