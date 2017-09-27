# Descriptive analytics in Javascript

Descriptive analytics is usually the first step in data analytics exercise. As the name suggests, it **describes** a dataset. It answers the question, "**what happened**".

Any data set can be **described** with:

- summary factors like mean and mode;
- spread factors like standard deviation;
- shape or pattern factors like standard distribution. 

Let us talk with an example. Let us say that following are the unit sales figures for two sales managers for the last 6 weeks:
- 43,41,42,46,41,41
- 32,34,68,62,28,30

What do these numbers tell? In total, they both sold 254 items, which means they both are equally competitive. Their average is 42.3, which again says they both are equal in caliber. 

The standard deviation paints a different picture. The **standard deviation measures concentration of data around the mean**. The standard deviation for the first manager is 1.8, while the second one is 16.2. What does this mean? The first manager is consistent week after week in meeting his target, but the second manager is not. If all else remain the same, then this data indicates that the first sales manager is more dependable than the second one.

Now let us look at calculating these descriptive analytics for any dataset, using **Javascript**. The web is replete with Python tutorials, not much of Javascript. If developers are already using Node.js to develop web-application or they use Javascript for designing front-end development, they shouldn't have to use another language only for computing statistics.

We will use two packages for this purpose. The first one, [**csvtojson**](https://www.npmjs.com/package/csvtojson), is to read csv records and convert them into json values. The second one, [**simple-statistics**](https://www.npmjs.com/package/simple-statistics), is to compute statistics. Refer the [documentation](https://simplestatistics.org/docs/) for all the features of this package. In this post, we are using only the essential functions.

Simple Statistics takes an array of values and computes statistics. Computing sum, mean, and standard deviation for the above two sales values goes like this.

```
$ node
> const stats = require('simple-statistics');
> const first=[43,41,42,46,41,41];
> const second=[32,34,68,62,28,30];
> stats.sum(first)
254
> stats.sum(second)
254
> stats.mean(first)
42.333333333333336
> stats.mean(second)
42.333333333333336
> stats.standardDeviation(first)
1.7950549357115015
> stats.standardDeviation(second)
16.224124698183942
```

